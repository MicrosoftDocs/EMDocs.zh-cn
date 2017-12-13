---
title: "标识和设备访问策略概述 - Microsoft 365 企业版 | Microsoft Docs"
description: "介绍针对有关如何应用标识和设备访问策略以及配置的 Microsoft 建议的策略。"
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 12/10/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: a25903de35ad349a09056ab24da5e00cd1a07695
ms.sourcegitcommit: 3cc06a29762d99a3649fb3cc80f9534dc6396d80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2017
---
# <a name="general-identity-and-device-access-policy-recommendations"></a>常规标识和设备访问策略建议
本文介绍了通用的建议策略，这些策略可帮助保护 Microsoft 365 企业版。 此外，还介绍了我们为了向用户提供最佳 SSO 体验而推荐的默认平台客户端配置，以及条件访问的技术先决条件。

本指南讨论如何在新预配的环境中部署推荐的策略。 通过在单独的实验室环境中设置这些策略，可以先了解和评估推荐的策略，然后再分阶段推出到预生产和生产环境。 新预配的环境可能仅限云，也可能是混合环境。  

要成功部署推荐的策略，需要在 Azure 门户进行操作，满足前面介绍的先决条件。 具体而言，需要：
* 配置命名网络，确保 Azure Identity Protection 可以正确生成风险评分
* 要求所有用户注册多重身份验证 (MFA)
* 配置密码哈希同步和自助式密码重置，以便用户能够自行重置密码

可以使 Azure AD 和 Intune 策略都面向特定用户组。 建议分阶段推出先前定义的策略。 这样，可增量验证策略和与策略相关的支持团队的性能。


## <a name="prerequisites"></a>先决条件

要实现本文档剩余部分所述的策略，组织必须满足多个先决条件：
* [配置密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。必须启用此功能，才能检测泄漏的凭据，并对它们采取措施，从而实现基于风险的条件访问。 **注意：**必须这样做，无论组织使用的是托管身份验证（如直通身份验证 (PTA)），还是联合身份验证。
* [配置命名网络](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection 收集并分析所有可用的会话数据，以生成风险评分。 建议在 Azure AD 命名网络配置中为网络指定组织的公共 IP 范围。 来自这些范围内的流量获得的风险评分较低，而来自公司外部环境的流量获得的风险评分较高。
* [要求所有用户注册多重身份验证 (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-manage-users-and-devices)。 Azure AD Identity Protection 利用 Azure MFA 来执行其他安全性验证。 建议让所有用户提前注册 Azure MFA。
* [启用已加入域的 Windows 计算机的自动注册](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件访问可确保连接到服务的设备已加入域或是兼容设备。 要在 Windows 计算机上支持此操作，必须已向 Azure AD 注册设备。  本文介绍了如何配置自动设备注册。
* **准备支持团队**。 为无法完成 MFA 的用户制定计划。 例如，将他们添加到策略排除组，或为它们注册新 MFA 信息。 在对上述任何安全敏感问题作出更改之前，请先确保实际用户正在发出请求。 请求用户的管理人员来帮助审批是一个有效的步骤。
* [配置密码写回到本地 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 当检测到高风险的帐户泄漏时，密码写回允许 Azure AD 要求用户更改其本地密码。 可使用 Azure AD Connect 通过以下两种方法之一来启用此功能。 可以在 Azure AD Connect 设置向导的可选功能屏幕中启用密码写回，也可以通过 Windows PowerShell 启用。  
* [启用新式身份验证](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)和[保护旧版终结点](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-supported-apps)。  条件访问对使用新式身份验证的移动和桌面应用程序都适用。 如果应用程序使用旧版身份验证协议，则在应用条件时，仍有可能获得访问权限。 必须知道哪些应用程序可使用条件访问规则，并了解保护其他应用程序入口点必须采取的步骤。
* 通过激活 Rights Management [启用 Azure 信息保护](https://docs.microsoft.com/information-protection/get-started/infoprotect-tutorial-step1)。 对电子邮件使用 Azure 信息保护，开始对电子邮件分类。 按照快速入门教程自定义和发布策略。  

### <a name="recommended-email-clients"></a>推荐的电子邮件客户端
下列电子邮件客户端支持新式身份验证和条件访问。 Azure 信息保护尚不对所有客户端都适用。

|平台|客户端|版本/说明|Azure 信息保护|
|:-------|:-----|:------------|:--------------------|
|**Windows**|Outlook|2016、2013 [启用新式身份验证](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)|是|
|**iOS**|Outlook|[最新版本](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|否|
|**Android**|Outlook|[最新版本](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|否|
|**macOS**|公共预览版||否|
|**Linux**|不支持||否|

要访问通过 Azure 信息保护进行保护的文档，可能还需要其他软件。 请确保使用[支持的软件和文档格式](https://docs.microsoft.com/information-protection/get-started/requirements-applications)创建和查看使用 Azure 信息保护的受保护文档。


### <a name="recommended-client-platforms-when-securing-documents"></a>保护文档时推荐使用的客户端平台
应用安全文档策略时，建议使用以下客户端。

|平台|Word/Excel/PowerPoint|OneNote|OneDrive 应用|SharePoint 应用|OneDrive 同步客户端|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|支持|支持|不适用|不适用|预览<sup>*</sup>|
|Windows 8.1|支持|支持|不适用|不适用|预览<sup>*</sup>|
|Windows 10|支持|支持|不适用|不适用|预览<sup>*</sup>|
|Windows Phone 10|不支持|不支持|支持|支持|不适用|
|Android|支持|支持|支持|支持|不适用|
|iOS|支持|支持|支持|支持|不适用|
|macOS|公共预览版|公共预览版|不适用|不适用|不支持|
|Linux|不支持|不支持|不支持|不支持|不支持|

<sup>*</sup>详细了解 [OneDrive 同步客户端预览版](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)。

> [!NOTE]
> 以下建议基于电子邮件的三个不同安全和保护层，用户可以根据自身的需求粒度来应用这些层：基线、敏感数据和高度管控。 有关这些建议引用的安全层和推荐客户端操作系统的详细信息，请参阅[推荐的安全策略和配置说明](microsoft-365-policies-configurations.md)。


## <a name="baseline"></a>Baseline
本部分介绍针对数据、标识和设备保护的基线层的建议。 这些建议可满足许多组织的默认保护需求。

>[!NOTE]
>以下各策略是相辅相成的。 每部分仅介绍每个层应用的策略。
>

### <a name="conditional-access-policy-settings"></a>条件访问策略设置

#### <a name="identity-protection"></a>标识保护
如前所述，可为用户提供单一登录 (SSO) 体验。 仅需根据[风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events)在必要时介入。  

* 要求在具有中级或以上登录风险时执行 MFA
* 要求为高风险用户进行安全密码更改

>[!IMPORTANT]
>此策略建议需要[密码同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)和[自助服务密码重置](https://docs.microsoft.com/azure/active-directory/active-directory-passwords)。
>

#### <a name="data-loss-prevention"></a>数据丢失防护
设备和应用管理策略专用于在设备丢失或被盗时防止数据丢失。 要实现此目标，请确保对数据的访问权限受 PIN 保护、设备上的数据已加密，且设备未被损害。

|策略建议|描述|
|:--------------------|:----------|
|要求用户进行电脑管理|要求用户将其 Windows 电脑加入 Active Directory 域，或使用 Microsoft Intune 或 System Center Configuration Manager 向管理系统注册其电脑。|
|通过组策略对象 (GPO) 或已加入域的电脑的 Configuration Manager 策略来应用安全设置|部署用于配置托管电脑的策略，以启用 BitLocker、防病毒软件和防火墙。|
|要求用户进行移动设备管理|用于访问电子邮件的用户设备必须由 Intune 管理，或仅允许通过受 Intune 应用保护策略保护的移动电子邮件应用（例如 Outlook Mobile）访问公司电子邮件。|
|在托管设备上应用 Intune 设备符合性策略|要为托管的公司移动设备和由 Intune 管理的电脑应用 Intune 设备符合性策略，需要：最小长度为 6 的 PIN、设备加密、正常运行的设备（没有越狱、没有取得 root 权限、通过运行状况证明），并且要求由 Lookout 或 SkyCure 等第三方 MTP 确定的设备风险级别为低（如果可用）。|
|将 Intune 应用保护策略应用于在非托管设备上运行的托管应用|要将 Intune 应用保护策略应用于在非托管个人移动设备上运行的托管应用，需要：最小长度为 6 的 PIN、设备加密以及运行正常的设备（没有越狱、没有取得 root 权限；通过运行状况证明）。|

### <a name="user-impact"></a>用户影响

对于大多数组织，必须能够设置用户需要登录 Office 365 才可访问其电子邮件的时间和状况。  

用户通常可受益于单一登录 (SSO)，但下列情形除外：
* 为 Exchange Online 请求身份验证令牌时：
  * 每当检测到中级或以上的登录风险，且用户尚未在当前会话中执行 MFA 时，系统可能会要求用户执行 MFA。  
  * 用户需要使用支持 Intune 应用保护 SDK 的电子邮件应用，或从 Intune 兼容设备或已加入 AD 域的设备访问电子邮件。
* 如果用户登录存在风险，且已成功完成 MFA，系统会要求其更改密码。

## <a name="sensitive"></a>敏感
本部分介绍针对数据、标识和设备保护的敏感层的建议。 这些建议适用于以下客户：其部分数据必须受到较高级别的保护，或者其所有数据都需要较高级别的保护。

可对 Office 365 环境中的所有或特定数据集应用增强的保护。 例如，可通过应用相关策略来确保仅在受保护的应用之间共享敏感数据，防止数据丢失。 建议以与安全性相当的级别保护访问敏感数据的标识和设备。

### <a name="conditional-access-policy-settings"></a>条件访问策略设置
#### <a name="identity-protection"></a>标识保护

如前所述，可为用户提供单一登录 (SSO) 体验。 仅需根据[风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events)在必要时介入。   

* 要求为具有低级或以上风险的会话执行 MFA
* 要求为高风险用户进行安全密码更改

>[!IMPORTANT]
>此策略建议需要[密码同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)和[自助服务密码重置](https://docs.microsoft.com/azure/active-directory/active-directory-passwords)。
>

#### <a name="data-loss-prevention"></a>数据丢失防护

这些设备和应用管理策略专用于在设备丢失或被盗时防止数据丢失。 要实现此目标，请确保对数据的访问权限受 PIN 保护、设备上的数据已加密，且设备未被损害。

|策略建议|描述|
|:--------------------|:----------|
|要求用户进行电脑管理|要求用户将其电脑加入 Active Directory 域，或使用 Intune 或 Configuration Manager 向管理系统注册其电脑，并在允许电子邮件访问前确保这些设备符合策略要求。|
|通过组策略对象 (GPO) 或已加入域的电脑的 Configuration Manager 策略来应用安全设置|部署用于配置托管电脑的策略，以启用 BitLocker、防病毒软件和防火墙。|
|要求用户进行移动设备管理|用于访问电子邮件的用户设备必须由 Intune 管理，或仅允许通过受 Intune 应用保护策略保护的移动电子邮件应用（例如 Outlook Mobile）访问公司电子邮件。|
|在托管设备上应用 Intune 设备符合性策略|要为托管的公司移动设备和由 Intune 管理的电脑应用 Intune 设备符合性策略，需要：最小长度为 6 的 PIN、设备加密、正常运行的设备（没有越狱、没有取得 root 权限、通过运行状况证明），并且要求由 Lookout 或 SkyCure 等第三方 MTP 确定的设备风险级别为低（如果可用）。|
|将 Intune 应用保护策略应用于在非托管设备上运行的托管应用|要将 Intune 应用保护策略应用于在非托管个人移动设备上运行的托管应用，需要：最小长度为 6 的 PIN、设备加密以及运行正常的设备（没有越狱、没有取得 root 权限；通过运行状况证明）。|

### <a name="user-impact"></a>用户影响
对于大多数组织，必须能够设置用户需要登录 Office 365 电子邮件的特定时间和状况。

用户通常可受益于单一登录 (SSO)，但下列情形除外：
* 为 Exchange Online 请求身份验证令牌时：
  * 每当检测到低级或以上的登录风险，且用户尚未在当前会话中执行 MFA 时，系统会要求用户执行 MFA。  
  * 用户需要使用支持 Intune 应用保护 SDK 的电子邮件应用，或从 Intune 兼容设备或已加入 AD 域的设备访问电子邮件。
* 如果用户登录存在风险，且已成功完成 MFA，系统会要求其更改密码。

## <a name="highly-regulated"></a>高度管控
本部分介绍针对数据、标识和设备保护的高度管控层的建议。 某些建议适用于有极少量数据属于高度机密、商业机密或监管数据的客户。 Microsoft 提供多种功能，帮助组织满足相关要求，包括为标识和设备添加保护。

### <a name="conditional-access-policy-settings"></a>条件访问策略设置
#### <a name="identity-protection"></a>标识保护

对于高度管控层，Microsoft 建议对所有新会话强制执行 MFA。
* 要求对所有新会话执行 MFA
* 要求为高风险用户进行安全密码更改

>[!IMPORTANT]
>此策略建议需要[密码同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)和[自助服务密码重置](https://docs.microsoft.com/azure/active-directory/active-directory-passwords)。
>

#### <a name="data-loss-prevention"></a>数据丢失防护
这些设备和应用管理策略专用于在设备丢失或被盗时防止数据丢失。 要实现此目标，请确保对数据的访问权限受 PIN 保护、设备上的数据已加密，且设备未被损害。

对于高度管控层，建议要求支持 Intune 应用保护策略的应用仅在 Intune 兼容设备或已加入域的设备上运行。

|策略建议|描述|
|:--------------------|:----------|
|要求用户进行电脑管理|要求用户将其 Windows 电脑加入 Active Directory 域，或使用 Intune 或 Configuration Manager 向管理系统注册其电脑，并在允许电子邮件访问前确保这些设备符合策略要求。|
|通过组策略对象 (GPO) 或已加入域的电脑的 Configuration Manager 策略来应用安全设置|部署用于配置托管电脑的策略，以启用 BitLocker、防病毒软件和防火墙。|
|要求用户进行移动设备管理|用于访问 Office 365 电子邮件和文件的设备必须由 Intune 管理，或仅允许通过受 Intune 应用保护策略保护的移动电子邮件应用（例如 Outlook Mobile）访问公司电子邮件。|
|在托管设备上应用 Intune 设备符合性策略|要为托管的公司移动设备和由 Intune 管理的电脑应用 Intune 设备符合性策略，需要：最小长度为 6 的 PIN、设备加密、正常运行的设备（没有越狱、没有取得 root 权限、通过运行状况证明），并且要求由 Lookout 或 SkyCure 等第三方 MTP 确定的设备风险级别为低（如果可用）。|

### <a name="user-impact"></a>用户影响
对于大多数组织，必须能够设置用户需要登录 Office 365 文件的特定时间和状况。

* 会话过期后，配置为高度监管的用户需要通过 MFA 重新进行身份验证。
* 如果用户登录存在风险，则在完成 MFA 后，系统会要求其更改密码。
* 为 Exchange Online 请求身份验证令牌时：
  * 无论何时开始新会话，系统都会要求用户执行 MFA。  
  * 用户需要使用支持 Intune 应用保护 SDK 的电子邮件应用
  * 用户需要从 Intune 兼容设备或已加入 AD 域的设备访问电子邮件。

## <a name="next-steps"></a>后续步骤

[了解有关用于保护电子邮件的策略建议](secure-email-recommended-policies.md)
