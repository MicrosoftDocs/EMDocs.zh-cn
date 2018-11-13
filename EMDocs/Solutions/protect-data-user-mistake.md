---
title: 针对用户错误保护数据 | Microsoft Docs
description: 此方案介绍如何使用企业移动性 + 安全性，通过利用 Cloud App Security 和 Azure 信息保护功能，针对用户错误保护企业数据并防止数据丢失。
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 09/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.assetid: 0af3894c-7b0e-4c0c-8874-31e041d81300
ms.reviewer: v-craic
ms.suite: ems
ms.custom: information-protection
ms.openlocfilehash: 5b1e5d113546da0df64e7777c0031543a7096a72
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196689"
---
# <a name="protect-data-against-user-mistakes"></a>针对用户错误保护数据

过渡到移动方式和云后，员工的工作效率显著提高，但是用户、设备、应用与本地及云中的数据之间的复杂交互也为 IT 团队制造了新的盲区。 尽管组织可能不接受这种转移，但员工已经接受了。 由于这些元素之间的交互和攻击媒介的复杂性在增加，安全性仍然是企业的最大挑战。 IT 人员致力于维持企业数据可见性和对企业数据的控制和保护。

数据控制资源可针对用户错误保护企业数据并防止数据丢失，是实现保护资源同时保持用户高效的重要环节。

## <a name="how-can-enterprise-mobility--security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？

企业移动性 + 安全性 (EMS) 可使 IT 深入了解本地和云中的用户、设备和数据活动。  通过 EMS，IT 可以借助更强的控制力和执行力，针对用户错误保护企业数据。  IT 将能够通过针对已发现的应用程序的用户、上传/下载流量、使用模式和交易，应用强大的报表和分析功能，来监视风险检测。

## <a name="recommended-solution"></a>建议的解决方案

为满足此方案的要求，EMS 使用 [Cloud App Security](https://technet.microsoft.com/library/mt489024.aspx) 和 [Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)。 通过实施这些技术，组织将能够：

- 全面了解员工的云应用使用情况和影子 IT
- 应用粒度级别控制和数据策略，以在云应用中持续保护数据
- 实现数据的持久性分类和保护，以确保数据随时受到保护 - 无需考虑数据的存储位置或共享对象
- 安全地与组织内外的人员共享数据
- 直观控制数据分类和保护
- 了解和控制用户和 IT 的共享数据

下图总结了此方案涉及的功能以及如何使用这些功能保护资源：

![图示：Cloud App Security 和 Azure 信息保护协同工作以保护本地和云中的数据。](./media/protect-data-user-mistake/protect-data-user-mistake-fig1-1.png)

在下面的简短视频中，可以快速概览企业移动性 + 安全性 (EMS) 如何让 IT 人员了解更多信息，并能掌控一切：

<iframe width="675" height="480" src="https://www.youtube.com/embed/LWlRVHp7sKQ" frameborder="0" allowfullscreen></iframe>


## <a name="how-to-implement-this-solution"></a>实现本解决方案的方式

执行以下步骤以实现 [Cloud App Security](https://technet.microsoft.com/library/mt668458.aspx) 和 [Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)：

- 步骤 1：发现使用中的云应用并使用策略进行控制
- 步骤 2：保护本地或云中的数据

## <a name="how-to-protect-data-against-user-mistakes"></a>如何针对用户错误保护数据

现今大多数企业都在使用云应用程序，云中存储的企业数据超过本地存储的企业数据的时代将很快到来。 很多时候，用户会在未经公司同意或公司不知情的情况下从其设备上使用 SaaS 应用，这会导致影子 IT 的云使用率增加。 此结论根据多项研究结果得出，研究显示 80% 的员工表示其出于工作需要在未经批准的情况下使用 SaaS 应用。 [Cloud App Security](https://technet.microsoft.com/library/mt657567.aspx) 提供组织中正在使用的所有云应用的详细总览。 它会标识访问应用程序的所有用户和 IP 地址。 还能对超过 13,000 个云应用执行风险评估，并基于 60 多项参数提供每个应用的自动风险评分。 

执行步骤 1 以发现环境中的云应用，并实施策略以控制这些应用。 此解决方案的第二个阶段将实现 [Azure 信息保护](https://docs.microsoft.com/information-protection/get-started/requirements)，目的是保护数据并进行分类，这有助于减少用户出错和误用数据的情况。

### <a name="step-1-discover-cloud-apps-in-use-and-control-them-with-policy"></a>步骤 1：发现使用中的云应用并使用策略进行控制

使用 Cloud App Security 的第一步是[发现应用](https://technet.microsoft.com/library/mt657567.aspx)。 如果跳过此步骤，则不会有可进行分析和使用策略进行限制的应用。 如果没有启动发现流程，Cloud App Security 仪表板中的“发现”选项将显示以下消息：

![显示消息的屏幕截图，消息指示用户尚未上传 Cloud Discovery 日志。](./media/protect-data-user-mistake/protect-data-user-mistake-fig2-1.png)

发现组织中正在使用哪些应用是确保企业敏感数据受到保护的第一步。 发现过程完成后，[Cloud Discovery 仪表板](https://technet.microsoft.com/library/mt727946.aspx)下将会显示发现的应用的列表。

![屏幕截图，显示 Cloud Discovery 仪表板和发现的应用的列表。](./media/protect-data-user-mistake/protect-data-user-mistake-fig3.png)

每个应用都有一个分数，表示该云应用的可信度和可靠性。 查看应用排名时，会注意到三个用于创建排名的类别：常规、安全性和合规性。 每个类别都具有测试期间会进行测试的特定属性。 如果某个属性不是完全相容的，会显示一部分，可以访问该属性的详细信息以了解其部分显示的原因。

![屏幕截图，显示“HTTP 安全标头”属性的详细信息。](./media/protect-data-user-mistake/protect-data-user-mistake-fig4.png)

下一步是控制使用策略发现的应用程序的行为。 此功能使 IT 人员能够微调已发现的应用程序和与组织关联的风险级别。 策略有不同类型；应首先创建的策略取决于组织的业务要求。 默认情况下异常检测策略为启用状态，因此不需要为其配置新的策略便可运行。 但是，可以微调默认策略中要针对其发出警告的异常类型。

![屏幕截图，显示如何选择要创建的策略类型。](./media/protect-data-user-mistake/protect-data-user-mistake-fig5.png)

配置策略后，便可调查可能发生的违反当前策略的情况。 在此特定方案中，需要验证云中是否存在任何个人身份信息 (PII)。 有关此活动类型的信息，请通过“文件策略”查看。 将要查看的文件级策略是 PII 合规性策略。 此策略旨在识别包含个人身份信息（已公开共享）的文件，并提供用于调查和修正的选项。

![屏幕截图，显示如何调查文件策略类型以发现潜在的违反策略的情况。](./media/protect-data-user-mistake/protect-data-user-mistake-fig6.png)

在此特定情况中，对于此策略，有三个匹配项，也就是说有三个文件与此策略相匹配。 可以单击其中一个文件以调查文件的名称和位置。

### <a name="step-2-protect-data-on-premises-or-in-the-cloud"></a>步骤 2：保护本地或云中的数据

实现此解决方案之前，请先查看 [Azure 信息保护](https://docs.microsoft.com/information-protection/get-started/infoprotect-tutorial-step1)的要求。

Microsoft Azure 信息保护可帮助在创建数据时对数据进行分类和添加标记。 然后可将保护（加密 + 身份验证 + 使用权）应用于敏感数据。 分类标记和保护会始终伴随数据，以便数据可识别并随时受到保护，而无需考虑其存储位置和共享对象。 计划实现信息保护策略和标签时，请使用以下指南：



- 根据机密性分类数据
- 首先分类机密性最高的数据
- IT 可以设置自动规则；用户可进行补充
- 关联可视标记和保护等操作

Azure 信息保护附带默认标签，但是可以自定义并创建用户可在信息保护栏中看到的自己的标签或子标签。

> [!NOTE]
> 标签是写入文档的元数据。 标签以明文形式呈现，以便 DLP 引擎等其他系统可以读取。

在以下示例中，可以看到在“机密”标签下创建的自定义子标签：

![屏幕截图，显示在“机密”标签下创建的自定义子标签。 ](./media/protect-data-user-mistake/protect-data-user-mistake-fig7.png)


在定义使用（默认或自定义）标签的方式后，[配置标签以应用权限管理保护](/azure/information-protection/configure-policy-protection#to-configure-a-label-to-apply-rights-management-protection)。

通过 Azure 信息保护，将数据分类和保护控件集成到 Office 和其他常见应用程序。 此集成提供简单的单击选项以保护用户处理的数据。 在 Azure 门户中，管理员可以将预定义的模式（如“信用卡号”或“美国社会保障号”）用作自动分类的条件。 或者，管理员可以使用文本模式和正则表达式来定义自定义字符串或模式。

配置标签的条件时，可以自动将标签分配到文档/电子邮件，或者也可以提示用户选择建议的标签。 有关如何执行此配置的详细信息，请阅读[如何配置 Azure 信息保护的自动和建议分类的条件](https://docs.microsoft.com/rights-management/information-protection/configure-policy-classification)。

> [!NOTE]
> 有关数据分类和保护的详细信息，请阅读[使用分类、标记和保护来保护数据](https://docs.microsoft.com/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario)。

## <a name="next-steps"></a>后续步骤

Microsoft Cloud App Security 提供了一个全面的解决方案，可用于发现、监视、控制和保护云应用程序中的活动和数据。 Cloud App Security 可帮助 IT 管理员使用 Azure 信息保护直接在 Cloud App Security 控制台中进行加密。 通过与 Azure 信息保护进行集成，现在可以根据需要对 SharePoint Online 和 One Drive for Business 中存储的文件进行一般保护。 若要详细了解 Cloud App Security 与 Azure 信息保护的集成，请参阅 [Azure 信息保护集成](https://docs.microsoft.com/cloud-app-security/azip-integration)。
