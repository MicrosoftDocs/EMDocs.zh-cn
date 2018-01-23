---
title: "保护电子邮件的推荐策略 - Microsoft 365 企业版 | Microsoft Docs"
description: "介绍针对有关如何应用电子邮件策略和配置的 Microsoft 建议的策略。"
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 01/18/2018
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: c86f8f86d134d77e45ab7a59564b9f0d4821ed38
ms.sourcegitcommit: eb3521981c5dec164ce2a14b4d4d53830b5ba461
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2018
---
# <a name="policy-recommendations-for-securing-email"></a>用于保护电子邮件的策略建议

本文介绍的推荐策略有助于保护支持新式身份验证和条件访问的组织电子邮件和电子邮件客户端。 这些建议是[通用标识与访问策略建议](identity-access-policies.md)的补充。

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
创建新的条件访问策略： 

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，会看到 Azure 仪表板。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新建策略”如下方屏幕截图所示：

![基线 CA 策略](./media/secure-email/CA-EXO-policy-1.png)

下表介绍了为每个保护层表达策略所需的正确设置。

### <a name="medium-and-above-risk-requires-mfa"></a>中等及以上风险需要进行 MFA

下表介绍了要为此策略实现的条件访问策略设置。

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|分配|用户和组|包括|选择用户和组 - 选择包含目标用户的特定安全组|从包含试点用户的安全组开始。|
|||排除|例外安全组；服务帐户(应用标识)|按需临时修改的成员身份|
||云应用|包括|选择应用 - 选择 Office 365 Exchange Online||
||条件|已配置|是|根据自身环境和需求进行配置|
||登录风险|风险级别|高、中|两项全选|
|访问控制|授予|授予访问权限|True|已选择|
|||需要进行 MFA|True|Check|
|||需要兼容设备|False||
|||需要已加入域的设备|False||
|||需要所有已选控件|True|已选择|
|启用策略|||开|部署条件访问策略|

### <a name="require-a-compliant-or-domain-joined-device"></a>需要一个兼容或已加入域的设备

为 Exchange Online 创建条件访问策略：

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，会看到 Azure 仪表板。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

5. 输入策略名称，然后选择要应用策略的“用户和组”。

6. 选择“云应用”。

7. 选择“选择应用”，从“云应用”列表中选择“Office 365 Exchange Online”，然后单击“选择”。 选择 Office 365 Exchange Online 应用后，单击“完成”。

8. 从“访问控制”部分选择“授予”。

9. 选择“授予访问权限”，同时选择“要求将设备标记为符合”和“要求加入域(混合 Azure AD)”，然后选择“选择”。

10. 单击“创建”，创建 Exchange Online 条件访问策略。

    > [!NOTE]
    > 从 Azure 上的 Intune 开始，必须在 Azure Active Directory 工作负荷中创建所有条件访问策略。 Intune 从其门户提供 Azure AD 条件访问策略工作负荷的链接，以便使用。

    > [!IMPORTANT]
    > 如果需要帮助，以便将过去在 Intune 经典门户中创建的条件访问策略 Intune 迁移到 Azure 门户，请参阅[将条件访问策略从 Intune 经典门户重新分配到 Azure 门户](https://docs.microsoft.com/intune/conditional-access-intune-reassign)主题。 

### <a name="app-based-conditional-access-for-exchange-online"></a>Exchange Online 基于应用的条件性访问

可为 Azure 门户上 Intune 中的 Exchange Online 设置基于应用的条件访问策略，添加另一个安全层。 为 Exchange Online 应用基于应用的条件访问，即是要求用户使用特定应用（例如 Microsoft Outlook 应用）访问公司电子邮件。

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
下表介绍了要为较低及以上风险策略实现的条件访问策略设置。

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|分配|用户和组|包括|选择用户和组 - 选择包含目标用户的特定安全组|从包含试点用户的安全组开始|
|||排除|例外安全组；服务帐户(应用标识)|按需临时修改的成员身份|
||云应用|包括|选择应用 - 选择 Office 365 Exchange Online||
||条件|已配置|是|根据自身环境和需求进行配置|
||登录风险|已配置|是|根据自身环境和需求进行配置|
|||风险级别|低、中、高|三项全选|
|访问控制|授予|授予访问权限|True|已选择|
|||需要进行 MFA|True|Check|
|||需要兼容设备|False||
|||需要已加入域的设备|False||
|||需要所有已选控件|True|已选择|
|启用策略|||开|部署条件访问策略|

### <a name="require-a-compliant-or-domain-joined-device"></a>需要一个兼容或已加入域的设备
（请参阅基线说明）

### <a name="app-based-conditional-access-for-exchange-online"></a>Exchange Online 基于应用的条件性访问

（请参阅基线说明）

#### <a name="apply-to"></a>应用于

完成试点项目后，应对组织中需要访问机密电子邮件的用户应用这些策略。

## <a name="highly-regulated"></a>高度管控
### <a name="mfa-required"></a>需要进行 MFA

下表介绍了要为高度管控策略实现的条件访问策略设置。

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|分配|用户和组|包括|选择用户和组 - 选择包含目标用户的特定安全组|从包含试点用户的安全组开始|
|||排除|例外安全组；服务帐户(应用标识)|按需临时修改的成员身份|
||云应用|包括|选择应用 - 选择 Office 365 Exchange Online||
|访问控制|授予|授予访问权限|True|已选择|
|||需要进行 MFA|True|Check|
|||需要兼容设备|False|Check|
|||需要已加入域的设备|False||
|||需要所有已选控件|True|已选择|
|启用策略|||开|部署条件访问策略|

### <a name="require-a-compliant-or-domain-joined-device"></a>需要一个兼容或已加入域的设备
（请参阅基线说明）
### <a name="app-based-conditional-access-for-exchange-online"></a>Exchange Online 基于应用的条件性访问
（请参阅基线说明）
#### <a name="apply-to"></a>应用于
完成试点项目后，应对组织中需要访问高度管控电子邮件的用户应用这些策略。

### <a name="high-risk-users-policy"></a>高风险用户策略
为了确保在登录时对受侵害的所有高风险用户帐户强制执行密码更改，必须应用下列策略。

使用管理员凭据登录 [Microsoft Azure 门户 (http://portal.azure.com)](http://portal.azure.com/)，然后导航到“Azure AD Identity Protection”>“用户风险策略”。

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|分配|Users|包括|所有用户|已选择|
|||排除|无||
||条件|用户风险|高|已选择|
|控制|访问|允许访问|True|已选择|
||访问|需要更改密码|True|Check|
|审阅|不适用|不适用|不适用|不适用|
|强制执行策略|||开|启用强制执行策略|


## <a name="additional-configurations"></a>其他配置
除上述策略外，还必须配置本节讨论的以下移动应用程序和设备管理设置。

### <a name="intune-mobile-application-management"></a>Intune 移动应用程序管理

为了确保使用前文所述针对各安全和数据保护层的策略建议保护电子邮件，必须从 Azure 门户中创建 Intune 应用保护策略。

要创建新的应用保护策略，请使用管理员凭据登录 Microsoft Azure 门户，然后导航到“Intune 应用保护”>“应用策略”。

添加新策略 (+添加)，如以下屏幕快照所示：

![Intune 移动应用程序管理](./media/secure-email/CA-EXO-policy-2.png)

>[!NOTE]
>iOS 和 Android 的应用保护策略选项略有不同。 以下策略专用于 Android。
>

下表介绍了推荐的 Intune 应用保护策略设置：

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|**常规**|Email|名称|适用于 Android 的安全电子邮件策略|输入策略名称|
|||描述||输入描述策略的文本|
|||平台|Android|iOS 和 Android 的应用保护策略选项略有不同，此策略专用于 Android|
|**应用**|应用程序|应用|Outlook|已选择（列表）|
|**设置**|数据重定位|阻止 Android 备份|是|在 iOS 上，这会专门调用 iTunes 和 iCloud|
||||允许应用向其他应用传送数据|策略托管应用||
|||允许应用接收其他应用的数据|策略托管应用||
|||防止“另存为”|是||
|||限制使用其他应用剪切、复制和粘贴|策略托管应用||
|||限制显示在托管浏览器内的 Web 内容|否||
|||加密应用数据|是|在 iOS 上，选择选项：“锁定设备时”|
|||禁用联系人同步|否||
||访问|访问需要 PIN|是||
|||重置 PIN 前的尝试次数|3||
|||允许使用简单 PIN|否||
|||PIN 长度|6||
|||允许使用指纹而不是 PIN|是||
|||访问需要公司凭据|否||
|||阻止在已越狱或取得 root 权限的设备上运行托管应用|是||
|||在一定时间后重新检查访问要求(分钟)|30||
|||离线宽限期|720||
|||擦除应用数据之前的脱机间隔时间（天）|90||
|||阻止屏幕捕获和 Android 助手|否|在 iOS 上，此选项不可用|

完成后，请记住单击“创建”。 重复上述步骤，并将所选平台（下拉列表）替换为 iOS。 这可创建两个应用策略，因此请在创建策略后将组分配到策略，并进行部署。

- 请参阅[如何创建和分配应用保护策略](https://docs.microsoft.com/intune/app-protection-policies)，了解有关详细信息。

### <a name="intune-mobile-device-management"></a>Intune 移动设备管理
使用 Intune 凭据登录到 [Azure 门户上的 Intune](https://portal.azure.com)创建以下设备配置文件和设备合规策略。

#### <a name="ios-email-profile"></a>iOS 电子邮件配置文件
在 [Azure 门户上的 Intune](https://portal.azure.com) 中，可在“设备配置”>“配置文件”>“创建配置文件”>“平台(iOS)”>“配置文件类型(电子邮件)”创建以下设备配置文件。

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|**电子邮件配置文件**|Exchange Active Sync|主机(#)|Outlook.office365.com||
|||帐户名(#)|SecureEmailAccount|管理员选择|
|||Username|用户主体名称|已选择 - 下拉列表|
|||电子邮件地址|主 SMTP 地址|已选择 - 下拉列表|
|||身份验证方法|用户名和密码|已选择 - 下拉列表|
|||使用 S/MIME|False||
||同步设置|要同步的电子邮件的天数|两周|已选择 - 下拉列表|
|||使用 SSL|True|Check|
|||允许将消息转移到其他电子邮件帐户|False||
|||允许从第三方应用程序发送电子邮件|True||
|||同步最近使用的电子邮件地址|True|Check|

#### <a name="android-email-profile"></a>Android 电子邮件配置文件
在 [Azure 门户上的 Intune](https://portal.azure.com) 中，可在“设备配置”>“配置文件”>“创建配置文件”>“平台(Android)”>“配置文件类型(电子邮件)”创建以下设备配置文件。

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|**电子邮件配置文件**|Exchange Active Sync|主机(#)| Outlook.office365.com|
|||帐户名(#)|SecureEmailAccount|管理员选择|
|||Username|用户主体名称|已选择 - 下拉列表|
|||电子邮件地址|主 SMTP 地址|已选择 - 下拉列表|
|||身份验证方法|用户名和密码|已选择 - 下拉列表|
|||使用 S/MIME|False||
||同步设置|要同步的电子邮件的天数|两周|已选择 - 下拉列表|
|||同步计划|未配置|已选择 - 下拉列表|
|||使用 SSL|True|Check|
|||要同步的内容类型|||
|||Email|True|选中（已锁定）|
|||联系人|True|Check|
|||日历|True|Check|
|||“策略概述”|True|Check|
|||注意|True|Check|

#### <a name="android-for-work-email-profile"></a>Android for Work 电子邮件配置文件
在 [Azure 门户上的 Intune](https://portal.azure.com) 中，可在“设备配置”>“配置文件”>“创建配置文件”>“平台(Android for Work)”>“配置文件类型(电子邮件)”创建以下设备配置文件。

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|**电子邮件配置文件**|Exchange Active Sync|主机(#)| Outlook.office365.com|
|||帐户名(#)|SecureEmailAccount|管理员选择|
|||Username|用户主体名称|已选择 - 下拉列表|
|||电子邮件地址|主 SMTP 地址|已选择 - 下拉列表|
|||身份验证方法|用户名和密码|已选择 - 下拉列表|
||同步设置|要同步的电子邮件的天数|两周|已选择 - 下拉列表|
|||使用 SSL|True|Check|

#### <a name="device-compliance-policy"></a>设备符合性策略
在[Azure 门户上的 Intune](https://portal.azure.com) 中，可在“设备合规性”>“策略”>“创建策略”>“平台(iOS、Android 或其他)”>“设置”创建以下设备合规策略。

|Categories|类型|属性|值|注意|
|:---------|:---|:---------|:-----|:----|
|系统安全|密码|需要密码才可解锁移动设备(...)|是|已选择 - 下拉列表|
|||允许简单密码(...)|否|已选择 - 下拉列表|
|||最短密码长度(...)|6|已选择 - 列表|
||高级密码设置|全部|未配置||
||加密|需要对移动设备加密(...)|是|已选择 - 下拉列表|
||电子邮件配置文件|电子邮件帐户必须由 Intune 管理(iOS 8.0+)|是| 已选择 - 下拉列表|
|||选择 (#)||必须为 iOS 选择电子邮件配置策略：iOS 电子邮件策略（请参阅上面的配置策略）|
|设备运行状况|Windows 设备运行状况证明|要求设备报告为正常运行（Windows 10 桌面版和移动版及更高版本）|是||
||设备安全设置|全部|未配置||
||设备威胁防护|全部|未配置||
||破解|设备不得越狱或取得 root 权限(iOS 8.0+、Android 4.0+)|是||
|设备属性|操作系统版本|全部|未配置|||

要将上述所有策略视为已部署，这些策略必须面向用户组。 要完成此操作，可以创建策略（在“保存”上），或稍后在“策略”部分（与“添加”在同一级别）中选择“管理部署”。

## <a name="remediating-medium-or-high-risk-access-events"></a>修正中等或高级险访问事件
如果用户报告说，他们现在需要执行 MFA，而以前无需执行，支持团队可从风险角度审查其状态。  

组织内具有全局管理员或安全管理员角色的用户可使用 Azure AD Identity Protection 来查看会增加风险评分的风险事件。 如果他们标识了某些标记为可疑的事件，但经确认这些事件有效（例如休假中的员工从不熟悉的位置登录），则管理员可解析该事件，使其不会增加风险评分。

## <a name="next-steps"></a>后续步骤

[了解用于保护 SharePoint 网站和文件的策略建议](sharepoint-file-access-policies.md)
