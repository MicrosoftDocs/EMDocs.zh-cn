---
title: 由云支持的保护
description: 本文介绍如何通过利用 Azure Active Directory 中的工具，使用企业移动性 + 安全性提供一组全面的安全工具，帮助在组织中主动识别安全威胁并作出响应。
keywords: ''
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/24/2016
ms.topic: conceptual
ms.prod: ''
ms.service: active-directory
ms.assetid: 46654ab0-0d0a-47ad-8715-b149a1092a37
ROBOTS: ''
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: 91234f0b3c3323cafafe29481db88cd2a2884a5b
ms.sourcegitcommit: c63d47c411504fb84651c43bb6851d9692450067
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "68937404"
---
# <a name="cloud-powered-protection"></a>由云支持的保护
Microsoft 保护基于云的标识已超过十年，借助 Azure Active directory，Microsoft 向企业客户提供相同的保护系统，以确保用户和管理员能通过更高的安全性和更好的管理履行各自的职责。

## <a name="how-can-enterprise-mobility--security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？
企业移动性 + 安全性 (EMS) 是一个不仅从设备自身本机保护公司数据，还采用身份、设备、应用和数据这四个保护层提供更多保护的综合云解决方案。 EMS 可帮助解决移动优先、云优先世界中的一个重大难题 - 如何提供一组全面的安全工具，以帮助在组织中主动识别安全威胁并做出响应：
- 控制对资源的访问
- 保护用户身份验证
- 使用基于风险的策略和监视对高级威胁做出响应
- 降低管理风险
- 管理本地和云标识

Azure Active Directory 标识保护是独一无二的。 它使用计算机学习每天分析超过 10 TB 的行为和上下文数据，使用户能够发现可疑活动，并在必要时立即采取行动。

此外，Azure AD 条件性访问规则允许客户基于属性（如设备合规性或网络位置）控制对联机服务的访问。 可能会有以下区分：
- Azure AD 基于 MFA 的条件性访问
- Azure AD 基于位置的条件性访问
- Azure AD 基于设备的条件性访问


## <a name="recommended-solution"></a>建议的解决方案
### <a name="azure-active-directory-identity-protection"></a>Azure Active Directory 标识保护

Azure AD 标识保护是一种安全服务，可让用户对影响组织标识的风险事件和潜在漏洞有一个综合全面的了解：
- 使用基于风险的策略和监视对高级威胁做出响应（Azure AD 标识保护）
- 降低管理风险（特权标识）
- 标识管理

在标识盗窃事件不断增加、不良参与方持续涌现和安全漏洞频繁出现的当今世界，Azure Active Directory 标识保护必不可少。

Azure AD 标识保护仪表板支持访问报表，以了解用户标记的风险、风险事件和漏洞。 它还提供一些设置，如安全策略、通知和多重身份验证注册的配置。
### <a name="azure-ad-conditional-access"></a>Azure AD 条件访问
随着移动到云服务和对移动性需求的不断增加，组织开始寻找既能保护数据又能提高用户效率和设备灵活性的解决方案。 客户需要能够根据不同属性（如网络位置或 MFA 强制）来控制对 Office 365 的访问。 这对监管客户（如政府）或金融类客户尤为重要。

在网络外围保护数据已不足以满足要求，组织还需要能够根据其他因素（如设备合规性）控制用户的访问。

Azure AD 条件性访问规则按应用程序进行应用，并且可供客户基于不同条件控制访问。 客户使用适用于 Office 365 或 Intune 的移动设备管理 (MDM) 时，对 Office 365 的访问必须仅限于使用公司设备或已注册个人设备进行管理的用户。

例如，客户可以配置条件性访问规则，以强制进行控制，如：
- 仅允许已加入域和合规的设备进行访问
- 对所有 Exchange Online 服务访问强制实施 MFA
- 阻止企业网络外部的客户端访问 SharePoint Online。

## <a name="how-to-implement-these-solutions"></a>如何实现这些解决方案？

接下来讨论开始使用 Azure AD 标识保护和条件性访问时的必要步骤。 本部分还提供操作指南文章，这些文章介绍特定步骤的详细信息。

### <a name="azure-ad-identity-protection"></a>Azure AD 标识保护
Azure AD 高级版 2 产品中提供 Azure AD 标识保护，可与 Azure AD Privileged Identity Management 结合使用，以提供无缝条件性访问策略功能。

可通过转到 Azure 市场，并搜索“标识保护”，来启用 Azure AD 标识保护，然后可单击“Azure AD 标识保护”磁贴，随即将会打开仪表板，显示租户风险数据的综合视图。 接下来重点了解几个关于 标识保护如何帮助组织应对帐户安全威胁的示例。

#### <a name="risk-events"></a>风险事件
风险事件是指由 标识保护标记为可疑的事件，表示标识可能已泄露。

Microsoft 仍在继续对这一领域进行投入，并计划持续改进当前风险事件的检测准确性，并在现有基础上增加新的风险事件类型。 例如，使用户能调查“无法实现的行程”风险事件。

有关详细信息，请参阅 [Azure AD Identity 操作手册](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-playbook/)。

下面是 标识保护仪表板上几个风险事件的示例：

![屏幕截图：显示 Azure AD 标识保护仪表板上列出的一些风险事件。](./media/cloud-powered-protection/cloud-powered-protection-fig1.png)

#### <a name="impossible-travels-risk"></a>“无法实现的行程”风险
在“无法实现的行程”边栏选项卡内，第一个和第二个登录位置会显示标记的所有事件和每次登录的时间。

![屏幕截图：Azure AD 标识保护仪表板显示“无法实现的行程”风险事件的位置。](./media/cloud-powered-protection/cloud-powered-protection-fig2.png)

有关详细信息，请参阅 [Azure Active Directory 标识保护检测到的风险事件类型](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/)。

#### <a name="remediation"></a>修正
除了基于单个事件的寻址事件外，Azure AD 标识保护支持通过配置用户风险修正策略这一主动方法来解决潜在的问题。 在策略设置中，可以将单个用户、群组或所有用户作为目标。 还可以设置触发此策略的特定条件。

![屏幕截图：显示如何直接从 Azure AD 标识保护仪表板修正风险事件。](./media/cloud-powered-protection/cloud-powered-protection-fig3.png)

最后，可以选择完全阻止访问或允许接受以下操作的访问：
- 多重身份验证
- Azure MFA 注册
- 更改密码

有关详细信息，请参阅 [Azure AD 标识保护](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/) 和此[企业移动性和安全性博客文章](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/07/azuread-identity-protection-azure-ad-privileged-identity-management-and-azure-ad-premium-p2-will-be-generally-available-sept-15th/)。

### <a name="azure-ad-conditional-access"></a>Azure AD 条件访问
下面的链接提供基于多重身份验证 (MFA)、位置和设备策略使用 Azure AD 条件性访问的信息。
- 了解[如何实现 Azure AD 条件性访问](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access/)。
- 详细了解 [MFA 和位置策略](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-azuread-connected-apps/)。
- 详细了解[基于设备的策略](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/)。
