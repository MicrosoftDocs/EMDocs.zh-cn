---
title: "建议的安全文档策略 - Microsoft 365 企业版 | Microsoft Docs"
description: "介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。"
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: ba69fe607fef9cdf6065f6a5b586770b87c771a9
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2017
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>用于保护 SharePoint 网站和文件的策略建议
除[通用标识与访问策略建议](identity-access-policies.md)和[用于保护电子邮件的策略建议](secure-email-recommended-policies.md)外，还提供了以下建议。 要保护 SharePoint Online 文件，必须创建新策略，并修改现有策略，如下所述。

以下建议基于三种针对 SharePoint 文件不同的安全层和保护层，可以根据需求粒度应用适当的层：基线、敏感及高度管控。 有关这些建议引用的安全层和推荐客户端操作系统的详细信息，请参阅[推荐的安全策略和配置说明](microsoft-365-policies-configurations.md)。

>[!NOTE]
>在这些建议中创建的所有安装组都必须在创建时启用 Office 功能。 在 SharePoint 中保护文档时，这一点对于部署 AIP 尤为重要。
>
>![为安全组启用 Office 功能](./media/security-group.png)
>

## <a name="baseline"></a>Baseline

### <a name="medium-and-above-risk-requires-mfa"></a>中等及以上风险需要进行 MFA
对应用[用于保护电子邮件的策略建议](secure-email-recommended-policies.md)时创建的 CA 策略进行如下更改：

| Category|类型|属性|值|注意|
|:-----|:-----|:-----|:-----|:-----|
|分配|云应用|包括|选择应用：<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|选择两者|

### <a name="require-a-compliant-or-domain-joined-device"></a>需要一个兼容或已加入域的设备
要为 SharePoint Online 创建新的 Intune 条件访问策略，请使用管理员凭据登录 [Microsoft 管理门户](http://manage.microsoft.com)，并导航至“策略”>“条件访问”>“SharePoint Online 策略” >  > 。

![SharePoint Online 策略](./media/secure-docs/sharepoint-online-policy.png)

必须在 Intune 管理门户中为 SharePoint Online 设置特定的条件访问策略，即设置为需要一个兼容或已加入域的设备。
| Category|类型|属性|值|注意|
|:-----|:-----|:-----|:-----|:-----|
|应用程序访问|OneDrive for Business 和使用新式验证的其他应用|所有平台|True|已选择|
|     |     |Windows 必须满足以下要求|设备必须已加入域或必须是兼容设备|已选择（列表）|
|     |     |特定平台|False||
|     |SharePoint 和 OneDrive for Business 的浏览器访问权限 |在与 OneDrive for Business 相同的平台上阻止不符合的设备|True|Check|
|策略部署|目标组|选择此策略要面向的 Active Directory 组|     |     |
|     |     |所有用户|False|     |
|     |     |所选安全组|True|已选择|
|     |     |修改|选择包含目标用户的特定安全组。|     |
|     |被免除的组|选择要从此策略免除的 Active Directory 组(替代目标组列表的成员)|     |     |    
|     |     |无免除用户|True|已选择|
|     |     |所选安全组|False|     |

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>用于 SharePoint Online 的移动应用管理条件访问

必须在 Intune 管理门户中为 SharePoint Online 设置特定的条件访问策略，以便管理移动应用。

要管理移动应用，请使用管理员凭据登录到 Microsoft Azure 门户，然后导航到“Intune 应用保护” > “设置” > “条件访问” > “SharePoint Online”。

| Category|类型|属性|值|注意|
|:-----|:-----|:-----|:-----|:-----|
|应用访问|允许的应用|启用应用访问|允许支持 Intune 应用策略的应用|已选择（列表）- 生成 Intune 应用策略支持的应用/平台组合列表。|
|用户访问|     |受限用户组|添加用户组 - 选择包含目标用户的特定安全组。|从包含试点用户的安全组开始。|
|     |     |被免除用户组|例外安全组|     |

### <a name="apply-to"></a>应用于

完成试点项目后，应对组织中的所有用户应用这些策略。

## <a name="sensitive"></a>敏感

### <a name="low-and-above-risk-requires-mfa"></a>较低及以上风险需要进行 MFA

对应用[用于保护电子邮件的策略建议](secure-email-recommended-policies.md)时创建的 CA 策略进行如下更改：

| Category|类型|属性|值|注意|
|:-----|:-----|:-----|:-----|:-----|
|分配|云应用|包括|选择应用：<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|选择两者|

### <a name="require-a-compliant-or-domain-joined-device"></a>需要一个兼容或已加入域的设备

（请参阅基线说明）

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>用于 SharePoint Online 的移动应用管理条件访问

（请参阅基线说明）

## <a name="highly-regulated"></a>高度管控

### <a name="mfa-required"></a>需要进行 MFA

对应用[用于保护电子邮件的策略建议](secure-email-recommended-policies.md)时创建的 CA 策略进行如下更改：

| Category|类型|属性|值|注意|
|:-----|:-----|:-----|:-----|:-----|
|分配|云应用|包括|选择应用：<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|选择两者|

### <a name="require-a-compliant-or-domain-joined-device"></a>需要一个兼容或已加入域的设备
（请参阅基线说明）

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>用于 SharePoint Online 的移动应用管理条件访问
（请参阅基线说明）

## <a name="additional-configurations"></a>其他配置
除上述策略外，还必须锁定不支持新式验证的旧协议。

### <a name="lock-down-legacy-protocols"></a>锁定旧协议
条件访问策略使用新式验证保护通过浏览器流程和应用的访问，比如受支持平台列表中的 Office 2016 和应用。 对于较旧的 Office 桌面应用程序（如 Office 2010），条件访问策略不适用。

不使用新式验证的旧版应用可[使用 OneDrive 管理门户](https://support.office.com/article/Control-access-based-on-network-location-or-app-59b83701-cefd-4bf8-b4d1-d4659b60da08)进行阻止。 此外，可以使用 SharePoint 管理员 PowerShell cmdlet 来禁用 SharePoint 旧协议。 要使用 PowerShell，只需运行 [Set-SPOTenant cmdlet](https://technet.microsoft.com/library/fp161390.aspx) 并将 -LegacyAuthProtocolsEnabled 设置为 $false。  完成设置后，将禁用旧协议支持，并且将阻止使用旧客户端应用程序对 SharePoint 的所有访问。

## <a name="next-steps"></a>后续步骤
[了解有关 Microsoft 365 服务的详细信息](index.md)
