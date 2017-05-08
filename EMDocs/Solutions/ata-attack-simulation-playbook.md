---
title: "Advanced Threat Analytics 攻击模拟手册"
description: "本指南将帮助客户了解针对 Windows 操作系统展开的凭据盗窃攻击、如何使用公开发布的调查工具来模拟此类行为，以及 Microsoft ATA 是如何检测这些威胁的。"
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 03/13/2017
ms.topic: solution
ms.prod: 
ms.service: advanced-threat-analytics
ms.technology: techgroup-identity
ms.assetid: da5eda7c-29bb-429f-9366-72495667c010
ms.reviewer: v-craic
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: cff5b87f6c5d0b9aa987631fefe5bf74e3a43862
ms.openlocfilehash: 41672ccdbd2c868add70e423b7dbc8048713259b
ms.contentlocale: zh-cn
ms.lasthandoff: 03/14/2017


---

# <a name="advanced-threat-analytics-attack-simulation-playbook"></a>Advanced Threat Analytics 攻击模拟手册

本指南将帮助你了解凭据盗窃（如传递哈希、传递票证、超传递哈希），以及如何使用公开发布的调查工具来模拟此类行为。 本攻击模拟手册的基础攻击场景是攻击者使用有效的 Internet 工具展开攻击。 旨在介绍如何像攻击者一样思考（图像式思维）、如何在凭据被盗的环境中移动，以及如何使用 Microsoft Advanced Threat Analytics (ATA) 在环境中检测这些活动。

本指南将介绍以下攻击场景：

- DNS 侦测
- 目录服务枚举
- SMB 会话枚举
- 搜集凭据 (lsass.exe)
- 超传递哈希
- 传递票证
- 远程执行代码
- 万能密钥
- DC 同步

> [!IMPORTANT]
> 只能在实验室环境中执行本指南中的步骤，不能在生产环境中执行。

## <a name="configuring-your-lab-environment"></a>配置实验室环境

建议严格遵循下面这些说明（包括最后的试验）。  需要进行一些设置，具体包括设置四台计算机、三位用户，以及用于抢占 Internet 的某调查软件。

有关如何安装 ATA 并获取 90 天评估版的详细指南，请参阅 [Advanced Threat Analytics 评估](http://aka.ms/ataeval)。 

> [!IMPORTANT]
> 本指南以 ATA 版本 1.7 为依据。


### <a name="scenario"></a>方案

在此示例实验室环境中，JeffV 是他自己的工作站管理员。  许多 IT 服务提供商仍为其用户群提供管理员权限。  在这种情况下，本地特权提升攻击是没有必要的，因为攻击者已在要执行后渗透操作的环境中拥有管理员访问权限。 
 
不过，即使 IT 服务提供商将特权降为使用非管理员帐户，攻击者也可以展开其他形式的攻击（如已知应用程序漏洞、零日攻击等）来实现本地特权提升。 在此示例中，本指南假定攻击者已在受害者 PC 上实现本地特权提升。  在这个虚构的实验室中，本地特权提升是通过向 JeffV 发送鱼叉式网络钓鱼电子邮件实现，本指南的后面部分将对此进行详细介绍。


### <a name="servers-and-workstations"></a>服务器和工作站

下面列出了需要使用的计算机，以及本次练习用到的配置。  这些全都暂存为 Windows 10 Hyper-V 上的来宾虚拟机 (VM)。  如果你选择这样做（也是建议操作），请确保 VM 位于同一虚拟交换机中。

| FQDN | 操作系统 | IP | 目的 |
| --- | --- | --- | --- |
| DC1.contoso.local | Windows Server 2012 R2 | 192.168.10.10 | 已安装 ATA 轻型网关 (LWGW) 的域控制器 |
| ATACenter.contoso.local | Windows Server 2012 R2 | 192.168.10.20 | ATA 中心 |
| Admin-PC.contoso.local | Windows 7 企业版 | 192.168.10.30 | 管理员的 PC |
| Victim-PC.contoso.local | Windows 7 企业版 | 192.168.10.31 | 受害者的 PC |

此实验室的域为“CONTOSO.LOCAL”。 创建此域，然后将这些计算机加入域中。 四台计算机全都设置且已加入域后，请立即转到下一部分，将一些虚构用户添加到环境中。


### <a name="users-configuration"></a>用户配置

现在要为技术支持和域管理员创建不同的角色。  创建这些角色旨在进行职责分离。不过，在本指南的后面部分中，你将了解到这并不足以防止凭据盗窃、横向移动或域权限提升发生，因为了解超越环境中这两组的安全依赖项并非易事。 

首先，在域中创建以下用户： 

| Name | 成員 | 目的 |
| --- | --- | --- |
| 支持人员 | RonHD | 管理 contoso.local 的客户端。 |

现在，创建以下安全组，每组包含一个特定成员：

| 全名 | SAM 帐户 | 目的 |
| --- | --- | --- |
| Jeff 受害者 | JeffV | 另一效果显著的鱼叉式网络钓鱼攻击的受害者 |
| Ron HD | RonHD | Ron 是 Contoso 的 IT 服务提供商的技术支持。  RonHD 是“技术支持”安全组的成员。 |
| Nuck Chorris | NuckC | 此前，认为不存在的角色。  恰好是 Contoso 的*域管理员*。 |

> [!IMPORTANT]
> 请确保已将 *RonHD* 添加为“*技术支持*”安全组的成员，然后再继续执行操作。


Contoso 的域管理员 Nuck Chorris 使用*管理员 PC* 工作站。 “*技术支持*”安全组（包含 *RonHD* 成员）也管理 *NuckC* 计算机。  可以使用[受限制的组](https://support.microsoft.com/kb/279301)对此进行配置。 管理员的组属性应如以下屏幕快照所示：

![管理员属性](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig1.png)

此外，*JeffV* 被添加为他自己设备（*受害者 PC*）上的管理员，就像许多 IT 服务提供商采用的设置一样。  这样做是有意而为之，本文的后面部分将对此进行说明。 本地管理员的组属性应如以下屏幕快照所示：

![管理员属性 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig2.png)


### <a name="security-research-tools"></a>安全调查工具

若要配置此实验室，需要下载下列工具，并将其安装到*受害者 PC* 中的 *C:\tools* 下：

- [Mimikatz](https://github.com/gentilkiwi/mimikatz)
- [PowerSploit](https://github.com/PowerShellMafia/PowerSploit)
- [PsExec](https://technet.microsoft.com/en-us/pxexec) 
- [NetSess.exe](http://www.joeware.net/freetools)

工具文件夹应如以下屏幕快照所示：

![管理员属性](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig3.png)


> [!IMPORTANT]
> 这些工具仅用于调查用途。  Microsoft 既没有这些工具的所有权，也无法保证其行为。  只能在测试实验室环境中运行这些工具。

鉴于此实验室的用途，请禁用*受害者 PC* 中的所有防病毒软件。 虽然禁用防病毒软件可能看似会导致结果出现偏差，但请务必注意，这些工具的源代码可免费获取，也就是说，攻击者可以修改源代码来规避基于防病毒软件特征的检测。 还请务必注意，只要攻击者成为计算机上的本地管理员，就很有可能规避防病毒软件。  此时的目标是保护组织的其余部分。 一台计算机遭到入侵不得导致域权限提升发生，当然也不得导致域入侵发生。

### <a name="environment-topology"></a>环境拓扑

此时，实验室应如下所示：

![拓扑](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig4.png)

如本指南的前面提到，存在不同的*域管理员*和*技术支持*角色，但在演示期间，你将会发现，只需利用一个安全依赖项联系角色（在此示例中，为用户 *RonHD*），攻击者就可以使用随时可用的调查工具操纵整个环境。

### <a name="helpdesk-simulation"></a>技术支持模拟

若要模拟常见的技术支持场景（即技术支持人员登录不同的计算机），请通过 *RonHD* 登录*受害者 PC*，然后以 *JeffV* 身份重新登录。  利用“切换用户”机制在此工作站上模拟特权凭据管理。

![切换用户](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig5.png)


还可以通过其他方式在此实验室中模拟这一管理工作流，如在命令行中创建批处理脚本服务帐户、计划任务和 RDP 会话或“runas”。  在安全操作中，某对象（不一定是某人）必须管理这些资源，而管理则表示拥有本地管理员权限。 鉴于此实验室的用途，为了节省时间，我们选择了模拟此工作流的最快方式。

> [!IMPORTANT]
> 此时，请勿注销或重启*受害者 PC*，因为这样会从内存中擦除 *RonHD* 的凭据，然后需要重现*技术支持*场景。 

下表汇总了每台计算机上保存的凭据：

| 计算机 | 计算机上保存的凭据 |
| --- | --- |
| 管理员 PC | - NuckC |
| 受害者 PC | - JeffV 和 RonHD（通过模拟技术支持场景） |

此时，实验室环境已准备就绪。 当前的实验室处于距域入侵攻击一步之遥的状态 (#1ea)。  接下来，你将看到野心勃勃且不会善罢甘休的攻击者通常会从环境中需要最低权限的资产开始，入侵大多数面向 Internet 的应用程序。  这样一来，[假设泄漏](https://blogs.msdn.microsoft.com/azuresecurity/2015/10/19/an-insiders-look-at-the-security-of-microsoft-azure-assume-the-breach/)方法就派上用场了。

## <a name="executing-the-attack"></a>执行攻击

在本指南的这一部分中，你将使用真实工具来模拟攻击者的后渗透活动。

### <a name="beachhead-via-spearphish"></a>通过鱼叉式网络钓鱼占领据点

对于此类攻击模拟，假定攻击者已在环境中的一台计算机上获取了本地管理员权限。  虽然这可以通过不同方法实现，但经常是通过对组织展开鱼叉式网络钓鱼活动来实现。 

[Microsoft 安全情报报告第 21 卷](https://www.microsoft.com/security/sir/default.aspx)中介绍了两个不同的参与者组（PROMETHIUM 和 NEODYNIUM）。 两个活动组均参与鱼叉式网络钓鱼，以便在其目标环境中占领据点。  原因是什么？  从攻击者的角度来看，使用电子邮件，可以快速规避组织的网络防御。 下图中的真实示例展示了 Microsoft Threat Intelligence Center 破译并处理的一个鱼叉式网络钓鱼电子邮件。

![鱼叉式网络钓鱼电子邮件](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig6.png)


在安全环境中，一个主机遭到入侵不得导致整个域或林被入侵。  在“后泄漏”场景中，请务必检测攻击者的后续行为。

### <a name="reconnaissance"></a>侦测

当攻击者占据环境后，侦测（亦称为“侦察”）就开始了。  在此阶段，攻击者会花时间来调查环境（发现设置、相关计算机、枚举安全组及其他相关活动目录对象等），以掌握环境的大致情况。

#### <a name="dns-reconnaissance"></a>DNS 侦测

许多攻击者首先都会做的一件事是试图从 DNS 接收所有内容，而 Microsoft ATA 可以检测此行为。

在受害者 PC 中，展开 DNS 侦测的第一步是使用 JeffV 凭据（这就是攻击者刚刚入侵的 PC 和用户）登录，然后运行以下命令： 
    
    nslookup
    ls -d contoso.local

结果应如以下屏幕快照所示：

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig7.png)

在此实验室中，DNS 已配置为阻止对域执行此类 DNS 转储操作。 不过，令人担忧的是，在网络杂讯中，此事件经常会被忽略或丢失，导致网络防御者没有发现攻击者已获取对其环境的某级别访问权限，并正在蓄谋更有针对性的攻击。

Microsoft ATA 可标记可疑的 DNS 活动，有助于检测这种类型的攻击，如下图所示：

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig8.png)

由于 ATA 持续分析 DNS 流量，因此它可以查看转储请求，无论其成功与否。  这样，以后如果可疑活动合法且来自获准 的 DNS 扫描设备，你也可以借鉴此事件。

在此示例中，攻击者差一点就大获全胜（即执行 DNS 转储，开始采用其他侦测技术）。

> [!IMPORTANT]
> 检测对环境展开的失败攻击与检测成功展开的攻击一样富有洞察力。
 
在上面的 ATA 警报中，你可能会发现“可疑活动”中的蓝色气泡，这表示 ATA 在不断学习生成的数据和分析反馈。  分析反馈有助于剔除无害的警报，并随着时间的推移减少噪音，从而自定义 ATA 及其环境可疑活动检测。

#### <a name="directory-services-enumeration"></a>目录服务枚举

[安全帐户管理器远程协议 (SAMR)](https://msdn.microsoft.com/library/cc245477.aspx) 提供了域用户和组管理功能。  了解用户、组和特权之间的关系对攻击者来说极为重要。  任何经过身份验证的用户都可以执行这些命令。 若要详细了解 SAMR 设置，以及如何限制为只有属于本地管理员组的用户才能进行此类侦测，请参阅[这篇文章](https://gallery.technet.microsoft.com/SAMRi10-Hardening-Remote-48d94b5b#content)。

#### <a name="enumerate-all-users-and-groups"></a>枚举所有用户和组

枚举用户和组对攻击者非常有用。  知道用户名和组名称也很有用。  作为攻击者，在侦测阶段希望获取尽可能多的信息。

若要模拟枚举用户和组，应使用遭到入侵的 *JeffV* 帐户登录*受害者 PC*。 登录后，尝试使用以下命令拉取所有域用户和组：

    net user /domain
    net group /domain

第一个命令的结果示例如下图所示：

![Net user](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig9.png)

第二个命令的结果示例如下图所示：

![Net group](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig10.png)

之所以能够成功执行这些操作，而未遇到任何问题是因为，这些操作是使用合法凭据执行的。 当前的问题是，攻击者现已了解环境中的所有用户和组。 如果不使用诸如 Microsoft ATA 之类的工具，此行为可能会遭到忽略。

对于此行为，Microsoft ATA 会显示攻击警报，以及攻击者能够获取的数据。

![侦测](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig11.png)

#### <a name="enumerate-high-privileged-accounts"></a>枚举高权限帐户

此时，攻击者持有用户列表和组列表。  但了解每个用户具体位于哪个组中也很重要，尤其对于高权限组（如“*企业管理员*”和“*域管理员*”）。 若要在实验室环境中获取此类信息，请在*受害者 PC* 中以 *JeffV* 的身份登录，然后执行以下命令：

    net group “domain admins” /domain

此命令的结果示例如下图所示：

![Net group 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig12.png)

攻击者现持有所有用户列表和组列表，并了解哪些用户属于高权限“*域管理员*”组。 在实际情形中，攻击者很有可能继续提升权限并试图获取企业管理员权限，因为“*企业管理员*”与“*域管理员*”之间没有安全边界。

> [!IMPORTANT]
> 若要详细了解林和域、“企业管理员”和“域管理员”之间的安全边界以及其他“第 0 层”权限，请参阅[保护特权访问参考资料](http://www.aka.ms/tier0)。

若要在实验室中获取“*企业管理员*”组的成员列表，请在*受害者 PC* 上运行以下命令：

    net group “enterprise admins” /domain

此命令的结果示例如下图所示：

![Net group 3](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig13.png)

在上面的示例中，“*企业管理员*”组中有一个帐户。 在此示例中，该信息并不十分有用，因为这只是默认帐户，但攻击者对帐户的了解远远大于此，并已确定他们最想要入侵的用户。

### <a name="smb-session-enumeration"></a>SMB 会话枚举

此时，攻击者知道要入侵哪个用户的凭据，但根据当前信息，他们并不完全知道如何入侵这些凭据。 使用 SMB 枚举，攻击者可以精确了解最关注的这些帐户的公开位置。

所有经过身份验证的用户都必须连接域控制器，才能（针对 SYSVOL）处理组策略，这就使得 SMB 枚举成为攻击者的宝贵工具。 这样一来，域控制器 (DC) 就成为 SMB 枚举的主要目标。

在这部分的实验室中，将用到 *NetSess*，这是从 Internet 下载的第一个调查工具。  *NetSess* 是用于在指定的本地或远程计算机上枚举 NetBIOS 会话的命令行工具。  

若要枚举在*受害者 PC* 上连接特定计算机（在此示例中，为 DC）的用户，请转到 NetSess 的本地保存位置，然后运行以下命令：

    NetSess.exe dc1.contoso.local

此命令的结果示例如下图所示：

![NetSess](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig14.png)

使用传统的安全控件（如防火墙）难以检测这种类型的侦测。 SMB 协议被 IT 服务提供商广泛使用，并且是 Active Directory 在执行许多操作时依赖的协议，这增加了此攻击获得成功的可能性。 Microsoft ATA 可以检测 SMB 会话枚举活动，并触发警报来提示哪些帐户已公开。

使用 Microsoft ATA，可以获取与攻击者一样的相关数据，包括源帐户、源计算机以及在攻击者进行枚举时公开的帐户和 IP 地址。 有关示例，请参阅下面的屏幕快照：

![SMB](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig15.png)

Microsoft ATA 提供的数据对于提高安全意识至关重要，这有助于你充分做好应对攻击的准备。

### <a name="lateral-movement"></a>横向移动

此阶段的目标是访问之前发现的 IP 地址 (192.168.10.30)，即公开 *NuckC* 的计算机凭据的位置。 为此，请枚举*受害者 PC* 上的内存中凭据。 请注意，*受害者 PC* 不只公开 *JeffV* 凭据，攻击者还可能会发现其他许多有用的帐户。 


若要从*受害者 PC* 中提取凭据，请使用 mimikatz，这是从 Internet 下载的另一个调查工具。 在*受害者 PC* 上提升的命令提示符处，转到保存 *Mimikatz* 的工具文件夹，然后执行以下命令：

    mimikatz.exe “privilege::debug” “sekurlsa::logonpasswords” “exit” >> c:\temp\victim-pc.txt

此命令的结果示例如下图所示：

![mimikatz](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig16.png)

以上命令将执行 mimikatz，然后将搜集内存中凭据。  此工具会将凭据写入“victim-pc.txt”文本文件中。 打开“victim-pc.txt”文件，看看可以获取哪些信息。

下一步是分析 *mimikatz* 的凭据转储输出。为此，需要在记事本中打开文件“victim-pc.txt”。  文件可能会因使用了不同的密码（默认设置是否启用因操作系统而异）而有所不同，因此如果文件与以下示例不完全一样，也不要惊慌。

![輸出](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig17.png)

根据此示例输出，攻击者发现了 JeffV 的凭据，这样就可以模拟 JeffV 了。 攻击者还发现了可以添加到其他计算机的“*本地管理员*”组和其他高权限安全组的计算机帐户，与用户帐户相似。  在此攻击场景中，此信息没有用，但应务必注意“*计算机帐户*”也可以映射到其他位置的权限帐户。

在下面的示例中，你将会注意到，攻击者还发现了一个可能会关注的帐户 *RonHD*。 请注意，*RonHD* 已在设置阶段登录*受害者 PC*。 此凭据在设置阶段就已向内存中 [LSA 进程](https://msdn.microsoft.com/library/windows/desktop/aa378327%28v=vs.85%29.aspx)公开，而 mimikatz 只是向攻击者显示此凭据。 枚举“*域管理员*”或“*企业管理员*”中的用户时，用户 *RonHD* 未列出，但现在有权访问他的凭据了。

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig18.png)

还有一点值得一提，在某些情况下，当环境未更新或未配置为阻止 [WDigest](https://blogs.technet.microsoft.com/kfalde/2014/11/01/kb2871997-and-wdigest-part-1/) 时，mimikatz 转储可能会公开纯文本密码。 根据最佳做法，最新环境将返回空的“*密码*”字段。   

作为攻击者，下一步自然是验证 *RonHD* 的帐户是否包含任何值。为此，攻击者将侦测该帐户。 若要在实验室中模拟此行为，请在*受害者 PC* 上执行以下命令：

    net user ronhd /domain

此命令的结果示例如下图所示：

![net user domain](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig19.png)

据此结果，攻击者就会知道 *RonHD* 是“*技术支持*”组的成员。 这样，*RonHD* 帐户就引起了攻击者的关注。  不过，需要进一步执行其他分析，才能确定此帐户是否拥有其他计算机上的管理员权限。 毕竟，如果使用此帐户横向移动到其他计算机，却发现它所拥有的权限低于攻击者的现有权限，那么这样做就没有多大意义。

因此，下一步是枚举远程计算机的成员身份。 在这一步中，将用到渗透测试程序使用的 PowerShell 模块系列 *PowerSploit*。 打开 PowerShell 会话，然后遍历到 *PowerSploit* 在*受害者 PC* 上的本地保存位置。  在 PowerShell 控制台中，执行以下命令：

    Import-Module .\PowerSploit.psm1
    Get-NetLocalGroup 192.168.10.30

第一个命令用于将 *PowerSploit* 模块导入内存，第二个命令用于执行此模块提供的函数之一（在此示例中，为 *Get-NetLocalGroup*）。

此命令的结果示例如下图所示：

![PowerShell](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig20.png)

如本指南前面部分所述，在 SMB 枚举阶段发现了 IP 地址 192.168.10.30。 攻击者刚刚发现了以下信息： 

- IP 192.168.10.30 连接*管理员 PC*（名称解析也是通过 PowerSploit 完成）
- “Contoso.local/Domain Admins”和“Contoso.local/Helpdesk”是*管理员组*的成员

*RonHD* 是“*技术支持*”组的成员，因此 *RonHD* 可以授予攻击者*管理员 PC* 上的*管理员*权限（攻击者在之前的侦测过程中了解到 *NuckC* 使用管理员 PC）。  
攻击者利用这样的[图像式思维](https://blogs.technet.microsoft.com/johnla/2015/04/26/defenders-think-in-lists-attackers-think-in-graphs-as-long-as-this-is-true-attackers-win/)发现网络中的关系。 防御者应采用这种思维来处理企业网络面临的新威胁。 

现在是时候利用 *RonHD* 展开[超传递哈希]()攻击，从而执行横向移动了。 如果攻击者处于的环境未禁用 WDigest，那么攻击者就已经胜利了，因为他们有纯文本密码。  不过，鉴于此实验室的用途，假定你不知道/无权访问纯文本密码。

使用超传递哈希技术，可以获取 NTLM 哈希，并使用它通过 Kerberos\Active Directory 获取票证授予票证 (TGT)。  借助 TGT，可以仿冒成 Ron**HD，并访问* RonHD* 有权访问的任何域资源。  

从之前搜集的 victim-pc.txt（通过“操作：转储受害者 PC 中的凭据”）中复制 *RonHD* 的 NTLM 哈希。 接下来，转到*受害者 PC*，访问 *mimikatz* 在文件系统上的存储位置，然后执行以下命令：

    Mimikatz.exe “privilege::debug” “sekurlsa::pth /user:RonHD /ntlm:[ntlm hash] /domain:contoso.local” “exit”

请务必使用从 victim-pc.txt 中粘贴的 NTLM 值替换 *[ntlm hash]*。

此命令的结果示例如下图所示：

![mimikatz 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig21.png)

此时，新的命令提示符会话会打开。这个新的命令提示符将 *RonHD* 的凭据插入了其中。 若要验证能否读取*管理员 PC* 的 C$ 内容（*JeffV* 本不能执行的操作），请在新的命令行会话中执行以下命令：

    dir \\admin-pc\c$
   
此命令的结果示例如下图所示：

![Dir](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig22.png)

此命令的结果证明，此时你已有权访问*管理员 PC* 的 C 驱动器。 现在，这就验证了已打开的新命令提示符已插入 *RonHD* 票证，并且你没有错误地将 *JeffV* 配置为拥有读取权限。

接下来，将在超传递哈希命令提示符处检查票证。 在执行超传递哈希攻击时打开的新命令提示符处，执行以下命令：

    klist

此命令的结果示例如下图所示：

![klist](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig23.png)

可以发现，此时你正在这个命令提示符处模拟 *RonHD*，这就验证了你已使用他的合法凭据获取了他自己的*管理员 PC* 的访问权限。

此时，你可能会发现 Microsoft ATA 发出了关于异常协议实现的警报，如下图所示。 这是因为超传递哈希使用 NTLM，所以 RC4 也是。 从防御者的角度来讲，你知道的是在*受害者 PC* 上，RonHD 的帐户已成功对域控制器进行了身份验证。  然后，就可以开始调查了。

![异常协议](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig24.png) 

### <a name="domain-escalation"></a>域权限提升

攻击者现已有权访问*管理员 PC*，在之前的侦测过程中，已发现此计算机是入侵高权限帐户 *NuckC* 的良好攻击途径。 攻击者现在想要移动到*管理员 PC*，提升他们的域权限。

为此，攻击者将展开[传递哈希](https://www.microsoft.com/security/sir/strategy/default.aspx#!pass_the_hash_defenses)攻击来搜集凭据，这样就可以移动到*管理员 PC*。   

在新的命令提示符处，在运行 *RonHD* 上下文的情况下，从相应的库转到 mimikatz 在文件系统中的位置，然后运行以下命令：

    xcopy mimikatz \\admin-pc\c$\temp

接下来，运行以下命令，远程执行 mimiKatz，以导出*管理员 PC* 中的所有 Kerberos 票证：

    psexec.exe \\admin-pc -accepteula cmd /c (cd c:\temp ^& mimikatz.exe “privilege::debug” “sekurlsa::tickets /export” ^& “exit”)

运行以下命令，将这些票证重新复制到*受害者 PC*：

    xcopy \\admin-pc\c$\temp c:\temp\tickets

此命令的结果示例如下图所示：

![XCopy](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig25.png) 

此操作表明，攻击者已将 *mimikatz* 工具成功复制到*管理员 PC*。 攻击者成功地远程执行了 mimikatz，导出了*管理员 PC* 中的所有 Kerberos 票证。  最后，攻击者将结果重新复制到了*受害者 PC* 上，现在攻击者已拥有 *NuckC* 的凭据，无需入侵他的的计算机了。

下一步是查找 *NuckC* TGT。 为此，必须查找不是 *NuckC* 的 kirbi 文件（即“ADMIN-PC$），然后删除这些文件并保留 *NuckC* 票证。

此命令的结果示例如下图所示：

![资源管理器](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig26.png) 

此时，攻击者可以将票证传递到内存，并使用它们获取对资源的访问权限，就像自己是 *NuckC* 一样。 攻击者可以将它们导入*受害者 PC* 的内存，以获取访问敏感资源所需的凭据。 此操作通过展开[传递票证](https://blogs.technet.microsoft.com/windowsserver/tag/pass-the-ticket/)攻击而完成。

在提升的命令提示符处（即 *mimikatz* 在文件系统中的位置），执行以下命令：

    mimikatz.exe “privilege::debug” “kerberos::ptt c:\temp\tickets” “exit”

此命令的结果示例如下图所示：

![mimikatz 权限](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig27.png) 

请确保 *NuckC@krbtgt-CONTOSO.LOCAL* 票证已成功导入，如上面的示例所示。

接下来，应验证命令提示符会话中的票证是否正确。 为此，请在同一个提升的命令提示符处执行以下代码：

    klist

此命令的结果示例如下图所示：

![klist 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig28.png) 

攻击者现已成功地将搜集的票证导入会话，并且现在将利用他们的新权限和访问权限来访问域控制器的 C 驱动器。 在刚刚导入票证的同一个命令提示符处执行以下命令：

    dir \\dc1\c$

此命令的结果示例如下图所示：

![dir 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig29.png) 

从各方面来说，攻击者现在就是 *NuckC*。 只有管理员才能访问域控制器的根。  攻击者现在使用的是合法凭据，可以访问合法的资源并执行合法的可执行文件。 

大多数 IT 服务提供商都会无视其环境中存在的这种后渗透活动。  Microsoft ATA 可以检测这种活动，如下图所示：

![渗透](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig30.png) 

可以发现，Microsoft ATA 检测到 Nuck Chorris 的票证从*管理员 PC* 中被盗，并被移动到*受害者 PC* 中。  ATA 还显示攻击者使用被盗的票证访问了哪些资源。  这样，不仅可以发现攻击，还能深入了解该从何处开始调查。 下图也表明 ATA 可以发现通过相关的传递票证攻击访问的资源：

![资源](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig31.png) 

作为网络防御者，这是需要关注的非常重要信息。 攻击者使用“dir \\dc1\c$”命令访问了 CIFS。  攻击者向本地 DC1 发送了 LDAP 请求，以访问 CIFS。  [KRBTGT](https://technet.microsoft.com/library/dn745899%28v=ws.11%29.aspx) 被用来直接与 DC1 通信并进行身份验证（访问 DC 的 c$ 驱动器的必需流程）。  由此，作为防御者，我们可以确认传递票证攻击活动促成了对 DC1 计算机的直接访问。

此时，大多数攻击者将尝试对 DC 远程执行代码。 这非常重要，因为修改“身份”层本身后要检测攻击者的存在极为困难。 若要模拟此行为，执行远程命令向域添加用户，然后使用 NuckC 的合法凭据，将其添加到“*管理员*”安全组。  所有这些都可通过内置工具完成，无需使用恶意软件或调查工具。

从 PsExec 在*受害者 PC* 上的位置处，执行以下命令：

    psexec \\dc1 -accepteula net user /add InsertedUser pa$$w0rd1
    psexec \\dc1 -accepteula net localgroup “Administrators” InsertedUser /add

此命令的结果示例如下图所示：

![psexec](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig32.png) 

攻击者刚刚创建了一个用户帐户，并使之成为*管理员*。 你显然通过远程执行代码利用了现在拥有的*域管理员*权限。  此外，你还可以创建其他*域管理员*和删除域管理员。  

Microsoft ATA 检测到*受害者 PC* 对 DC1 远程执行代码。  在下面的示例屏幕中，ATA 检测的是攻击者成功和失败的攻击尝试。

![远程执行代码](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig33.png) 

### <a name="domain-dominance"></a>域控制

攻击者已实现了域控制，他们可以管理员的身份运行任意代码，并能访问域中的所有资源。
 
不过，为了确保域控制的持久性，需要采用后门程序和其他机制作为保险策略，以防原攻击方法被发现或凭据随机被重置。 此时假定攻击者想要创建到达 DC 的最终后门程序，即快速创建拥有*管理员*权限的用户的方法，此方法被称为“万能密钥”。 

下一步是在 DC1 上插入万能密钥攻击。 首先，必须将 *mimikatz* 复制到 DC。 请注意，在此阶段务必要确定 DC 是 32 位还是 64 位计算机。  示例使用的是 64 位计算机，请根据特定环境的需求进行修改。

    xcopy x64\mimikatz.exe \\dc1\c$\temp\

接下来，将运行以下命令使用 *PsExec* 远程执行它，并部署万能密钥：

    PsExec \\dc1 -accepteula cmd /c (cd c:\temp ^& mimikatz.exe “privilege::debug” “misc::skeleton” ^& “exit”)

此命令的结果示例如下图所示：

![PSExec2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig34.png) 

攻击者使用万能密钥“修补”了 LSASS.exe 二进制文件。  此时，攻击者已可以使用万能密钥。 若要模拟此行为，以 *JeffV* 身份打开命令提示符。  首先要验证没有其他用户的票证。 执行此步骤只是为了可以完全确认当前的运行状况。 在*受害者 PC* 中，以 *JeffV* 身份执行以下命令：

    klist

此命令的结果示例如下图所示：

![klist nucko](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig35.png) 

如上面的示例所示，没有高权限票证。  也就是说，攻击者将要运行的每个命令只能拥有 *JeffV* 的权限。 现在要尝试通过映射 DC1 的 C$ 来对 DC1 进行身份验证。  为了说明并不是每个密码都有效，将故意使用错误的密码。 在同一个干净的命令提示符处，执行以下命令：

    net use k: \\dc1\c$ wrongpassword /user:Administrator@contoso.local

此命令的结果示例如下图所示：

![net use](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig36.png) 

如上面的示例所示，此命令失败了，与预期的一样。  但万能密钥将派上用场。 你将重新尝试执行同一命令，但现在使用的是你刚刚向对 DC1 进行过身份验证的各个帐户（插入万能密钥的位置）添加的万能密钥。 在命令提示符处，执行以下命令，但这次使用的是主密钥“mimikatz”：

    net use k: \\dc1\c$ mimikatz /user:Administrator@contoso.local

此命令的结果示例如下图所示：

![net use 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig37.png) 

借助主密钥“mimikatz”（硬编码），攻击者可以获取管理员权限。  此密钥不是帐户密码，而是使用修补进程到达 DC1 并以管理员（或其他任何安全组）的身份对任意用户进行身份验证的方法。 请注意，每个帐户现在有 2 个活动密码：

- 用户/管理员创建的原密码。
- 万能主密钥  

Microsoft ATA 可以检测此活动，如以下示例所示：

![万能密钥](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig38.png) 

目前，攻击者无论在 DC 上执行什么操作，都必须在 DC 上运行任意代码。  ATA 通过显示相应的可疑活动标记，并向网络防御者提供要修正的信息，从而检测到这些行为。 不过，攻击者可能想要展开更为隐蔽的攻击来继续他的入侵，这种攻击不在 DC 上运行任意代码（无需 *PsExec* 或将万能密钥直接插入 LSASS 进程）。
此时选择的调查工具 *Mimikatz* 具有称为“DC 同步”的功能。  这样一来，攻击者可以使用域管理员凭据将任意凭据重新复制到计算机上，如同是在 DC 上一般。

打开包含 *NuckC* 凭据的命令提示符，转到命令提示符处，并确保 NuckC 的票证仍已插入会话，如以下示例所示：

![票证](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig39.png) 

至此，你知道自己使用的是正确的工作台，可以模拟攻击者并尝试获取域的终极凭据：[KRBTGT](https://technet.microsoft.com/library/dn745899.aspx#Sec_KRBTGT)。  之所以需要使用此帐户是因为通过此帐户你可以签署自己的票证。

在*受害者 PC* 上现已验证的 *NuckC* 命令提示符处，遍历到 mimikatz 在文件系统上的位置，执行以下命令：

    mimikatz.exe “lsadump::dcsync /domain:contoso.local /user:krbtgt “exit” >> krbtgt-export.txt

此命令的结果示例如下图所示：

![lsadump](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig40.png) 

攻击者打开“krbtgt-export.txt”后，便拥有所需的 KRBTGT 详细信息。  打开刚刚将哈希导出到其中的“krbtgt-export.txt”文件，如以下示例所示：

![KRBTGT](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig41.png) 

此时，攻击者已拥有所需的一切，可以使用窃取的 NTLM 哈希签署所有资源的任何 TGT，无需再返回域控制器。  这样一来，攻击者就可以根据需要随时仿冒任何人员（直至 KRBTGT 帐户本身重置两次）。

Microsoft ATA 可以发现这种类型的攻击，如以下示例所示：

![攻击](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig42.png) 

Microsoft ATA 不仅检测到此攻击，还提供了执行修正操作所需的信息。

利用 KRBTGT 签署伪造票证被称为“黄金票证”攻击，也可以通过 ATA 检测到。  不过，鉴于基于范围和签名的检测的目的，它已超出本指南的范围。

## <a name="conclusion"></a>结论

Microsoft ATA 可以提供其他服务所不能提供的信息和见解，从而帮助你保护网络。  Microsoft ATA 将标识平台变成了发现环境中的后渗透活动的强大检测工具。  Microsoft ATA 可帮助你汇编宏事件，并将其迅速转变成连贯的攻击场景。

![结论](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig43.png) 

Microsoft ATA 提供了“假设泄漏”（必须发现后渗透活动）的必备见解和情报。  防火墙、防病毒引擎、入侵检测服务和入侵防护服务都会尝试阻止攻击者进入，但是当攻击者恶意利用包含合法凭据的合法工具入侵后，它们或多或少都会有所懈怠。  在网络安全领域，真正了解这些恶意活动非常关键。 

有关 Microsoft ATA 的详细信息，请访问 [Microsoft ATA](https://www.microsoft.com/cloud-platform/advanced-threat-analytics) 页面，或发送电子邮件至 ataeval@microsoft.com。




