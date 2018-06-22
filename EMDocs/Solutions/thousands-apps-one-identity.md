---
title: 数千个应用，一个标识
description: 本文介绍如何使用企业移动性 + 安全性，利用 Azure Active Directory 内的工具提供适用于行业内任何基于 Web 的应用的单一标识。
keywords: ''
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: ''
ms.service: active-directory
ms.technology: ''
ms.assetid: dd879a14-919e-431b-89b9-c035c83a6899
ROBOTS: ''
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: 6aca218a4607579ce97f057ca6f67b344eae7894
ms.sourcegitcommit: 573bba4fa70ce651971ec5bafd9967ebdd6bd6c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
ms.locfileid: "34474014"
---
# <a name="thousands-of-apps-one-identity"></a>数千个应用，一个标识
通过为可访问云和本地资源的服务型软件 (SaaS) 应用程序的用户提供通用标识，Azure Active Directory (Azure AD) 使用户的工作效率更高。

Azure AD 与当前许多受欢迎的 SaaS 应用程序集成，如 Box、Twitter、ServiceNow、DocuSign 和 Workday 等。 它支持单一登录 (SSO) 身份验证、标识，以及通过任何设备以安全可靠的方式对应用程序进行安全访问管理。

## <a name="how-can-enterprise-mobility--security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？
企业移动性 + 安全性 (EMS) 是一个不仅从设备自身本机保护公司数据，还采用身份、设备、应用和数据这四个保护层提供更多保护的综合云解决方案。 EMS 可帮助解决移动优先、云优先世界中的一个重大难题 - 提供适用于行业中任何基于 Web 的应用的单一标识：
- 连接云的无缝身份验证体验
- 单一登录到 1000 个预先集成的应用或自己的应用
- 对本地应用进行安全的远程访问
- 支持“提起并移动”到云


## <a name="recommended-solution"></a>建议的解决方案
Azure AD 是云标识和访问管理解决方案，它可与传统工具上的现有投资协作，使组织能够以安全高效的方式随处访问所需的任何内容。
### <a name="access-to-single-sign-on-applications"></a>访问单一登录应用程序

在单一登录之前，IT 管理员必须管理组织拥有的所有不同应用程序的用户和密码，以支持：

- 用户在使用的每个应用中输入用户名和密码
- 用户管理过多密码
- 密码重用很常见
- 撤消访问很困难

根据最新调查，63% 的已确认的数据破坏与密码强度弱、使用默认密码或密码被盗相关。

单一登录使用户只需使用单个用户帐户登录一次，就能访问进行业务所需的全部应用程序和资源。 登录之后，用户可以访问全部所需的应用程序，而无需再次进行身份验证（例如键入密码）。

Azure AD 支持三种单一登录身份验证：

- **Microsoft Azure AD 单一登录：** 此选项使用联合登录，允许用户使用 Azure AD 的用户帐户信息自动登录到第三方应用程序，例如 Salesforce。
- **密码单一登录：** 此选项使用户能够使用第三方用户帐户信息通过 Azure AD 自动登录到第三方 SaaS 应用程序。
- **现有单一登录：** 此选项支持使用 Active Directory 联合身份验证服务 (ADFS) 或其他第三方单一登录提供程序单一登录到第三方 SaaS 公司。

### <a name="how-single-sign-on-works"></a>单一登录的工作原理
Azure AD 支持使用支持任何以下标准协议的应用进行单一登录：
- SAML 2.0
- OAuth 2.0 / OpenID Connect
- WS 联合身份验证

一个应用程序配置为将 Azure AD 用作标识提供程序。 配置后，应用程序不再需要直接输入用户名/密码，而是重定向到标识提供程序进行身份验证：

![图示：Azure AD 和不同应用程序之间建立的信任关系。](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig1.png)


### <a name="do-i-still-need-azure-active-directory-federation-services-adfs"></a>是否仍需要 Azure Active Directory 联合身份验证服务 (ADFS)？
是。 ADFS 连接到 Azure AD 使用户可从加入域的计算机上进行无缝单一登录：
- 用户不会看到任何基于 Web 的登录页
- 单独的应用程序信任通过 Azure AD 进行管理

![图示：Azure Active Directory 联合身份验证服务如何连接到 Azure AD 以提供到多个应用程序的无缝单一登录。](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig2.png)

### <a name="what-if-an-app-doesnt-support-federated-single-sign-on"></a>应用不支持联合单一登录怎么办？
对于不支持 SAML/OpenID 而仅支持在 Web 窗体中输入用户名和密码的应用来说，基于密码的 SSO 是最佳解决方案。
- 启用将在 Azure AD 中定义并存储的特定于应用程序的凭据集
- 可向用户或组分配凭据以实现共享访问

### <a name="user-account-provisioning"></a>用户帐户设置
用户帐户设置是指在应用程序的本地用户配置文件存储中创建、更新和/或禁用用户帐户记录的操作。 大多数 SaaS 应用在其自己的本地用户配置文件存储中存储用户的角色和权限。

Azure AD 配置服务连接到按应用提供的 soap/rest 用户管理 API，可以添加、更新和禁用用户帐户。 它支持组同步，还可将配置文件/角色从应用导入到 Azure AD。

![图示：Azure AD 配置服务如何连接到 soap/rest 用户管理 API。](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig3.png)

### <a name="the-end-user-experience"></a>最终用户体验
应用程序访问面板是跨设备和跨浏览器的门户，可通过 iOS、Android、Mac 和 Windows 进行访问。 若要访问“访问面板”，用户可向 Azure AD 进行身份验证，然后会看到自己具有访问权限的应用程序列表，只需在其中单击一下便可启动相应的应用。 如果管理员已针对 SSO 配置应用程序，用户无需重新进行身份验证便可访问该应用程序：单一登录将自动处理身份验证。

### <a name="bring-your-own-apps"></a>可引入自己的应用
Azure AD 应用程序库包含成千上万款可添加到组织的应用，但如果找不到第三方应用程序，仍可将该应用添加为自定义应用，以供组织使用。

用户可以载入任何基于 Web 并具有基于用户名和密码的身份验证机制的应用程序，无需考虑其是否在 Azure 应用程序库中列出。

![屏幕截图，显示如何使用 Azure AD 应用程序库为组织添加应用程序。](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig4.png)

### <a name="secure-remote-access-to-on-premises-apps"></a>对本地应用进行安全的远程访问
[Azure AD 应用程序代理](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-enable/)提供用于本地托管的 Web 应用程序的单一登录 (SSO) 和安全远程访问。 其中包括 SharePoint 站点、Outlook Web Access 或任何其他 LOB Web 应用程序。 这些本地 Web 应用程序与 O365 所使用的标识和控制平台 Azure AD 集成。

然后最终用户便可以访问本地应用程序（与访问 O365 和其他与 Azure AD 集成的 SaaS 应用程序的方式相同），而无需使用 VPN 或更改网络基础结构。

## <a name="how-to-implement-this-solution"></a>实现本解决方案的方式
以下步骤介绍之前讨论的实现每个 Azure AD 功能的方法。 每个链接表示一组不同的文章，其中包含要在组织中实现的一组不同的说明/步骤：
1. [使用应用程序代理启用单一登录。](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-sso-using-kcd/)
2. [提供对本地应用程序的安全远程访问。](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-get-started/)
   - [使用 Azure AD 应用程序代理中的自定义域。](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-custom-domains/)
   - [使用应用程序代理中的声明感知应用。](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-claims-aware-apps/)
   - [为使用应用程序代理发布的应用处理条件性访问。](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-conditional-access/)
3. [将自己的应用引入 Azure AD。](https://blogs.technet.microsoft.com/enterprisemobility/2015/06/17/bring-your-own-app-with-azure-ad-self-service-saml-configuration-now-in-preview/)

## <a name="additional-resources"></a>其他资源
- **Azure.com 上的应用库**
  - https://azure.microsoft.com/marketplace/active-directory/
- **SaaS 应用程序列表**（带有集成功能）
  - https://aadappgallery.azurewebsites.net/Default.aspx?Microsoft_Integrated_Synchronization=on
- **SaaS 应用程序教程**
  - https://azure.microsoft.com/documentation/articles/active-directory-saas-tutorial-list/
