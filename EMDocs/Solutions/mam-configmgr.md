---
title: "正在使用 Configuration Manager 中的移动应用程序管理策略"
description: 
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 74288276-84d3-4d24-8307-7875491be9c9
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 276a4ee6ceab6b39b9add2ea844cdf03f142a253
ms.openlocfilehash: 48f0f43b925090aec2cf0585b1372f5c27d1bd5b


---

# 使用 Configuration Manager 中的移动应用程序管理策略
从 System Center 2012 Configuration Manager SP2 开始，应用程序管理策略可以修改部署的应用的功能，以使其符合公司的合规性策略和安全策略。 例如，您可以限制在受限制的应用内进行剪切、复制和粘贴操作，或配置应用以打开托管浏览器内的所有 Web 链接。 应用管理策略支持：

- 运行 Android 4 和更高版本的设备。
- 运行 iOS 7 和更高版本的设备。

> [!TIP]
> 除了托管设备，移动应用管理策略还可用于保护不由 Intune 管理的设备上的应用。 你可以使用这项新功能，为连接到 Office 365 服务的应用应用移动应用管理策略。 连接到内部部署 Exchange 或 SharePoint 的应用不支持此操作。
若要使用这项新功能，必须使用 Azure 门户。 下列主题可帮你入门：
- [准备好使用 Microsoft Intune 配置移动应用管理策略](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
- [使用 Microsoft Intune 创建和部署移动应用管理策略](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

与 Configuration Manager 中的配置项目和基线不同，你不会直接部署应用程序管理策略。 而是将该策略与你想要进行限制的应用部署类型 (DT) 关联。 在设备上部署并安装了应用 DT 后，你指定的设置将生效。

若要将限制应用到应用上，该应用必须包含 Microsoft Intune 应用软件开发工具包 (SDK)。 有两种方式获得此类应用：

- **使用策略托管应用**（Android 和 iOS）：内置应用 SDK。 要添加此类型的应用，你可以从 iTunes 应用商店或 Google Play 等应用商店指定应用的链接。 对于此类应用，无需进一步的处理。 有关可用于 iOS 和 Android 设备的策略托管应用的列表，请参阅 [Microsoft Intune移动应用程序库](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)。
- **使用“已包装的”应用**（Android 和 iOS）：使用 Microsoft Intune 应用包装工具重新进行封装以将应用 SDK 包括在内的应用。 该工具通常用于处理公司内部开发的应用。 它可用于处理从应用商店下载的应用。 请参阅[使用 Microsoft Intune 应用包装工具为移动应用程序管理准备 iOS 应用](https://docs.microsoft.com/en-us/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)和[使用 Microsoft Intune 应用包装工具为移动应用程序管理准备 Android 应用](https://docs.microsoft.com/en-us/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)。

## 创建和部署具有移动应用程序管理策略的应用

- 步骤 1：获取指向策略托管应用的链接，或创建已包装的应用。
- 步骤 2：创建包含应用的 Configuration Manager 应用程序。
- 步骤 3：创建移动应用程序管理策略。
- 步骤 4：将应用程序管理策略与部署类型相关联。
- 步骤 5：监视应用部署。

### 步骤 1：获取指向策略托管应用的链接，或创建包装的应用。
- **获取策略托管应用的链接** - 从应用商店查找并记录你想要部署的策略托管应用的 URL。
例如，Microsoft Word for iPad 应用的 URL 是 [https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8](https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8)
- **创建已包装的应用** - 使用主题[通过 Microsoft Intune 应用包装工具为移动应用程序管理准备 iOS 应用](https://docs.microsoft.com/en-us/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)和[通过 Microsoft Intune 应用包装工具为移动应用程序管理准备 Android 应用](https://docs.microsoft.com/en-us/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)中的信息创建已包装的应用。 创建处理过的应用和关联的清单文件的工具。 在创建包含该应用的 Configuration Manager 应用程序时，将使用这些文件。

### 步骤 2：创建包含应用的 Configuration Manager 应用程序。
创建 Configuration Manager 应用程序的过程有所不同，具体取决于使用的是策略托管应用（外部链接）还是通过适用于 iOS 的 Microsoft Intune 应用包装工具（iOS 应用包）创建的应用。

有关创建包含应用的 Configuration Manager 应用程序所需的完整步骤，请参阅[如何在 Configuration Manager 中使用移动应用程序管理策略控制应用](https://technet.microsoft.com/en-us/library/mt131414.aspx?f=255&MSPPError=-2147217396#BKMK_Step2)。

创建应用程序后，它会显示在“软件库”工作区“应用程序”节点中。

### 步骤 3：创建移动应用程序管理策略。
接下来，你将[创建一个应用程序管理策略](https://technet.microsoft.com/en-us/library/mt131414.aspx?f=255&MSPPError=-2147217396#bkmk_step3)，该策略将与该应用程序关联。 可以创建一个常规或托管浏览器策略。

新建策略后，它会显示在“软件库”工作区“应用程序管理策略”节点中。

### 步骤 4：将应用程序管理策略与部署类型相关联。
在为某个需要应用程序管理策略的应用创建部署类型时，Configuration Manager 将在部署关联应用时确认应用管理策略必须已链接到此部署类型，并提示你关联应用管理策略。 对于托管浏览器，将需要关联常规和托管浏览器策略。 有关详细信息，请参阅[如何在 Configuration Manager 中针对移动设备创建和部署应用程序](https://technet.microsoft.com/en-us/library/dn469410.aspx)。

> [!TIP]
> 对于运行 iOS 7.1 之前的操作系统的设备，关联的策略只有在卸载应用后才能删除。

> 如果从 Configuration Manager 取消注册设备，则策略不会从应用中删除。 应用了策略的应用将保留策略设置，甚至在卸载并重新安装了该应用后也是如此。


### 步骤 5：监视应用部署。
创建并部署了与移动应用程序管理策略关联的应用后，可以[监视应用并解决任何策略冲突问题](https://technet.microsoft.com/en-us/library/mt131414.aspx?f=255&MSPPError=-2147217396#BKMK_Step5)。

有关监视应用程序的常规信息，请参阅[如何在 Configuration Manager 中监视应用程序](https://technet.microsoft.com/en-us/library/gg682201.aspx)。

## 后续步骤

创建并部署与 MAM 策略关联的应用后，可以了解有关 [MAM 最终用户体验](end-user-experience-mam.md)的详细信息。 这将帮助你为可能出现的任何问题做好准备。



<!--HONumber=Jul16_HO1-->


