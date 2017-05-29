---
title: "条件访问 - 本地 Exchange、Intune、Configuration Manager"
description: "使用 Configuration Manager、本地 Exchange Server 和 Intune 来管理电子邮件访问和保护移动设备上的电子邮件数据。"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56b6cd2d-3dea-468b-9f1c-92717c9ec5f5
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: 9778ccfc6a2c7583e0659c76e7ada91711517243
ms.contentlocale: zh-cn
ms.lasthandoff: 05/29/2017


---

# <a name="deploy-exchange-server-on-premises-with-microsoft-intune-and-configuration-manager"></a>将 Microsoft Intune 和 Configuration Manager 与本地 Exchange Server 结合部署
你已通读了[有关保护公司电子邮件和文档的体系结构指南](architecture-guidance-for-protecting-company-email-and-documents.md)，现在可以继续部署解决方案。

如果你已在你的本地基础结构中使用 System Center Configuration Manager 和 Exchange，则你可以集成 Intune 来管理移动设备上的电子邮件访问和保护电子邮件数据。 用于实施此解决方案的高级别过程如下所示：

-   通过 Configuration Manager 控制台配置本地 Intune Exchange Connector，这会使 Configuration Manager 与托管移动设备的邮箱的 Exchange Server 进行通信。

-   运行 Exchange Server 连接器的完全同步，以便发现用户，并列出与本地 Exchange Server 连接的所有移动设备的 Exchange ActiveSync ID (EASID) 的清单。

-   创建要在条件访问策略中包括或排除的用户组的用户集合。 然后创建合规性策略，这些策略用于定义设备必须遵从的规则和设置，以便将设备视为符合条件访问策略。

-   开始实施条件访问。

## <a name="conditional-access-control-flow-for-exchange-server-on-premises"></a>本地 Exchange Server 的条件访问控制流
下图显示客户端试图在本地 Exchange 中访问电子邮件的控制流。

![与 Intune 和本地 Exchange Server 结合使用的 Configuration Manager 中的条件访问控制流程图](./media/ProtectEmail/Hybrid-on-prem-CA-architecture.png)

-   Microsoft Intune：管理设备的合规性和条件访问策略

-   Microsoft Azure Active Directory：对用户进行身份验证，并提供设备的合规性状态

-   Configuration Manager：管理设备注册和提供报表

-   本地 Exchange：根据设备状态执行对电子邮件的访问

## <a name="before-you-begin"></a>在开始之前
确保你的环境满足实施此解决方案的要求。

> [!NOTE]
> 如果你已将 Configuration Manager 配置为通过 Intune 服务管理移动设备，则你可以继续[部署步骤](#deployment-steps)。

-   确认满足[本地连接器的硬件要求](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)。

-   确认你运行的是具有累积更新包 1 或更高版本的 System Center 2012 R2 Configuration Manager SP1。

-   确保已正确配置 [Exchange Web 服务 (EWS) 终端](https://technet.microsoft.com/library/hh529912.aspx)用于发现。 如有必要，请联系 Configuration Manager 支持团队，以获取一种可帮助识别 EWS 连接问题的工具。 EWS 通过使用标准 HTTP 使开发人员与 Exchange 邮箱和内容交互。

-   安装 Exchange 服务并分配到从受信任的公用证书颁发机构购买的[有效数字证书](https://technet.microsoft.com/library/dd351044.aspx)。

-   配置具有运行以下 Exchange Server cmdlet 的权限的帐户（本地或域管理员）：

    Clear-ActiveSyncDevice

    Get-ActiveSyncDevice

    Get-ActiveSyncDeviceAccessRule

    Get-ActiveSyncDeviceStatistics

    Get-ActiveSyncMailboxPolicy

    Get-ActiveSyncOrganizationSettings

    Get-ExchangeServer

    Get-Recipient

    Set-ADServerSettings

    Set-ActiveSyncDeviceAccessRule

    Set-ActiveSyncMailboxPolicy

    Set-CASMailbox

    New-ActiveSyncDeviceAccessRule

    New-ActiveSyncMailboxPolicy

    Remove-ActiveSyncDevice

> [!IMPORTANT]
> 如果你尝试在没有所需 cmdlet 的情况下安装或使用 Exchange Server 连接器，你将看到以下消息记录的错误：站点服务器计算机上的 EasDisc.log 文件中_调用 cmdlet &lt;cmdlet&gt;失败_。

## <a name="deployment-steps"></a>部署步骤
请按照以下步骤来部署本地 Exchange 解决方案：

### <a name="step-1-ensure-that-intune-connector-role-is-installed"></a>步骤 1：确保安装了 Intune Connector 角色。
确保已安装 Intune Connector 角色，以便 Configuration Manager 可以与 Intune 进行交互。 有关详细信息，请参阅[使用 Configuration Manager 和 Intune 管理移动设备](https://technet.microsoft.com/library/JJ884158.aspx)。

### <a name="step-2-install-and-configure-an-exchange-server-connector"></a>步骤 2：安装和配置 Exchange Server 连接器。
Configuration Manager 仅支持一个 Exchange 组织包含一个连接器。

> [!IMPORTANT]
> 在安装 Exchange Server 连接器之前，请确认 Configuration Manager 支持你所使用的 Microsoft Exchange 的版本。 有关详细信息，请参阅 [Configuration Manager 支持的配置](https://technet.microsoft.com/library/gg682077.aspx)。

按照[如何使用 Configuration Manager 和 Exchange 管理移动设备](https://technet.microsoft.com/library/gg682001.aspx)中的步骤安装并配置 Exchange Server 连接器。

### <a name="step-3-run-a-full-synchronization-to-discover-users"></a>步骤 3：运行完全同步来发现用户。

1.  在 Configuration Manager 控制台中，单击“管理” ，展开“层次结构配置” ，然后选择“Exchange Server 连接器” 。

2.  选择在步骤 2 中安装的 Exchange Server 连接器。

3.  单击“立即同步” 。

    ![显示在何处对 Configuration Manager 控制台执行完全同步的屏幕截图](./media/ProtectEmail/Hybrid-Onprem-Run-FullSync.png)

此完全同步可能需要几个小时才能完成，具体取决于设备的数目。 默认情况下，完全同步每 24 小时运行一次。 增量同步将发现自上次完全同步之后的设备连接，并且按照你在安装 Exchange Server 连接器时设置的间隔时间执行同步。 这可以确保快速发现新用户和新的 Exchange 用户，以便应用条件访问。

使用 Configuration Manager 跟踪日志工具，可以打开 EasDisc.log 文件（位于安装 Configuration Manager 的 **Microsoft Configuration Manager/Logs** 文件夹）以验证连接器是否正在运行和查询设备连接。 完全同步完成后，该工具将列出与本地 Exchange 连接的所有移动设备的 Exchange ActiveSync ID (EASID) 的清单。

### <a name="step-4-create-user-collections"></a>步骤 4：创建用户集合
确定条件访问策略将要针对的 Intune 用户组。 然后，创建要在条件访问策略中包括或排除的用户组的用户集合。 你可以在以后实施条件访问时指定这些组。

请按照[如何在 Configuration Manager 中创建集合](https://technet.microsoft.com/library/gg712295.aspx)的步骤创建用户集合。

### <a name="step-5-create-compliance-policies-and-deploy-to-users"></a>步骤 5：创建合规性策略，并部署到用户。
合规性策略定义设备必须遵从的规则和设置，以便将设备视为符合条件访问策略。 请按照 [Configuration Manager 中的合规性策略](https://technet.microsoft.com/library/mt131417.aspx)中的步骤创建合规性策略。

如果你希望在 iOS 设备不再属于公司之后，你能够从该设备中删除所有公司的电子邮件，那么你必须创建并部署电子邮件配置文件，然后设置合规性策略，该策略指定由 Intune 管理电子邮件配置文件。 你必须将电子邮件配置文件部署到此合规性策略针对的同一用户集。

![显示“创建符合性策略向导”的“规则”页面的屏幕截图，你可以在该页面指定电子邮件配置文件必须由 Intune 管理](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

如果你指定此合规性策略，则已设置电子邮件帐户的用户必须手动删除它，之后 Intune 会通过[条件访问的最终用户体验](end-user-experience-conditional-access.md)中描述的注册过程将其重新添加。

创建合规性策略后，在列表中选择合规性策略的名称，然后单击“部署” 。

### <a name="step-6-configure-conditional-access-policy"></a>步骤 6：配置条件访问策略。
首先，确定以何种方式、何时实施条件访问，以及将影响哪些员工。 然后，按照 [Configuration Manager 中针对 Exchange 电子邮件的条件访问](https://technet.microsoft.com/library/mt131421.aspx)中的步骤为本地 Exchange 配置条件访问策略。

### <a name="step-7-monitor-enrollments-and-enforce-conditional-access"></a>步骤 7：监视注册情况并实施条件访问。
如果 Intune 中已经注册大量符合条件访问的用户，则你可以开始实施条件访问，方法是每天向大约 500 个用户推出条件访问。 对于 70,000 个用户，这将需要花费大约 4 到 5 个月的时间，并且你需要解决在未限制太多用户在同一时间访问电子邮件的情况下可能产生的任何问题。

如果 Intune 中尚未注册大量用户，则条件访问将为用户提供针对注册的引导式体验，如[条件访问的最终用户体验](end-user-experience-conditional-access.md)中所述。

## <a name="verification-steps"></a>验证步骤
使用 Configuration Manager 跟踪日志工具，可以打开 EasDisc.log 文件（位于安装 Configuration Manager 的 Microsoft Configuration Manager/Logs 文件夹）。 在日志文件中搜索 "Exchange Connector" 以查找有关 Exchange Connector 是否正在运行以及连接的设备数量的信息。

![显示 EasDisc 日志文件在 Configuration Manager 跟踪日志工具中打开的屏幕截图](./media/ProtectEmail/Hybrid-Onprem-Eas-DiscLog-Sample.PNG)

Configuration Manager 跟踪日志工具包含在 [System Center 2012 R2 Configuration Manager 工具包](http://www.microsoft.com/download/details.aspx?id=50012)中。

## <a name="reporting"></a>报表
可以使用 Configuration Manager 控制台以查看有关 Exchange Connector 已发现的设备的特定信息。 对于已实施条件访问的设备，你可以查看每个设备的当前状态、最后一次使用 Exchange Server 连接设备的时间等等。

在 Configuration Manager 控制台中，单击“资产和合规性”  ，然后单击“设备” 。 在“Exchange 访问状态”列中可以查看每个设备的当前状态（阻止或允许）  。 如果该列尚未显示，可以右键单击列标题栏区域来添加该列。 通过添加“上次成功同步到 Exchange Server 的时间”  列，还可以查看如 Exchange 报告的每个设备的上次成功同步时间。

![显示 Configuration Manager 控制台中的设备列表的屏幕截图](./media/ProtectEmail/Hybrid-Onprem-Verify-Devices-State.png)

如果你正在运行 SQL Server Reporting Service (SSRS)，则可以查看条件访问报表，其中显示了设备的合规性状态、是否已安装并运行 Exchange Connector，以及 EAS 访问状态。 该报表还将提供有关 Active Directory 注册、EAS 激活，以及设备所有者的信息。

![显示 SQL Server Reporting Services 报表的一个示例的屏幕截图](./media/ProtectEmail/Hybrid-Reports-CA.png)

要查看 SSRS 报表，必须在主服务器上安装报表角色：

1.  在 Configuration Manager 中，依次单击“管理” 、“层次结构配置” 、“站点配置” 和“服务器和站点系统角色” 。

2.  选择一个服务器，然后单击“添加站点系统角色”  以打开“添加站点系统角色”向导。

3.  在“系统角色选择”页面上，选择“报表服务点”  复选框。 报表服务点将显示与客户端管理相关的报表。

4.  单击“下一步” 。

下面显示了配置策略的部署状态：

![显示配置策略的部署状态的屏幕截图](./media/ProtectEmail/Hybrid-Reports-Deployment-Status.png)

### <a name="latency"></a>延迟
当 Exchange Connector 发现设备后，设备即被阻止。 阻止的延迟时间取决于完全同步和增量同步所配置的时间间隔以及设备连接到 Exchange Server 时这两个时间间隔之间的时间。 默认情况下，完全同步每 24 小时执行一次，增量同步每 240 分钟执行一次。 设备在延迟期间视为合规。

## <a name="where-to-go-from-here"></a>后续步骤
当你在移动设备上部署保护企业电子邮件和电子邮件数据的解决方案后，你可以了解有关[条件访问的最终用户体验](end-user-experience-conditional-access.md)的详细信息。 这将帮助你为最终用户注册其特定设备时可能出现的问题做好准备。

