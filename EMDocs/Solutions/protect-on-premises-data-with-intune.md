---
title: "使用 Microsoft Intune 保护本地数据 | Microsoft Docs"
description: "借助企业移动性 + 安全性 (EMS)，可使员工通过使用其最喜欢的应用和设备提高工作效率，同时保护本地公司数据。"
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 02/03/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebf7be63-4ac2-4158-9772-58f15416ccb7
ms.reviewer: vlpetros
ms.suite: ems
ms.custom: active-directory
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea7cc0c6c7b8286077c0bbc4251a22d138ed8e2
ms.openlocfilehash: 98acda761b353eacb2ce861dcef2f39385691021
ms.contentlocale: zh-cn
ms.lasthandoff: 05/29/2017


---
# <a name="protect-on-premises-company-data-with-intune"></a>使用 Intune 保护本地公司数据
只使用防火墙不再能提供足够的公司安全边界。 当今，安全边界必须包括最终用户及其访问、使用和共享公司数据的方式。 无论使用智能手机、平板电脑或是笔记本电脑，信息工作者希望可在任何位置、任何设备、任何需要的时候访问资源。 为用户启用访问和保护功能对想要确保公司数据受到保护的 IT 管理员来说是个挑战。 借助企业移动性 + 安全性 (EMS)，可使员工通过使用其最喜欢的应用和设备提高工作效率，同时保护本地公司数据。 继续阅读，了解详情。

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>企业移动性 + 安全性 (EMS) 可提供什么帮助？
企业移动性 + 安全性 (EMS) 是一个不仅从设备自身本机保护公司数据，还采用身份、设备、应用和数据这四个保护层提供更多保护的综合云解决方案。 借助 EMS，员工可安全顺畅地访问公司电子邮件和文档，同时 IT 可确信公司数据受到保护。

## <a name="recommended-solution"></a>建议的解决方案
使用 Microsoft Intune，可远程配置资源访问配置文件策略，从而自动设置电子邮件帐户、访问 WiFi 或 VPN 设置等配置文件、提供确保设备只接受和安装受信任配置的证书配置文件。

除提供访问权限外，Intune 对本地 Microsoft Exchange 2010 或更高版本服务器的条件性访问可确保只有托管和合规设备才能访问公司电子邮件。 将管理扩展到设备本身之外，还可使用 Intune 的 Cisco 标识服务引擎 (ISE)（很快将推出其他合作伙伴标识服务引擎），将访问公司网络的设备限制为只有使用 Intune 注册到管理且符合公司策略的设备。 通过利用 Azure Active Directory 应用程序代理，甚至可在没有 VPN、DMZ 或本地反向代理的情况下提供对本地应用程序的安全访问。 最重要的是，所有这些无需安装或维护其他本地基础结构，无需打开通过其路由流量的公司防火墙即可完成。

以下短视频快速介绍了 EMS 的条件性访问如何提供顺畅体验，让员工从 iOS、Android 和 Windows 设备安全访问公司数据：

<iframe width="675" height="480" src="https://youtube.com/embed/fvCT7Y3nlAY" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>实现本解决方案的方式
此解决方案的其余部分分为以下各节，展示如何使用 Intune 保护 Office 365 公司数据：
- **将移动设备和 Windows 电脑注册到管理**。 本部分介绍如何使用 Intune 将设备（iOS、Android、Android for Work 和 Windows 电脑）注册到管理，以便配置对本地资源的安全访问。
- **访问和保护公司电子邮件**。 本部分介绍 Intune 如何自动为用户配置本机应用电子邮件设置，以及如何提供对本地 Exchange Server 的条件性访问。
- **提供对其他本地公司资源的访问**。 本部分介绍如何通过使用 Wi-Fi、VPN 或 Azure Active Directory 应用程序代理向员工提供对本地网络资源的安全访问。
- **使用证书来保护公司资源访问**。 本部分有助于创建和部署 PKCS #12 (.PFX) 或简单证书注册协议 (SCEP) 证书来保护对公司资源的用户访问。

## <a name="enroll-mobile-devices-and-windows-pcs-into-management"></a>将移动设备和 Windows 电脑注册到管理
使用 Intune 将设备和电脑注册到管理可确保为托管设备配置的所有策略和访问配置文件得到应用。 注册设备前，首先需要[准备 Intune 服务](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)，方法是将许可证分配给用户，设置移动设备管理机构并满足要管理的不同设备类型的各种注册要求。 此时，还应该使用支持信息和特定于公司的品牌[自定义公司门户](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal)，为用户提供受信任的注册和支持体验。

Intune 服务准备就绪后，将设备注册到管理的过程就非常直接了，但各设备类型略有不同：

-   **iOS 和 Mac 设备**。 注册 iPad、iPhone 或 Mac OS X 设备需要获取 Apple 推送通知服务 (APN) 证书。 [将 APN 证书上传到 Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) 后，用户可使用公司门户应用[注册 iOS 设备](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios)，并使用公司门户网站[注册 Mac OS X 设备](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x)。
-   **Android 设备**。 将 Intune 服务注册到 Android 设备无需任何准备工作。 用户可使用 Google Play 提供的公司门户应用[将 Android 设备注册](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune)到管理。
-   **Android for Work**。 若要为支持 Intune 所托管工作配置文件的 Android 5.0 Lollipop 及更高版本设备[设置 Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)，组织需使用 Google 注册 Android for Work，然后在 Intune 管理控制台的管理员节点中配置 Android for Work 设置。
-   **Windows Phone 和电脑**。 要让注册 Windows 设备变得轻松，应[设置注册服务器的 DNS 别名](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)。 另外，可以通过添加工作或学校帐户[注册 Windows 设备](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows)。

> [!TIP]
> 在 Azure AD (Premium) 中[启用自动注册](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)功能，用户可更轻松地注册 Windows 设备。 执行该操作时，如果用户添加工作或学校帐户来注册其个人设备，或者如果公司所拥有设备加入组织的 Azure AD，则设备将通过 Intune 自动注册到管理。

## <a name="access-and-protect-company-email"></a>访问和保护公司电子邮件
大多数员工希望通过其移动设备做的第一件事是访问公司电子邮件和文档。 他们希望设置步骤简单，不需要询问支持人员。 Microsoft Intune 让你轻松为预安装在组织所用移动设备上的本机电子邮件应用创建和部署电子邮件设置。

将 Intune 条件访问策略用于 Exchange 內部部署，可确保仅 Azure Active Directory 中注册的托管且符合策略的设备可访问公司的本地 Exchange Server 信息。

### <a name="configure-exchange-email-settings-for-native-email-apps-on-managed-devices"></a>在托管设备上为本机电子邮件应用配置 Exchange 电子邮件设置
通过创建电子邮件配置文件配置策略并将其部署到用户，可在以下设备上轻松[配置本机电子邮件应用设置](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)：

-   Windows Phone 8 及更高版本。
-   Windows 10 桌面版和移动版
-   iOS 8.0 及更高版本
-   Android、Samsung Knox 标准版 4.0 及更高版本以及 Android for Work

> [!NOTE]
> Intune 支持 Google Play 商店中的 Gmail 和 Nine Work 电子邮件应用使用 Android for Work 电子邮件配置文件配置。

### <a name="protect-access-to-your-on-premises-exchange-server"></a>保护对本地 Exchange Server 的访问
除使用 Intune 来提供用于连接到本地 Exchange 服务器的电子邮件配置设置外，还可使用 Intune 通过 Intune [本地 Exchange 连接器](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)来[控制对本地 Exchange Server](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)（2010 或更高版本）的电子邮件访问。

如果设备未注册或不符合公司策略，则用户会看到如何将设备注册到管理或如何更正阻止其访问电子邮件的合规性问题的相关信息。

> [!TIP]
> 查看这些[示例方案](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios#all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune)，了解有关如何使用 Intune 条件访问来保护公司 Exchange 电子邮件的更多想法。

可为组织中在用的以下设备类型[配置 Exchange 内部部署的条件访问策略](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune#configure-a-conditional-access-policy)：

-   Windows Phone 8.1 及更高版本
-   iOS 8.0 及更高版本
-   Android 4.0 或更高版本和 Samsung Knox 标准版 4.0
-   Android for Work（当前仅支持用于 Gmail 和 Nine Work 应用电子邮件配置文件）
-   托管的 Windows 电脑上的邮件应用

> [!NOTE]
> Intune 条件访问策略仅适用于设备上的本机电子邮件应用，但用于 Android for Work 的工作配置文件中的 Gmail 和 Nine Work 本机电子邮件应用除外。 用于 Android 和 iOS 的 Microsoft Outlook 应用当前不受支持，但计划在将来进行支持。

## <a name="provide-access-to-other-on-premises-company-resources"></a>提供对其他本地公司资源的访问
除了电子邮件，EMS 还有助于控制访问权限和保护正从外部传统公司安全边界访问的本地公司数据。 Microsoft Intune Wi-Fi、VPN 和电子邮件配置文件协同工作，以便帮助你的用户获得对完成其工作所需的文件和资源的访问权限，无论他们身在何处。 使用 Azure Active Directory 应用程序代理和条件性访问，也可实现对公司 Web 应用程序和本地托管服务的安全访问和保护。

### <a name="deploy-wi-fi-settings-to-managed-devices"></a>将 Wi-Fi 设置部署到托管设备
Intune Wi-Fi 配置策略可轻松实现[将无线网络设置部署到用户](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)。 通过这些设置，用户无需在以下任何受支持设备上手动配置 Wi-Fi 设置，就可轻松连接到公司网络：

-   Android 4.0 及更高版本、Samsung KNOX 标准版和 Android for Work<sup>1</sup>
-   iOS 8.0 及更高版本<sup>1</sup>
-   Mac OS X 10.9 及更高版本<sup>1</sup>
-   Windows 设备（Windows 8.1 及更高版本的电脑、Windows Phone 8.1 或 Windows 10 移动版及更高版本的设备）<sup>2</sup>

> <sup>1</sup>可使用内置 Intune Wi-Fi 配置策略。

> <sup>2</sup>可[导入以前导出的 Wi-Fi 设置 .xml](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune#export-or-import-a-wi-fi-configuration-profile-for-windows-devices) 配置文件。

### <a name="deploy-vpn-settings-to-managed-devices"></a>将 VPN 设置部署到托管设备
用户需远程连接到其移动设备上的公司资源时，将用到 VPN 连接。 借助 Intune，可[创建和部署 VPN 配置文件](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile)，使用户能轻松安全地访问公司网络资源，无需手动配置 VPN 服务器或身份验证方法信息。

可在以下类型的设备上为多种 [Intune 支持的 VPN 连接类型](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#vpn-connection-types)配置 VPN 设置：

-   Android 4.0 及更高版本、Samsung KNOX 标准版和 Android for Work
-   iOS 8.0 及更高版本
-   Mac OS X 10.9 及更高版本
-   Windows 设备（Windows 8.1 及更高版本的电脑、Windows Phone 8.1 和 Windows 10 移动版及更高版本的设备）

### <a name="protect-network-access"></a>保护网络访问
如同仅允许托管且合规的设备访问公司 Exchange 信息，可使用 [Cisco 标识服务引擎 (ISE)](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_00.html) 网络策略来保护对网络环境的访问。 Cisco ISE 是基于策略的网络访问控制系统，可跨支持 802.1X 有线、无线和 VPN 的企业基础结构对其进行部署。

对 Cisco ISE 托管网络的设备访问在 Cisco ISE 服务器上进行配置，而非在 Intune 管理控制台中配置设置。 只需[赋予 Cisco ISE 服务器访问 Intune 租户的权限](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-networks)，然后使用 Cisco ISE 策略将访问网络环境的设备限制为托管且合规的设备。

> [!IMPORTANT]
> 利用此种保护需要 [Cisco ISE 许可证](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_0110.html)，它不包括在 EMS 中。

也可使用 Azure AD 应用程序代理为本地托管的 Web 应用程序启用单一登录 (SSO) 和安全远程访问的条件性访问。 Azure AD 应用程序代理让用户轻松访问本地托管的 Web 应用程序，如 SharePoint 站点、Outlook Web Access 或其他 LOB Web 应用程序，而不需要使用 VPN。 连接到 Web API 以支持远程桌面网关后所托管的各种设备和应用也受到支持。

[设置 Azure Active Directory 应用程序代理](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-enable)很容易。 只需在 Azure AD（基本版或高级版）中启用该功能，然后在网络内部安装称为连接器的小型 Windows Sever 服务，再向其发布应用程序即可。 无需打开任何入站防火墙端口，也无需在 DMZ 中放入任何东西。 对其进行设置后，通过单一登录到 Azure AD 即可访问本地 Web 应用程序。 [条件访问规则](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-conditional-access)提供额外的安全防护措施，如当员工不在工作时要求进行多重身份验证或阻止其访问

## <a name="use-certificates-to-secure-company-resource-access"></a>使用证书来保护公司资源访问
当通过 VPN、Wi-Fi 或电子邮件配置文件给予用户对公司资源的访问权限时，可使用每个用户设备上安装的证书[对该访问进行保护](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)，而不是依靠简单的用户名和密码进行身份验证。

可创建和部署 **PKCS #12 (.PFX)**，或者在这些设备平台上请求身份验证证书的设备要使用的**简单证书注册协议 (SCEP)** 证书配置文件：

-   iOS 8.0 及更高版本
-   Mac OS X 10.9 及更高版本
-   Android 4.0 及更高版本和 Android for Work
-   Window 8.1 及更高版本
-   Windows Phone 8.1 及更高版本
-   Windows 10（桌面版和移动版）及更高版本

虽然需要企业证书颁发机构 (CA) 来进行公司的任何基于证书的身份验证，在使用 SCEP 或 .PFX 证书前还须满足其他先决条件，从而安全访问公司资源。

-   必须首先[配置 SCEP 证书基础结构](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep)，然后才能使用 Intune 创建和部署 SCEP 证书配置文件。 此步骤需要配置数个本地服务器，包括企业证书颁发机构 (CA)、网络设备注册服务器 (NDES) 和 Microsoft Intune 证书连接器服务器。
-   除企业证书颁发机构外，若要[使用 .PFX 证书配置文件](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx)（受信任的移动设备证书），需要 Intune 证书连接器（可在 CA 上安装）。 不需要 NDES。

> [!NOTE]
> 可以选择将 Web 应用程序代理 (WAP) 服务器与 SCEP 和 .PFX 证书一起使用，从而使设备能够通过 Internet 连接接收和续订证书。

向用户[部署证书配置文件](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)时，将在其设备上安装受信任的 CA 证书。 然后设备使用 SCEP 或 .PFX 证书配置文件为自身创建证书请求。 证书请求完成时，通过选择证书（而非用户名和密码）策略身份验证方法选项，可使用证书对 Wi-Fi、VPN 和电子邮件配置文件配置策略进行身份验证。

### <a name="learn-more"></a>了解详细信息

[开始使用企业移动性 + 安全性](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft 企业移动性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

