---
title: "通过 Intune 实现 BYOD | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 2/10/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d31eebe-81d2-4c6b-bfec-fbd536096dda
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4edb16e4ef00b7376af800ab542f42c0e530197
ms.openlocfilehash: 9defe28a74bc3e53f6ae5dc33b33396e47247265


---
# <a name="enable-byod-with-intune"></a>通过 Intune 实现 BYOD
在当今日益复杂的移动领域，支持数字转换为 IT 带来了全新挑战，因为它们要在致力保护公司数据的同时，还要帮助员工保持高效。 随着各组织持续迁移到云，员工们希望拥有一种跨多个设备、与客户体验相匹配的高效移动办公体验。

![复杂设备环境中的选择](..\Solutions\media\enable-byod\management-choices-with-intune.png)

> <sup>可以从以下网址下载此信息图：https://gallery.technet.microsoft.com/Infographic-Management-3644ae41。</sup>

这些设备中的部分设备由公司管理，有的可专用于某个特定用户，有的可在多个员工之间进行共享。 此外还有由员工管理的设备。 这些个人设备可能是员工在日常工作中使用的 iPhone 或电脑，或偶尔用于联机的配套设备（如女儿的 iPad 或家庭计算机）。

除了设备，人们完成工作的地点也在不断变化。 人们不再仅在传统的办公室或工作场所工作。 现代员工不仅可以在家中、咖啡馆、客户现场和路途中工作，甚至在飞机上也可以。 因此，自带设备办公 (BYOD) 程序已成为现代工作场所中司空见惯的事。 这就需要由 IT 以某种方式利用这样的优势和机会，来提高员工满意度，降低成本，同时保持对公司数据的控制。

成功的 BYOD 程序可加强控制和提高安全性，并且无需施加复杂流程或改变员工的工作方式。 出色的最终用户体验意味着，用户使用你所提供的、受保护的解决方案的可能性更高；而为完成工作，创建完全脱离你监控的解决方法的可能性更低。

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>企业移动性 + 安全性 (EMS) 可提供什么帮助？

通过 EMS，可以提供一种创建高效工作场所的功能和体验，它适用于多种工作风格，且不拘泥于地点。 无论你的员工使用 iOS、MacOS、Android 还是 Windows 设备，Microsoft Intune（作为 EMS 的一部分），都能帮助你提高员工跨设备的工作效率，同时保证公司数据安全。 Intune 提供 MAM 和 MDM 功能，允许你使用（或不使用）设备管理来保护公司数据。 除全面的移动设备和应用生命周期管理外，Intune 还直接与 Office 365 和 Office 移动应用集成。

### <a name="recommended-solution"></a>建议的解决方案

使用 Intune，可轻松地授予员工几乎可从任何设备随时随地访问公司应用程序、数据和资源的权限，同时确保了公司信息安全。 直接与 Office 365 集成实现了杰出的最终用户体验，并提供适用于 Office 移动应用的最全面数据丢失防护功能，以及对 Office 365 的访问控制。 当设备丢失、被盗或单纯的无需再用于工作时，Intune 允许你从 BYOD 设备中有选择地仅擦除公司数据。

下面是一个简短视频，聆听来自真实 IT 专业人士和实际用户的需求，以及平衡工作效率与保护移动优先、云优先环境之间的挑战：
<iframe width="675" height="480" src="https://www.youtube.com/embed/pgAmKnluwVw" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>实现本解决方案的方式

此解决方案的其余部分分为以下各节，展示如何：

-   **注册设备和检查合规性**。 本部分介绍如何让用户通过 Intune 注册设备（iOS、MacOS、Android、Android for Work 和 Windows）以进行管理，向其部署策略，并确保它们符合基本安全要求。

-   **提供对公司资源的访问**。 本部分介绍 IT 如何通过将访问配置文件部署到托管设备来使用户能够轻松、安全地访问公司资源，以及如何使用 Intune 管理批量采购的应用部署。  

-   **保护公司数据**。 本部分有助于了解如何提供对公司资源的条件访问、防止数据丢失，以及当设备上的公司应用和数据不再需要或丢失被盗时如何将其删除。

## <a name="enroll-devices-and-check-for-compliance"></a>**注册设备和检查合规性**

本部分介绍如何让用户通过 Intune 注册设备以进行管理，并确保它们符合基本安全要求。

### <a name="enable-users-to-enroll-their-personal-devices-into-management"></a>让用户注册其个人设备以进行管理

使用 Intune 将设备和电脑注册到管理可确保为托管设备配置的所有策略和访问配置文件得到应用。 注册设备前，首先需要[准备 Intune 服务](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)，方法是将许可证分配给用户，设置移动设备管理机构并满足要管理的不同设备类型的各种注册要求。 此时，还应该使用支持信息和特定于公司的品牌[自定义公司门户](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal)，为用户提供受信任的注册和支持体验。

Intune 服务准备就绪后，将设备注册到管理的过程就非常直接了，但各设备类型略有不同：

-   **iOS 和 Mac 设备**。 注册 iPad、iPhone 或 MacOS 设备需要先获取 Apple 推送通知服务 (APN) 证书。 [将 APN 证书上传到 Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) 后，用户可使用公司门户应用[注册 iOS 设备](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios)，并使用公司门户网站[注册 MacOS 设备](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x)。

-   **Android 设备**。 将 Intune 服务注册到 Android 设备无需任何准备工作。 用户可使用 Google Play 提供的公司门户应用[将 Android 设备注册](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune)到管理。

-   **Android for Work**。 若要为支持 Intune 所托管工作配置文件的 Android 5.0 Lollipop 及更高版本设备[设置 Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)，组织需使用 Google 注册 Android for Work，然后在 Intune 管理控制台的管理员节点中配置 Android for Work 设置。

-   **Windows Phone 和电脑**。 要让注册 Windows 设备变得轻松，应[设置注册服务器的 DNS 别名](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)。 另外，可以通过添加工作或学校帐户[注册 Windows 设备](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows)。

> [!TIP]
> 在 Azure AD (Premium) 中[启用自动注册](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)功能，用户可更轻松地注册 Windows 设备。 执行该操作时，如果用户添加工作或学校帐户来注册其个人设备，或者如果公司所拥有设备加入组织的 Azure AD，则设备将通过 Intune 自动注册到管理。

### <a name="make-sure-that-managed-devices-comply-with-basic-security-requirements"></a>确保托管设备符合基本安全要求

用户将设备注册到管理后，IT 需要确保用于访问公司应用和数据的设备符合基本安全要求。 这些规则可能包括使用 PIN 访问设备和加密存储在设备上的数据。 一组这样的规则就称为[合规性策略](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)。

向用户[创建和部署合规性策略](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)时，将检查所有由 Intune 管理的设备，以查看它们是否符合作为 BYOD 策略的一部分，由你所定义的基本安全要求。 在对设备进行策略合规性评估后，会将其状态报告回 Intune 服务。 在某些情况下，用户可能收到需修正不合规设置的提示，例如使用 PIN 或设备加密时，但有时公司门户应用也只向用户通知所发现的任意合规性问题。

## <a name="provide-access-to-company-resources"></a>提供对公司资源的访问

本部分介绍 IT 如何通过将访问配置文件部署到托管设备来使用户能够轻松、安全地访问公司资源，以及如何管理批量采购的应用。

### <a name="provide-access-to-company-data"></a>提供对公司数据的访问
大多数员工希望通过其移动设备做的第一件事是访问公司电子邮件和文档。 他们希望设置步骤简单，不需要询问支持人员。 Microsoft Intune 让你轻松为预安装在组织所用移动设备上的本机电子邮件应用[创建和部署电子邮件设置](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)。

> [!NOTE]
> Intune 支持 Google Play 商店中的 Gmail 和 Nine Work 电子邮件应用使用 Android for Work 电子邮件配置文件配置。

除了电子邮件，EMS 还有助于控制访问权限和保护正从外部传统公司安全边界访问的本地公司数据。 Microsoft Intune [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)、[VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) 和电子邮件配置文件协同工作，以便帮助你的用户获得对完成其工作所需的文件和资源的访问权限，无论他们身在何处。 使用 Azure Active Directory 应用程序代理和条件性访问，也可实现对公司 Web 应用程序和本地托管服务的安全访问和保护。

### <a name="manage-volume-purchased-apps"></a>管理批量采购的应用
可以轻松[将应用商店应用传递到托管设备](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)，甚至使用公司门户网站将应用定向传递至非托管设备，但 Intune 还允许你管理和部署从 iOS 应用商店和适用于企业的 Windows 应用商店批量购买的应用。 这有助于降低跟踪批量购买应用的管理成本。

> [!TIP]
> 可以轻松[使用 Azure AD Connect 配置单一登录 (SSO)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)，以便让用户可以通过其在本地使用的域用户名和密码登录应用。 此外，还可使用 Azure Active Directory 应用程序代理来[提供对本地托管的 Web 应用的基于 Internet 的访问](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)。

通过 Intune 可轻松导入来自应用商店的批量许可证信息，跟踪已使用的许可证数量，并防止用户安装的应用副本数多于你所拥有的数量。

-   [管理批量采购的适用于 iOS 设备的应用](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)。 通过 [Apple Volume Purchase Program 企业版](http://www.apple.com/business/vpp/)购买多个 iOS 应用许可证。 这涉及到从 Apple 网站设置一个 Apple VPP 帐户并将 Apple VPP 令牌上载到 Intune。 然后你可以将你的批量购买信息与 Intune 同步并追踪你的批量购买的应用的使用情况。

-   [适用于企业的 Windows 应用商店](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)。 你可以在[适用于企业的 Windows 应用商店](https://www.microsoft.com/business-store)中为你的组织查找和购买应用，可以购买单个或批量购买。 通过将此应用商店连接到 Microsoft Intune，你可以在 Intune 门户中管理批量购买的应用。

## <a name="protect-company-data"></a>保护公司数据

Intune 通过多个技术层保护公司数据。 在标识层上，条件性访问通过仅允许从托管及合规设备进行访问来保护对服务的访问。 在客户端应用程序层上，移动应用管理 (MAM) 通过防止将数据移动到不受保护的应用或存储位置以及在设备丢失或被盗时擦除数据来防止数据丢失。

### <a name="enforce-conditional-access-to-company-resources"></a>强制执行对公司资源的条件访问

可结合使用合规性策略与[条件访问策略](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)，以检查设备是否符合你的 BYOD 策略所需的基本安全要求。 如果设备不符合策略，则强制执行条件访问规则并拒绝其访问，直至将设备配置为满足策略要求。 这可确保仅托管设备和合规设备才能从 Exchange（[Exchange 内部部署](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)或 [Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)）、SharePoint Online、Skype for Business Online 等服务访问公司数据。

> [!IMPORTANT]
> 如果用于验证合规性的合规性策略未准备就绪，则无法使用条件访问策略。

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>使用应用程序保护策略防止公司数据丢失

Intune 的应用程序保护策略使你能多方面地管理访问数据的方式（无论设备注册与否）。 公司数据保护功能（无论设备注册与否），使你能够启用数据保护方案，从而安全访问公司数据，即使用户不愿意将其设备注册到管理。

可使用 [Intune 应用保护策略](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)帮助保护由用户的 iOS 和 Android 设备访问的公司数据。 通过实施这些应用级策略，可控制员工使用和共享公司数据的方式（即使该设备本身不由 Intune 管理）。

使用 [Windows 信息保护 (WIP) 策略](https://docs.microsoft.com/intune/deploy-use/microsoft-intune-policy-reference#windows-configuration-policies)对托管的 Windows 10 设备可执行相同操作。 这些策略不会影响员工体验，也无需对网络环境或其他应用进行更改。

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>在保留个人数据完整的同时，擦除公司数据

如果不再需要某设备用于办公、设备改变用途或丢失，则需要从此设备删除公司的应用和数据。 为此，可使用 Intune 的选择性擦除和完全擦除功能。 用户也可从 Intune 公司门户远程擦除注册到管理的自有设备。

可以不使用[完全擦除](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#full-wipe)将设备恢复出厂默认设置并删除用户数据和设置，而是使用[选择性擦除](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#selective-wipe)功能可以仅删除设备上的公司数据，同时保留用户个人数据完整性。

启动后，设备将立即开始选择性擦除流程，从管理中删除。 流程完成后，将删除所有公司数据，设备名称将从 Intune 管理员控制台中删除，设备管理生命周期结束。

### <a name="learn-more"></a>了解详细信息
[开始使用企业移动性 + 安全性](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft 企业移动性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Feb17_HO2-->


