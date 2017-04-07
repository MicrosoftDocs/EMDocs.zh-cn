---
title: "利用 Intune 管理公司拥有的设备 | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 3/08/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9e695ec-5608-43bb-bbfb-808b869b1567
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b5be7105266a7f455e1482a814929f65a130db82
ms.openlocfilehash: 6b220f4992651b5f3c107b5b958c47900515b77f
ms.lasthandoff: 03/08/2017


---

# <a name="manage-company-owned-devices-with-intune"></a>利用 Intune 管理公司拥有的设备

在现代职场中，有许多可供选择的方式可以满足员工移动性体验的期望，包括自带设备办公 (BYOD) 计划。 但是，许多组织想对能够使用哪些设备访问公司数据具有更强的控制力。 在这些情况下，公司可以实行自选设备办公 (CYOD) 策略，让 IT 为员工提供受管理的移动设备。

要成功实行 CYOD 策略，公司必须能够提供各种可供选择的设备让用户从中选择。 当组织将 CYOD 作为 BYOD 的替代方法实行时尤其如此，因为如果用户对组织为其分发的设备不满意，他们就会想办法使用自己的不受管理的设备。 通过 CYOD，IT 可以只向管理系统注册特定类型的设备，降低支持成本，并且从将设备分发给员工的那一刻就开始帮助保护公司数据。  员工可以选择他们在个人生活中已经习惯使用的移动设备，而无需采取其他步骤或呼叫技术支持来管理其设备和配置公司数据访问权限。  

## <a name="how-can-enterprise-mobility--security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？

可通过 Microsoft Intune 采用多种方法来管理组织或公司拥有的设备，这具体取决于设备的类型、其购买方式及组织需求。 也可安装公司门户应用，注册和管理公司拥有的设备，如 [BYOD 方案](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod)中所述。 可通过 Apple 提供的配置工具使用 Intune 在管理系统中直接注册公司拥有的 iOS 设备。 管理员或经理可以使用设备注册管理器注册所有设备类型。 具有 IMEI 号码的设备也可以标识并标记为公司拥有，以实现 COD 方案。

通过 EMS，可以提供一种创建高效工作场所的功能和体验，它适用于多种工作风格，且不拘泥于地点。 无论员工使用的是 iOS、MacOS、Android 还是 Windows 设备，Intune 都能帮助你提高员工跨设备的工作效率，同时保证公司数据安全。 除全面的移动设备和应用生命周期管理外，Intune 还直接与 Office 365 和 Office 移动应用集成，让你可以轻松保护公司数据。

### <a name="recommended-solution"></a>建议的解决方案

使用 Intune，可轻松地授予员工几乎可从任何设备随时随地访问公司应用程序、数据和资源的权限，同时确保了公司信息安全。 直接与 Office 365 集成实现了杰出的最终用户体验，并提供适用于 Office 移动应用的最全面数据丢失防护功能，以及对 Office 365 的访问控制。 当设备丢失、被盗或单纯的无需再用于工作时，Intune 可以从受管理设备中有选择地仅擦除公司数据。

>[!Note]
>使用本解决方案中所述的任何一种方法注册设备时，Intune 都可将该设备视为公司拥有的设备。 Intune 服务将设备识别为公司设备时，管理员控制台中该设备记录的“所有权”列会显示为“公司”。

![复杂设备环境中的选择](..\Solutions\media\enable-byod\management-choices-with-intune.png)

> <sup>可以从以下网址下载此信息图：https://gallery.technet.microsoft.com/Infographic-Management-3644ae41。</sup>

### <a name="how-to-implement-this-solution"></a>实现本解决方案的方式
此解决方案的其余部分分为以下各节，展示如何：
- **注册公司拥有的 iOS 设备**。 本部分介绍如何使用 Apple Configurator（Mac 设备上）和 Apple DEP 集成来注册公司拥有的设备。
- **注册公司拥有的 Windows 10 设备**。 本部分介绍将 Windows 10 设备加入公司的 Azure Active Directory 后，如何在管理系统中自动注册该设备。
- **使用设备注册管理器 (DEM) 帐户注册设备**。 了解 DEM 帐户如何允许 IT 部门中的某位人员在管理系统中注册超过默认数量的设备。
- **根据国际移动设备标识 (IMEI) 号码标记公司拥有的设备**。 本部分介绍另一种方式，通过导入标识公司拥有设备的 IMEI 号码，在注册时就开始管理公司拥有的设备。
- **确保管理的设备符合基本安全要求**。 本部分介绍如何确保用于访问公司应用和数据的设备符合基本安全要求。
- **提供对公司资源的访问**。 本部分介绍 IT 如何通过将访问配置文件部署到托管设备来使用户能够轻松、安全地访问公司资源，以及如何使用 Intune 管理批量采购的应用部署。
- **保护公司数据**。 本部分有助于了解如何提供对公司资源的条件访问、防止数据丢失，以及当设备上的公司应用和数据不再需要或丢失被盗时如何将其删除。

## <a name="enroll-corporate-owned-ios-devices"></a>注册企业拥有的 iOS 设备
如果 CYOD 策略中提供了iOS 设备供用户选择，则可预配置注册，使设备自用户首次打开它时就通过 Intune 管理。 针对[设置助理](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)或[直接](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)注册，Intune 支持通过 [Apple 设备注册计划 (DEP)](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) 或使用 Mac 计算机上的 Apple Configurator 工具进行注册。 还可以将注册配置文件无线部署到通过 DEP 购买的 iOS 设备。

### <a name="setup-assistant-enrollment"></a>设置助理注册
使用[适用于 iOS 设备的设置助理注册选项](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)时，设备将重置为出厂默认设置并为设备的新用户准备好最后的安装。 此方法要求管理员通过 USB 将 iOS 设备连接到运行 [Apple 配置器](http://go.microsoft.com/fwlink/?LinkId=518017) 的 Mac 计算机以预配置注册。 然后，将设备提供给运行设置助理过程的用户。 此过程使用工作或学校凭据配置该设备，并完成注册过程。

### <a name="direct-enrollment"></a>直接注册
[适用于 iOS 设备的直接注册](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)会在设备准备过程中创建 Apple Configurator 符合文件以供使用。 已注册设备没有进行出厂重置，但没有用户隶属关系。 此方法要求管理员通过 USB 将 iOS 设备连接到运行 [Apple 配置器](http://go.microsoft.com/fwlink/?LinkId=518017)的 Mac 计算机以注册设备。

### <a name="dep-enrollment"></a>DEP 注册
Microsoft Intune 可以部署注册配置文件，该配置文件以无线方式注册通过[设备注册计划 (DEP)](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) 购买的 iOS 设备。 注册包可以包括设备的设置助理选项，这样当用户在设备上运行设置助理时，就在 Intune 中注册该设备，以便提供即时管理。

>[!Important]

>用户无法注销[通过 DEP 注册的设备](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)。

## <a name="enroll-corporate-owned-windows-10-devices"></a>注册公司拥有的 Windows 10 设备
在 Azure AD (Premium) 中启用自动注册功能，使用户可以在管理系统中无缝注册 Windows 设备。 执行该操作时，如果公司拥有的设备联接了组织的 Azure AD，当用户添加工作或学校帐户来注册该设备时，设备将通过 Intune 自动注册到管理系统。

[Windows 10 Azure Active Directory 联接（Azure AD 联接）](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-overview)可以方便用户通过 Azure AD 连接到你的企业云。 他们可以从此处在 Windows 设备上访问组织的应用和资源。 自动设备注册集成意味着这些设备也由 Microsoft Intune 自动管理。

>[!Tip]

>若要从 [Microsoft Azure 门户](https://portal.azure.com)中启用 Azure AD Premium 目录中的自动 MDM 注册，请转到“Azure Active Directory” > “移动性(MDM 和 MAM)” > “Microsoft Intune”。

Azure AD 联接适用于云优先/仅限云的企业。 这些组织通常是中小规模的企业，并且没有本地 Windows Server Active Directory 域服务 (AD DS) 基础结构。 这就是说，大型组织也可以在无法进行传统域联接的设备（例如移动设备）上使用 Azure AD 联接，并且主要需要访问 Office 365 或其他 Azure AD SaaS 应用的用户也可以使用 Azure AD 联接。 使用 Intune 进行设备管理后，IT 管理员可以通过[混合 MDM](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management#what-is-hybrid-mdm-with-configuration-manager) 在 Configuration Manager 管理控制台中管理 Azure AD 联接的设备和 AD DS 加入域的设备。
用户在 Windows 10 设备上添加工作或学校帐户时，该设备将被自动标记为“公司所有”。

## <a name="enroll-devices-with-a-device-enrollment-manager-dem-account"></a>使用设备注册管理器 (DEM) 帐户注册设备
一个 Intune [设备管理注册器 (DEM) 帐户](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)可用于为组织注册大量移动设备。 创建 DEM 帐户后，可以使用该帐户注册多达 1,000 台设备。

仅可使用 DEM 帐户注册未被单个特定用户使用的设备。 这些类型的设备非常适用于销售点或实用工具应用，但是不适用于需要访问电子邮件或公司资源的用户。
- 用户无法使用 Apple 批量购买计划 (VPP) 应用，因为每个用户都需具有 Apple ID 才可管理应用。
- 如果使用 DEM 注册 iOS 设备，则无法使用 Apple Configurator 或 Apple 设备注册计划 (DEP) 注册设备。

## <a name="tag-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>根据国际移动设备标识 (IMEI) 号码标记公司拥有的设备
Microsoft Intune 让管理员可以使用 IMEI 号码导入移动设备平台的[国际移动设备标识 (IMEI) 号码](https://docs.microsoft.com/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)，以帮助标识公司拥有的移动设备。

使用特殊格式的 .CSV 文件最多可以导入 5,000 个 IMEI 号码，在 Intune 管理控制台中一次可以手动输入最多 15 台设备 IMEI 号码。 当具有 IMEI 号码的设备在 Intune 中注册后，通常当用户安装公司门户应用并完成注册过程时，设备会被标记为“公司拥有”，并在“IMEI 设备”组中显示为“已注册”。

## <a name="make-sure-that-managed-devices-comply-with-basic-security-requirements"></a>确保托管设备符合基本安全要求
注册 iOS、Android 或 Windows 10 设备时，IT 需要确保用于访问公司应用和数据的设备符合基本安全要求。 这些规则可能包括使用 PIN 访问设备和加密存储在设备上的数据。 一组这样的规则就称为[合规性策略](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)。

向用户[创建和部署符合性策略](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)时，将检查所有由 Intune 管理的设备，以查看它们是否符合 CYOD 或 BYOD 策略中由你所定义的基本安全要求。 在对设备进行策略合规性评估后，会将其状态报告回 Intune 服务。 在某些情况下，用户可能收到需修正不合规设置的提示，例如使用 PIN 或设备加密时，但有时公司门户应用也只向用户通知所发现的任意合规性问题。

## <a name="provide-access-to-company-resources"></a>提供对公司资源的访问

本部分介绍 IT 如何通过将访问配置文件部署到托管设备来使用户能够轻松、安全地访问公司资源，以及如何管理批量采购的应用。

### <a name="provide-access-to-company-data"></a>提供对公司数据的访问
大多数员工希望通过其移动设备做的第一件事是访问公司电子邮件和文档。 他们希望设置步骤简单，不需要询问支持人员。 Microsoft Intune 让你轻松为预安装在组织所用移动设备上的本机电子邮件应用[创建和部署电子邮件设置](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)。

> [!NOTE]
> Intune 支持 Google Play 商店中的 Gmail 和 Nine Work 电子邮件应用使用 Android for Work 电子邮件配置文件配置。

除了电子邮件，EMS 还有助于控制访问权限和保护正从外部传统公司安全边界访问的本地公司数据。 Microsoft Intune [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)、[VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) 和电子邮件配置文件协同工作，以便帮助你的用户获得对完成其工作所需的文件和资源的访问权限，无论他们身在何处。 使用 Azure Active Directory 应用程序代理和条件性访问，也可实现对公司 Web 应用程序和本地托管服务的安全访问和保护。

### <a name="add-apps-for-enrolled-devices"></a>为注册设备添加应用
使用 Intune 将应用添加到已注册设备很容易，但是必须使用 Intune 软件发布程序[将其添加到 Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) 后才能部署或管理该应用。 你可以使用 Intune 软件发行者来配置应用的属性，并将该应用上载到云存储空间（如果适用）。

使用 Intune 可以[将以下几种类型的应用部署到已注册设备或对其进行管理](https://docs.microsoft.com/intune/deploy-use/add-apps)：
- **软件安装程序**。 这类应用包括 Windows 软件安装程序（.exe 或 .msi）、Android 应用包 (.apk)、iOS 应用包 (.ipa)、Windows Phone 应用包（.xap、.appx 和 .appxbundle）、Windows 应用包（.appx、.appxbundle）和通过 MDM (.msi) 文件的 Windows 安装程序。 所有软件安装程序的应用类型都会上传到[云存储空间](https://docs.microsoft.com/intune/deploy-use/add-apps#cloud-storage-space)。
- **外部链接**。 这类应用部署会提供一个外部链接 (URL) 方便用户从应用商店下载应用，或者提供一个指向基于 Web 的应用的链接，该应用从 Web 浏览器中运行。 基于外部链接的应用不存储在 Intune 云存储空间中。
- **来自应用商店的托管 iOS 应用**。 你可以使用托管 iOS 应用管理和部署来自应用商店的免费 iOS 应用。 你还可使用托管 iOS 应用将移动应用管理策略与兼容的应用相关联，并在管理员控制台中查看它们的状态。 托管 iOS 应用不存储在 Intune 云存储空间中。

### <a name="manage-volume-purchased-apps"></a>管理批量采购的应用
可以轻松[将应用商店应用传递到托管设备](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)，甚至使用公司门户网站将应用定向传递至非托管设备，但 Intune 还允许你管理和部署从 iOS 应用商店和适用于企业的 Windows 应用商店批量购买的应用。 这有助于降低跟踪批量购买应用的管理成本。

> [!TIP]
> 可以轻松[使用 Azure AD Connect 配置单一登录 (SSO)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)，以便让用户可以通过其在本地使用的域用户名和密码登录应用。 此外，还可使用 Azure Active Directory 应用程序代理来[提供对本地托管的 Web 应用的基于 Internet 的访问](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)。

通过 Intune 可轻松导入来自应用商店的批量许可证信息，跟踪已使用的许可证数量，并防止用户安装的应用副本数多于你所拥有的数量。

-   [管理批量采购的适用于 iOS 设备的应用](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)。 通过 [Apple Volume Purchase Program 企业版](http://www.apple.com/business/vpp/)购买多个 iOS 应用许可证。 这涉及到从 Apple 网站设置一个 Apple VPP 帐户并将 Apple VPP 令牌上载到 Intune。 然后你可以将你的批量购买信息与 Intune 同步并追踪你的批量购买的应用的使用情况。

-   [适用于企业的 Windows 应用商店](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)。 你可以在[适用于企业的 Windows 应用商店](https://www.microsoft.com/business-store)中为你的组织查找和购买应用，可以购买单个或批量购买。 通过将此应用商店连接到 Microsoft Intune，你可以在 Intune 门户中管理批量购买的应用。

## <a name="protect-company-data"></a>保护公司数据

Intune 通过多个技术层保护公司数据。 在标识层上，条件性访问通过仅允许从托管及合规设备进行访问来保护对服务的访问。 在客户端应用程序层上，应用管理策略通过防止将数据移动到不受保护的应用或存储位置以及在设备丢失或被盗时擦除数据来防止数据丢失。

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

