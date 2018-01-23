---
title: "建议的安全文档策略 - Microsoft 365 企业版 | Microsoft Docs"
description: "介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。"
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 01/18/2018
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 3eabab5a19c99fe97d56ed3d802c026c0b0bc6ef
ms.sourcegitcommit: eb3521981c5dec164ce2a14b4d4d53830b5ba461
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2018
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>用于保护 SharePoint 网站和文件的策略建议
除[通用标识与访问策略建议](identity-access-policies.md)和[用于保护电子邮件的策略建议](secure-email-recommended-policies.md)外，还提供了以下建议。 要保护 SharePoint Online 文件，必须创建新策略，并修改现有策略，如下所述。

以下建议基于电子邮件的三个不同安全和保护层，用户可以根据自身的需求粒度来应用这些层：

- **基线**：Microsoft 建议为保护数据、以及访问数据的标识和设备建立一个最低标准。 Microsoft 提供了强劲的默认防护，以满足许多组织的需求。 某些组织需要额外功能以满足其基线要求。
- **敏感**：某些客户具有必须在较高级别进行保护的数据子集。 可对 Office 365 环境中的特定数据集应用增强的保护。 Microsoft 建议以与安全性相当的级别保护访问敏感数据的标识和设备。 
- **高度管控**：某些组织可能有极少量数据属于高度机密、商业机密或监管数据。 Microsoft 提供多种功能，帮助组织满足相关要求，包括为标识和设备添加保护。

请参阅[建议的安全策略和配置简介](microsoft-365-policies-configurations.md)主题，了解更多详细信息。

> [!IMPORTANT]
> 在这些建议中创建的所有安装组都必须在创建时启用 Office 功能。 在 SharePoint Online 中保护文档时，这一点对于部署 Azure 信息保护 (AIP) 尤为重要。
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

为 Exchange Online 创建条件访问策略：

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，会看到 Azure 仪表板。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

5. 输入策略名称，然后选择要应用策略的“用户和组”。

6. 选择“云应用”。

7. 选择“选择应用”，从“云应用”列表中选择“Office 365 SharePoint Online”，然后单击“选择”。 选择 Office 365 SharePoint Online 应用后，单击“完成”。

8. 从“访问控制”部分选择“授予”。

9. 选择“授予访问权限”，同时选择“要求将设备标记为符合”和“要求加入域(混合 Azure AD)”，然后选择“选择”。

10. 单击“创建”，创建 Exchange Online 条件访问策略。

    > [!NOTE]
    > 从 Azure 上的 Intune 开始，必须在 Azure Active Directory 工作负荷中创建所有条件访问策略。 Intune 从其门户提供 Azure AD 条件访问策略工作负荷的链接，以便使用。

    > [!IMPORTANT]
    > 如果需要帮助，以便将过去在 Intune 经典门户中创建的条件访问策略 Intune 迁移到 Azure 门户，请参阅[将条件访问策略从 Intune 经典门户重新分配到 Azure 门户](https://docs.microsoft.com/intune/conditional-access-intune-reassign)主题。 

### <a name="app-based-conditional-access-for-sharepoint-online"></a>SharePoint Online 基于应用的条件性访问

可为 Azure 门户上 Intune 中的 SharePoint Online 设置基于应用的条件访问策略，添加另一个安全层。 为 SharePoint Online 应用基于应用的条件访问，即是要求用户仅使用此应用访问公司资源。

添加基于应用的条件访问策略

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用 Intune 凭据登录。 成功登录后，会看到 Azure 仪表板。

2. 从左侧菜单中选择“更多服务”，然后键入“Intune”。

3. 选择“Intune 应用保护”。

4. 在“Intune 移动应用程序管理”边栏选项卡中，选择“全部设置”。

5. 在“条件访问”部分之下，选择“Exchange Online”。

6. 选择“允许使用支持 Intune 应用策略的应用”，然后选择应用（例如 Microsoft Outlook）。

7. 选择“受限制的用户组”，单击“选择组”，选择要应用策略的用户或组，然后单击“选择”。

## <a name="sensitive"></a>敏感

### <a name="low-and-above-risk-requires-mfa"></a>较低及以上风险需要进行 MFA

对应用[用于保护电子邮件的策略建议](secure-email-recommended-policies.md)时创建的 CA 策略进行如下更改：

| Category|类型|属性|值|注意|
|:-----|:-----|:-----|:-----|:-----|
|分配|云应用|包括|选择应用：<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|选择两者|

### <a name="require-a-compliant-or-domain-joined-device"></a>需要一个兼容或已加入域的设备

（请参阅基线说明）

### <a name="app-based-conditional-access-for-sharepoint-online"></a>SharePoint Online 基于应用的条件性访问

（请参阅基线说明）

## <a name="highly-regulated"></a>高度管控

### <a name="mfa-required"></a>需要进行 MFA

对应用[用于保护电子邮件的策略建议](secure-email-recommended-policies.md)时创建的 CA 策略进行如下更改：

| Category|类型|属性|值|注意|
|:-----|:-----|:-----|:-----|:-----|
|分配|云应用|包括|选择应用：<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|选择两者|

### <a name="require-a-compliant-or-domain-joined-device"></a>需要一个兼容或已加入域的设备
（请参阅基线说明）

### <a name="app-based-conditional-access-for-sharepoint-online"></a>SharePoint Online 基于应用的条件性访问
（请参阅基线说明）

## <a name="additional-configurations"></a>其他配置
除上述策略外，还必须锁定不支持新式验证的旧协议。

### <a name="lock-down-legacy-protocols"></a>锁定旧协议
条件访问策略使用新式验证保护通过浏览器流程和应用的访问，比如受支持平台列表中的 Office 2016 和应用。 对于较旧的 Office 桌面应用程序（如 Office 2010），条件访问策略不适用。

不使用新式验证的旧版应用可[使用 OneDrive 管理门户](https://support.office.com/article/Control-access-based-on-network-location-or-app-59b83701-cefd-4bf8-b4d1-d4659b60da08)进行阻止。 此外，可以使用 SharePoint 管理员 PowerShell cmdlet 来禁用 SharePoint 旧协议。 要使用 PowerShell，只需运行 [Set-SPOTenant cmdlet](https://technet.microsoft.com/library/fp161390.aspx) 并将 -LegacyAuthProtocolsEnabled 设置为 $false。  完成设置后，将禁用旧协议支持，并且将阻止使用旧客户端应用程序对 SharePoint 的所有访问。

## <a name="next-steps"></a>后续步骤
[了解有关 Microsoft 365 服务的详细信息](index.md)
