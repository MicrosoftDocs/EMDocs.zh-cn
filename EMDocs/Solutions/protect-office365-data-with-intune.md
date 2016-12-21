---
title: "使用 Microsoft Intune 保护 Office 365 公司数据 | Microsoft Docs"
description: "EMS 和 Office 365 的结合造就了完全托管的移动工作效率解决方案，可为用户带来绝对标准的工作效率，为 IT 人员提供深度集成的数据控件。"
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 10/18/2016
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cc0d2e1f-9c34-4dcb-ac1f-2f355e9ebb7e
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 168d6d559aa17bbe0b8e912a53cbd384a3dc48a3
ms.openlocfilehash: 59bbc2cd3476c8632f8a72c9144eeedcdb141c42


---

# <a name="protect-office-365-company-data-with-intune"></a>使用 Intune 保护 Office 365 公司数据
大多数员工希望通过其移动设备做的第一件事是访问公司电子邮件和文档。 他们希望设置步骤简单，不需要询问支持人员。 另一方面，IT 希望确保公司数据保持安全，无需维护大型的本地基础结构。 通过企业移动性 + 安全性 (EMS)，可使员工通过使用其最喜欢的应用和设备提高工作效率，同时保护公司数据。 敬请阅读，了解详情。

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>企业移动性 + 安全性 (EMS) 可提供什么帮助？
EMS 是旨在本地保护用户用来工作的所有设备上的 Microsoft Office 电子邮件、文件和应用的唯一解决方案。 EMS 在后台简化了将安全电子邮件传递给外出员工的过程，这是通过标识、设备、应用和数据的四层保护实现的。 通过 EMS，员工可以安全无缝地访问公司电子邮件和文档，体验到 Office Mobile 应用（如 Outlook、Word、Excel、PowerPoint 和 OneDrive）熟悉的电子邮件和工作效率。

Office 365 适用于随时随地可以办公但又不愿牺牲用户体验的员工。 EMS 和 Office 365 的结合造就了完全托管的移动工作效率解决方案，可为用户带来绝对标准的工作效率，为 IT 人员提供深度集成的数据控件。

### <a name="recommended-solution"></a>建议的解决方案
通过使用 EMS 的“管理武器”Intune，可轻松地授予员工几乎可从任何设备随时随地访问公司应用程序、数据和资源的权限，同时确保了公司信息安全。 与大多数传统本地解决方案相比，Intune 不仅更简便，而且还是更现代的一种保护公司数据的经济高效方式。 通过 Intune 保护 Office 365 数据，无需安装和维护任何本地基础结构或打开公司防火墙路由流量。

以下短视频快速介绍了如何搭配使用 Intune 和 Office 365，为员工提供从 iOS、Android 和 Windows 设备安全访问公司数据的无缝体验：

<iframe width="675" height="480" src="https://www.youtube.com/embed/To9zfl6-Z6Y" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>实现本解决方案的方式
此解决方案的其余部分分为以下各节，展示如何使用 Intune 保护 Office 365 公司数据：
- **将移动设备和 Windows 电脑注册到管理**。 本部分介绍如何使用 Intune 将设备（iOS、Android、Android for Work 和 Windows 电脑）注册到管理，以便向其部署保护 Office 365 公司数据的策略。
- **安全访问 Office 365 服务**。 在本部分中，可以了解 Intune 合规性策略相关信息，以及如何管理 Exchange Online 和 SharePoint Online Office 365 服务的条件性访问。
- **保护公司数据**。 本部分演示如何将应用保护策略用于 Android 和 iOS 设备，以及如何利用 Windows 信息保护 (WIP) 策略来保护作为设备由 Intune 托管的 Windows 10 电脑上的公司应用数据。
- **有选择地擦除公司数据**。 本部分有助于了解当设备上的公司应用和数据不再需要或丢失被盗时，如何将其删除。


## <a name="enroll-mobile-devices-and-windows-pcs-into-management"></a>将移动设备和 Windows 电脑注册到管理
使用 Intune 将设备和电脑注册到管理可确保为托管设备配置的所有策略和访问配置文件得到应用。 注册设备前，首先需要[准备 Intune 服务](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)，方法是将许可证分配给用户，设置移动设备管理机构并满足要管理的不同设备类型的各种注册要求。 此时，还应该使用支持信息和特定于公司的品牌[自定义公司门户](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal)，为用户提供受信任的注册和支持体验。

Intune 服务准备就绪后，将设备注册到管理的过程就非常直接了，但各设备类型略有不同：
- **iOS 和 Mac 设备**。 注册 iPad、iPhone 或 Mac OS X 设备需要获取 Apple 推送通知服务 (APN) 证书。 [将 APN 证书上传到 Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) 后，可使用公司门户应用[注册 iOS 设备](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios)并使用公司门户网站[注册 Mac OS X 设备](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x)。
- **Android 设备**。 将 Intune 服务注册到 Android 设备无需任何准备工作。 用户可使用 Google Play 提供的公司门户应用[将 Android 设备注册](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune)到管理。
-   **Android for Work**。 若要为支持 Intune 所托管工作配置文件的 Android 5.0 Lollipop 及更高版本设备[设置 Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)，组织需使用 Google 注册 Android for Work，然后在 Intune 管理控制台的管理员节点中配置 Android for Work 设置。
- **Windows Phone 和电脑**。 要让注册 Windows 设备变得轻松，应[设置注册服务器的 DNS 别名](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)。 另外，可以通过添加工作或学校帐户[注册 Windows 设备](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows)。

> [!TIP]
> 在 Azure AD (Premium) 中[启用自动注册](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)功能，用户可更轻松地注册 Windows 设备。 执行该操作时，如果用户添加工作或学校帐户来注册其个人设备，或者如果公司所拥有设备加入组织的 Azure AD，则设备将通过 Intune 自动注册到管理。

## <a name="secure-access-to-office-365-services"></a>安全访问 Office 365 服务
用户希望使用 Office 365 移动应用时可访问所有公司电子邮件和文件，但也需要确保仅受信任的设备连接到公司资源。 为此，可使用 Intune 条件访问策略，确保员工仅从托管设备和符合策略的设备访问 Office 365 云服务。

若要使用条件访问策略，首先必须定义 [Intune 设备合规性策略](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)。 这些类型的 Intune 策略在首次注册时检查设备，以后会定期检查，以确保设备设置按预期配置。 这样就可以轻松确保仅满足安全要求的设备可访问公司资源。 可通过创建 Intune 设备合规性策略并将其部署到用户来自行定义设备合规性（例如，解锁需密码、允许或拒绝简单密码、密码最短长度、未越狱等）。

> [!IMPORTANT]
> 如果用于验证合规性的合规性策略未准备就绪，则无法使用条件访问策略。

[条件访问策略](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)可用于安全访问 Office 365 服务，例如 Dynamics CRM Online<sup>1</sup>、Exchange Online<sup>2</sup>、SharePoint Online<sup>2</sup> 和 Skype for Business Online<sup>1</sup>。 以下示例中，将为 Exchange Online 和 SharePoint Online 配置条件访问策略。  

> <sup>1</sup> 仅限 iOS 和 Android。

> <sup>2</sup> iOS、Android 和 Windows 设备。

### <a name="secure-access-to-exchange-online"></a>安全访问 Exchange Online
通过 Intune，可根据用户设置的条件访问和合规性策略保护公司的 Exchange Online 电子邮件。 例如，可[将 Exchange Online 电子邮件的访问限制](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)为不使用强密码、未越狱且未加密的设备。

以下是在已配置使用条件访问策略访问 Exchange Online 后，用户尝试使用不由 Intune 托管的设备查看其电子邮件时发生的情景：
1. 用户尝试使用其未托管的 Android 设备上的本机电子邮件应用阅读 Exchange online 公司电子邮件。 对电子邮件的访问被拒绝，因为此设备不由 Intune 托管且不符合合规性策略。
2. 用户看到的唯一的电子邮件来自 Intune 服务，告知其设备不符合公司策略，需要先注册此设备才能访问电子邮件。
3. 注册设备并评估为符合公司策略后，将恢复对公司电子邮件的完全访问权限。

![显示条件访问如何作用于 Exchange Online 的图像](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig1.png)

### <a name="secure-access-to-sharepoint-online"></a>安全访问 SharePoint Online
Intune 也可使用条件访问轻松地[安全访问 SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)文件。 就像保护对电子邮件的访问权限一样，用户需要设置启用访问权限必须满足的两个策略：确保设备遵循公司策略的设备合规性策略以及设置访问服务必须满足的条件的条件访问策略。

用户尝试使用非托管设备连接由 Intune 条件访问策略保护的 SharePoint Online 服务时，将发生以下情景：
1.  用户对 SharePoint Online 资源的访问被拒绝，并获得一条告知其加强安全性的消息以及将设备注册到 Intune 管理的链接。
2.  通过拒绝访问消息提供的链接，用户可注册设备。
3.  注册设备并评估为符合公司策略后，将恢复对公司 SharePoint Online 数据的完全访问权限。

![显示条件访问如何作用于 SharePoint Online 的图像](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig2.png)

## <a name="protect-company-data"></a>保护公司数据
你可能已知道大多数员工将移动设备同时用于个人和工作用途。 特别是现在，随着越来越多的员工自有设备用于工作，通过不受控的应用和服务（如电子邮件、社交媒体和公有云）产生的意外数据泄露风险也在不断增加。 例如，某位员工从其个人电子邮件帐户发送最新的工程图片、将产品信息复制并粘贴到推文，或将正在进行的销售报表保存到他的公有云存储。 因此，你所面临的挑战是需要在保持员工工作效率的同时防止有意和无意的公司数据泄露。

虽然通过条件访问策略可确保仅合规设备和用户可访问电子邮件，但保护电子邮件本身及其附加文件也存在问题。 如何防止内容被复制、移动、保存到其他位置或与他人分享？ Intune 通过用于 iOS 和 Android 设备的移动应用程序管理 (MAM) 策略和用于 Windows 10 电脑和移动设备的 Windows 信息保护 (WIP) 策略解决了此问题。  

### <a name="mam-for-managed-ios-and-android-mobile-devices"></a>用于托管 iOS 和 Android 移动设备的 MAM
可使用 Intune 移动应用管理 (MAM) 策略帮助保护由用户的 iOS 和 Android 设备访问的公司数据。 通过实施这些应用级策略，可控制员工使用和共享公司数据的方式。

> [!TIP]
> 只要用户分配有 Intune 许可证，就可独立于任何移动设备管理 (MDM) 解决方案使用 Intune MAM 策略。 这意味着无论是否将设备注册到 Intune 管理，都可保护公司数据，即使非 Microsoft MDM 服务管理设备也是如此。

作为管理员，可[从 Azure 管理门户配置 Intune MAM 应用策略设置](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)。 MAM 策略中包含的两种设置是“数据重定位”和“访问”设置。 数据重定位策略定义使用受保护应用中的数据的方式。 例如，可禁止“另存为”或剪切、复制、粘贴功能。 访问策略设置可决定你期望员工使用应用所需的设备安全级别。 通过这些设置，可要求使用其他应用 PIN，或阻止应用在已越狱或取得 root 权限的设备上运行。

以下屏幕截图显示使用 Intune MAM 策略保护应用的一些方法。 在此示例中，需要 PIN 才能访问应用（访问设置）以及通过拒绝将公司信息粘贴到非托管应用来保护公司数据（数据重定位设置）：

1.  首次启动托管应用（此示例中是 Yammer for iOS）时，系统提示用户创建 PIN 以访问应用。 以后每次启动应用时，用户需要输入此 PIN。
2.  用户可复制 Yammer 对话等公司数据，并将其粘贴到其他托管应用。
3.  但是，如果用户尝试将此内容粘贴到文本消息（或其他非托管应用），粘贴功能将不可用。  

![显示 MAM 策略工作原理的图像](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig3.png)

### <a name="windows-information-protection-wip-for-managed-windows-10-pcs-and-mobile-devices"></a>用于托管的 Windows 10 电脑和移动设备的 Windows 信息保护 (WIP)
Intune 的 WIP 策略有助于防止托管的 Windows 10 设备发生潜在的数据泄露。 最重要的是，这些策略不会影响员工体验，也无需对网络环境或其他应用进行更改。

以下是其工作原理：企业数据从企业源加载到托管 Windows 设备上后，或者员工将数据标记为“工作”（而不是标记为“个人”）后，这些数据将自动加密。 企业数据写入磁盘时，WIP 使用 Windows 提供的加密文件系统 (EFS) 保护数据并将其与企业标识关联。 制定 Intune WIP 策略时，请定义允许访问和修改公司数据的受信任应用的列表。 然后，AppLocker 功能在后台运行，而操作系统控制哪些应用可运行以及访问和共享公司数据的方式。 不必修改允许的应用以打开公司数据，因为这些应用包含在允许 Windows 为其授予公司数据访问权限的列表中。

> [!TIP]
> WIP 策略保护应用和公司数据时，最终用户将在设备的“开始”菜单中看到每个允许的应用名称上附加了“已托管”。 除标准应用图标外，应用快捷方式和保存的文件还会显示 WIP 公文包图标。
<img src="..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig4.png" alt="Image showing how WIP policies affect the Start Menu and files" style="width:376px;height:112x;">

通过 [WIP 配置策略设置](https://docs.microsoft.com/intune/deploy-use/microsoft-intune-policy-reference#windows-configuration-policies)，可在 Intune 管理控制台中设置不同级别的控制和审核。 数据保护级别从“无提示”（仅记录 WIP 活动）一直到“阻止”（完全阻止用户共享受保护应用的所有内容）。 “替代”是一种中间设置，允许用户将公司数据共享到不受保护的应用（带警告），但同时记录所有此类操作供以后查看。

以下是 Intune WIP 策略帮助保护托管的 Windows 10 设备上的公司数据的方式：
1.  从 Intune 管理员控制台创建新的 WIP 策略并部署到用户。
2.  在此示例中，Microsoft Word 的 AppLocker 信息用于将 Word 2016 添加到允许的应用列表，策略限制级别设置为“替代”，策略部署到用户。
3.  用户尝试将从受保护的 Word 2016 文档复制的公司数据粘贴到新建未受保护的记事本实例。 系统立即提示验证从工作到个人分类的这项更改是否在计划内，并且跟踪此操作。

![显示 WIP 策略工作原理的图像](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig5.png)

## <a name="selectively-wipe-company-data"></a>有选择地擦除公司数据
如果不再需要某设备用于办公、设备改变用途或丢失，则需要从此设备删除公司的应用和数据。 为此，可使用 Intune 的选择性擦除和完全擦除功能。 用户也可从 Intune 公司门户远程擦除注册到管理的自有设备。

可以不使用[完全擦除](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#full-wipe)将设备恢复出厂默认设置并删除用户数据和设置，而是使用[选择性擦除](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#selective-wipe)功能可以仅删除设备上的公司数据，同时保留用户个人数据完整性。

执行选择性擦除设备非常简单，只需右键单击设备名称，选择“停用/擦除”，然后选择“选择性擦除设备”：

![Intune 控制台中选择性擦除选项的图像](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig6.png)

启动后，设备将立即开始选择性擦除流程，从管理中删除。 流程完成后，将删除所有公司数据，设备名称将从 Intune 管理员控制台中删除，设备管理生命周期结束。

### <a name="learn-more"></a>了解详细信息
[开始使用企业移动性 + 安全性](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft 企业移动性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Dec16_HO2-->


