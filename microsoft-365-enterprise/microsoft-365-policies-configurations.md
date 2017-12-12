---
title: "推荐的安全策略和配置 - Microsoft 365 企业版 | Microsoft docs"
description: "介绍部署安全电子邮件、文档、应用策略及配置的相关 Microsoft 建议和核心概念。"
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 70eb0ba8a887a703ee8c723a3a4584f3bedc1e7f
ms.sourcegitcommit: 3cc06a29762d99a3649fb3cc80f9534dc6396d80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2017
---
# <a name="recommended-security-policies-and-configurations"></a>推荐的安全策略和配置

## <a name="introduction"></a>简介
尽管没有对所有客户环境都适用的单个最佳建议，但本文的最佳做法和建议介绍了 Microsoft 一般建议，让用户了解如何在 Microsoft 云中应用策略和配置，确保员工安全高效地工作。  

目标受众：这些建议适用于熟悉 [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) 和 [Microsoft 企业移动性 + 安全性](http://microsoft.com/ems)（其中包括 Azure Active Directory（标识）、Microsoft Intune（设备管理）和 Azure 信息保护（数据保护））的企业基础结构架构师和 IT 专业人员。

客户环境：推荐的策略适用于完全在 Microsoft 云内运营的企业组织，以及跨本地和 Microsoft 云部署了基础结构的客户。

假设：提供的许多建议都依赖仅企业移动性 + 安全性 (EMS) E5 订阅才提供的服务。 提出的建议假设具有完整的 EMS E5 订阅功能。

注意事项：你的组织可能受法规或其他符合性要求约束，某些特定建议可能要求应用与推荐的配置不一致的策略。  这些配置推荐以前没有提供的使用情况控件。  推荐这些控件的原因是我们认为这些控件可实现安全性与生产力之间的平衡。  

尽管我们已尽最大努力满足各种组织保护要求，但无法完全满足所有可能存在的要求，或组织所有独特的要求。 使用这些建议作为指南，了解 Microsoft 和 Secure Productive Enterprise 团队如何考虑正确应用策略。  

>[!NOTE]
>有关了解这些建议中所述的保护功能所需的核心概念的概述，请参阅 [Microsoft 365 企业版文档主页](index.md)。
>

## <a name="core-concepts"></a>核心概念
当用户在尝试完成工作时遇到不必要的阻碍，并绕过组织的安全策略时，世界上所有的安全措施都没有意义。 Azure AD 单一登录 (SSO) 尝试最大限度降低用户负担。 这样，用户可在保证工作效率的同时，任然遵循组织的访问控制策略。

### <a name="single-sign-on-authentication"></a>单一登录身份验证

下图说明了一个典型的 SSO 身份验证流：

![最终用户单一登录体验](./media/policies-configurations/authentication-flow.png)

开始身份验证时，客户端将过去获得的凭据（如用户名和密码）和/或任何 SSO 项目提交到 Azure AD。 SSO 项目可以是浏览器的会话令牌，也可以是富应用程序的刷新令牌。

在 Azure AD 中验证了凭据和/或 SSO 项目，并评估了所有适用策略后，会为资源提供程序（在上图中为 Office 365）发布一个访问令牌。 Azure AD 也会发布一个 SSO 项目作为响应的一部分，允许客户端在后续请求中实现 SSO。 客户端会存储 SSO 项目，并将访问令牌作为标识的证明提交给资源提供程序。 Office 365 在验证访问令牌并执行必要的检查后，会向客户端授予对文档的访问权限。

#### <a name="single-sign-on-sso-refresh-tokens"></a>单一登录 (SSO) 刷新令牌
可通过多种方式实现 SSO。 例如，可使用来自标识提供者的 Cookie 作为 SSO 项目，在浏览器内存储用户的单一登录状态。 以后即可使用相同的标识提供者，以无提示方式登录（不会出现任何要求提供凭据的提示）应用程序。

用户向 Azure AD 进行身份验证时，将通过用户的浏览器和 Azure AD 建立一个 SSO 会话。 SSO 令牌以 Cookie 形式表示此会话。 Azure AD 使用两种 SSO 会话令牌：持久型和非持久型。 在登录过程中，如果选中“使我保持登录状态”复选框，则浏览器将持久会话令牌存储为持久 Cookie。 非持久会话令牌存储为会话 Cookie，在浏览器关闭时被销毁。

对于可使用新式身份验证协议的可靠应用程序（例如 [OpenId Connect](http://openid.net/specs/openid-connect-core-1_0.html) 和 [OAuth 2.0](https://tools.ietf.org/html/rfc6749)），可通过将刷新令牌用作 SSO 项目来启用 SSO（前文所述的 SSO Cookie 除外）。 当应用程序请求新的访问令牌时，将向身份验证服务器提供刷新令牌。 刷新令牌包含有关对用户进行身份验证时所用身份验证方法的声明和属性。 例如，如果用户已使用多种方法（用户名和密码，以及基于手机的身份验证）成功进行了身份验证，那么刷新令牌中包含多重身份验证 (MFA) 声明。 此外，还可能有包含数据（例如 MFA 有效期）的其它声明。

刷新令牌允许客户端获取新的访问令牌，而无需进行其它交互式身份验证。 刷新令牌的生存期比访问令牌长得多，并且可通过兑换刷新令牌获取新的访问令牌和刷新令牌对。 然后可继续使用新获取的刷新令牌来获取另一组访问令牌和刷新令牌。 客户端将继续执行此 SSO 过程，直到刷新令牌最大非活动时间设置过期、刷新令牌最长时间过期，或身份验证和身份验证策略要求发生更改。 颁发原始刷新令牌期间会出现此更改。 如果发生重大用户属性更改（例如密码重置），也需要生成新的身份验证令牌。 客户端必须执行新的交互式身份验证才能继续操作。 实际上它表示 SSO 过程中发生的中断，客户端之前未遇到此中断。

#### <a name="conditional-access"></a>条件性访问
Azure AD 充当应用程序的验证服务，基于对应用于要尝试访问的资源的任何条件访问策略的评估结果，确定是否颁发访问令牌。 如果满足策略要求，则颁发访问令牌和更新的刷新令牌。 如果不满足策略要求，用户会收到有关如何满足策略要求的说明，并且/或者需要完成其他步骤，包括多重身份验证 (MFA)。 完成 MFA 后，MFA 声明会添加到生成的刷新令牌中。  

刷新令牌中的声明随时间而累积。 某些声明具有过期时间线，在该时间线后进行的身份验证检查不再考虑相关声明。 这有时会导致意外结果。 例如，如果配置了条件访问策略，来自 Extranet 位置的身份验证尝试需要完成 MFA。 在这种情况下，当从 Extranet 访问资源时，用户有时可能不会接收到预期的 MFA 提示。 出现此情况可能是因为，在离开 Intranet 不久前，用户可能执行了 MFA。 因此，其访问令牌中具有有效的 MFA 声明。 由于此 MFA 声明满足策略要求，因此 Azure AD 不会向用户提示额外的 MFA 请求。

#### <a name="token-lifetime-policy"></a>令牌生存期策略
除了令牌中的单个声明具有过期时间外，令牌自身也具有过期时间。 如前文所述，过期的令牌也是导致 SSO 体验中断的原因之一。 可使用[令牌生存期策略](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)来设置 Azure AD 颁发的令牌的生存期。 从上文可推断出，捕获定义 SSO 会话的分布图十分困难。 例如，种类繁多的应用虽然看起来是毫无关联的不同因素，但却会影响 SSO 会话的生存期。

>[!NOTE]
>Azure AD 全局管理员可控制刷新令牌的有效期和不活动时段。 有关访问令牌和声明的相关信息，请参阅文章 [Azure Active Directory 中可配置的令牌生存期](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)中所述设置。
>

#### <a name="primary-refresh-tokens"></a>主刷新令牌
到目前为止，本文讨论了 SSO 在单个客户端上下文中的工作方式，但这不足以在单个应用中体验 SSO。 如今，用户在同一套应用程序（例如 Microsoft Office）中跨多个应用程序体验交互式工作流。 用户还需要在不相关的应用程序（包括内部开发的业务线 (LOB) 应用程序）之间访问。

传统上，已加入域的 Windows 设备使用 Windows 集成身份验证 (Kerberos) 实现跨多个应用程序和资源的高水平 SSO 体验。 这些应用包括受支持的浏览器，如 Internet Explorer 或 Microsoft Edge。 Azure AD 领域有一个模拟令牌，其形式为主刷新令牌 (PRT)。 此特权令牌仅适用于选定的一组客户端实体（例如平台系统组件）。 然后，这些实体可以允许对其它客户端应用程序进行中转身份验证访问，以便它们也能提供无缝 SSO 体验。 对于使用 [iOS](https://docs.microsoft.com/azure/active-directory/develop/active-directory-sso-ios) 和 [Android](https://docs.microsoft.com/azure/active-directory/develop/active-directory-sso-android) 设备的 Office 365 用户，已通过应用身份验证中转站功能完成了额外的工作，减少了所需身份验证次数。 此功能内置于 Microsoft Authenticator 和 Intune 公司门户应用中。

>[!NOTE]
>本文所述建议假设已在用户的 iOS 或 Android 设备上部署了其中一个应用（Microsoft Authenticator 或 Intune 公司门户）。

### <a name="multi-factor-authentication"></a>多重身份验证
多重身份验证 (MFA) 可提供对身份验证使用者的高级别信任，因为该使用者提供了有关其标识的多个证明或证据。 此证明可以是预先创建的只有使用者和颁发机构知道的机密，或是预期仅使用者拥有的物理实体。 MFA 通常分阶段执行。 首先，它使用密码建立标识，然后需要一个不同（不容易遭受恶意攻击）的身份验证方法作为第二个因素，反之亦然。

不同的颁发机构对 MFA 或强身份验证的解释可能略有不同。 例如，某些颁发机构（或更具体地说，在这些颁发机构中配置策略的管理员）可能会将基于物理智能卡的身份验证解释为 MFA。 即使严格来说，智能卡身份验证是一种单级身份验证，也可能发生这种情况。

既要求使用物理智能卡，还要求输入 PIN（密码）来使用智能卡，这种组合也可被解释为 MFA。 但是，对于较繁重的身份验证方法，组织可能会选择放宽其执行频率要求。 在这种情况下，对于通常需要强身份验证的资源而言，在两次强身份验证之间执行的常规身份验证是有效的。 例如，在某些组织中，要求用户每隔几小时或几天执行一次 MFA 是可以接受的。 只要尝试访问资源的用户的物理位置保持不变，则执行 MFA 的时间间隔取决于所保护资源的敏感性。

Azure AD 和 AD FS 通过 MFA 声明来指示是否使用 MFA 来执行身份验证。 默认情况下，当使用 [Azure MFA](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud) 或 [Windows Hello 企业版](https://docs.microsoft.com/windows/access-protection/hello-for-business/hello-identity-verification)完成身份验证时，Azure AD 使用 MFA 声明来颁发令牌。 在联合方案中，Azure AD 遵循联合标识提供者（如 AD FS）发出的 MFA 声明，并将 MFA 声明留在令牌中。

## <a name="recommended-client-configurations"></a>推荐的客户端配置
本部分介绍了我们为了向用户提供最佳 SSO 体验而推荐的默认平台客户端配置，以及条件访问的技术先决条件。

### <a name="windows-devices"></a>Windows 设备
由于 Azure 旨在为本地和 Azure AD 提供尽可能流畅的 SSO 体验，因此建议使用 Windows 10（版本 1703 或更高版本）。 应将工作或学校设备配置为直接加入 Azure AD，或者当组织使用本地 AD 域加入时，这些设备应[配置为自动以无提示方式注册到 Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

对于 BYOD Windows 设备，用户可以使用“添加工作或学校帐户”。 请注意，Windows 10 上的 Chrome 浏览器用户需要[安装扩展](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)，以便获得与 Microsoft Edge/IE 相同的流畅登录体验。 此外，如果组织的 Windows 7 设备已加入域，可以安装非 Windows 10 计算机的 Microsoft Workplace Join 包以[向 Azure AD 注册设备](https://www.microsoft.com/download/details.aspx?id=53554)。

### <a name="ios-devices"></a>iOS 设备
建议在部署条件访问或 MFA 策略之前，在用户设备上安装 [Microsoft Authenticator 应用](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 至少应在系统[要求用户向 Azure AD 注册其设备](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/multi-factor-authentication-end-user-first-time)时通过添加工作或学校帐户安装该应用，或在安装 Intune 公司门户应用以便向管理系统注册设备时安装该应用。 具体取决于配置的条件访问策略。

### <a name="android-devices"></a>Android 设备
建议用户在部署条件访问策略之前，或在某些身份验证尝试期间需要时，安装 [Intune 公司门户应用](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
)和 [Microsoft Authenticator 应用](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 安装应用后，系统可能会要求用户向 Azure AD 注册或向 Intune 注册设备。 具体取决于配置的条件访问策略。

我们还建议企业拥有的设备 (COD) 使用支持 Android for Work 或 Samsung Knox 的标准化 OEM 和版本，以便通过 Intune MDM 策略管理和保护电子邮件帐户。

## <a name="security-guidelines"></a>安全指导原则
本节包含在实现后面各节中提供的任何建议时应遵循的一般安全指导原则。

### <a name="security-and-productivity-trade-offs"></a>安全性和生产力权衡
需要在安全性和工作效率之间进行权衡。 为了帮助理解这些权衡，广泛使用了安全性、功能性、可用性/易用性 (SFU) 安全性三联原则：

![安全性和生产力权衡](./media/policies-configurations/security-triad.png)

提供的建议基于下列 SFU 安全性三联原则：

* 了解受众 - 通过作业职能/安全栏实现灵活性
* 实时应用安全策略，确保其有意义

### <a name="administrators-versus-users"></a>管理员与用户
建议创建一个安全组，在其中包括具有管理帐户或有资格临时接收管理帐户权限的所有用户。 然后应使用这些安全组来定义特定于 Azure AD 和 Office 365 管理员的条件访问策略。  

提供的策略建议考虑了与帐户关联的权限。 [Office 365 管理员](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)角色明显具有更多的 Office 365 服务权限。 因此，与常规用户帐户相比，针对这些帐户的策略建议更加严格。 涉及管理员的所用策略都是指针对 Office 365 管理员帐户的建议策略。

### <a name="reduce-the-number-of-accounts-with-persistent-admin-access"></a>减少具有永久管理员访问权限的帐户数目
使用 Azure AD Privileged Identity Management 减少永久管理帐户的数目。 此外，我们建议 Office 365 管理员对常规的非管理用途使用单独的用户帐户，仅当需要完成与其工作职能关联的任务时才使用其管理帐户。

## <a name="tiers-of-security-and-protection"></a>安全和保护层
大多数组织都具有安全性和数据保护方面的特定要求。 这些要求因行业部门和组织内的工作职能而异。 例如，法律部门和 Office 365 管理员可能要求对其电子邮件通信进行额外的安全和信息保护控制，而其他业务部门用户不要求这样做。

每个行业也有自己独特的一组规定。 本文没有针对各行业部门或工作职能提供所有可能的安全选项或建议列表，而是针对以下三个不同的安全和保护层提供建议，用户可以根据自身的需求粒度来应用这些层：[基线、敏感和高度管控](https://go.microsoft.com/fwlink/p/?linkid=841656)。  

基线。 建议为保护数据、以及访问数据的标识和设备建立一个最低标准。 遵循基线建议，可提供强大的默认保护，满足许多组织的需求。

敏感。 某些客户的部分数据必须受到较高级别的保护，或者其所有数据都需要较高级别的保护。 可对 Office 365 环境中的所有或特定数据集应用增强的保护。 建议以与安全性相当的级别保护访问敏感数据的标识和设备。

高度管控。 某些组织可能有极少量数据属于高度机密、商业机密或监管数据。 Microsoft 提供多种功能，帮助组织满足相关要求，包括为标识和设备添加保护。

### <a name="default-protection-mechanism-recommendations"></a>默认保护机制建议
下表包含针对先前定义的每个安全和保护层的默认保护机制建议：

|保护机制|Baseline|敏感|高度管控|
|:-------------------|:-------|:--------|:---------------|
|强制执行 MFA|针对中级或以上登录风险|针对低级或以上登录风险|针对所有新会话|
|强制更改密码|针对高风险用户|针对高风险用户|针对高风险用户|
|强制执行 Intune 应用程序保护|是|是|是|
|强制执行 Intune 注册 (COD)|需要一个兼容或已加入域的设备|需要一个兼容或已加入域的设备|需要一个兼容或已加入域的设备|

### <a name="device-ownership"></a>设备所有权
上表反应了许多组织的一种共同趋势，即支持企业拥有的设备 (COD) 以及个人拥有的设备或自带设备办公 (BYOD) 的混合模式，这加强了移动性，解放了生产力。 Intune 应用保护策略确保电子邮件不会从 Outlook 移动应用或其他 Office 移动应用中泄露（在 COD 和 BYOD 上都是如此）。  

企业拥有的设备需要由 Intune 管理，或已加入域，以便应用额外的保护和控制。  基于数据敏感性，组织可选择禁止特定用户群体或特定应用使用 BYOD。

## <a name="next-steps"></a>后续步骤

 [部署通用身份识别和设备访问策略](identity-access-policies.md)
