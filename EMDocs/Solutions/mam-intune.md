---
title: "在 Intune 中使用移动应用管理策略"
description: "使用移动应用管理策略在 Intune 中创建和部署应用。"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d7c4104-b85f-407e-8832-0e6bbac934f5
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0eacdea52150bc8282df618ae73c96724cec26c5
ms.openlocfilehash: 2efaf8b6298cabd640f141675b5cefe3f77aaae7


---

# 在 Intune 中使用移动应用管理策略
很多公司使用 Microsoft Intune 的一个主要原因是用它来部署用户完成其工作所需的应用。 在部署应用之前，你需要[管理你的设备](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune)。

例如，如果贵公司使用 Microsoft Word，则提供有 Windows、iOS、Android 等使用的版本。 作为 IT 管理员，你面临的挑战是在许多不同的设备和计算机平台上管理多个可用的应用，这样做的目的是允许用户完成其工作的同时仍能确保公司数据的安全性。

如果要将 Intune 与 Configuration Manager 结合使用，请参阅[如何使用 Configuration Manager 中的移动应用程序管理策略控制应用](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396)。

移动应用管理 (MAM) 策略支持：
- 运行 Android 4 和更高版本的设备。
- 运行 iOS 7 和更高版本的设备。

> [!NOTE]
> MAM 策略支持已注册 Intune 的设备。 有关如何为不受 Intune 管理的设备创建应用管理策略的信息，请参阅[通过 Microsoft Intune 使用移动应用管理策略保护应用数据](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)。

与其他 Intune 策略不同，你不会直接部署 MAM 策略。 而是将该策略与你想要进行限制的应用相关联。 当应用部署并安装在设备上时，你指定的设置将起作用。

若要将限制应用到应用上，该应用必须包含 Microsoft Intune 应用软件开发工具包 (SDK)。 有两种方式获得此类应用：

- **使用策略托管应用** – 内置了应用 SDK。 要添加此类型的应用，你可以从 iTunes 应用商店或 Google Play 等应用商店指定应用的链接。 对于此类应用，无需进一步的处理。 若要查看受支持的 Microsoft 应用的完整列表，请转到 [Microsoft Intune 应用程序合作伙伴](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)页上的 Microsoft Intune 移动应用程序库。 单击应用可查看支持的方案、平台以及应用是否支持多身份。
- **使用“已包装的”应用** - 通过使用 Microsoft Intune 应用包装工具对应用进行重新封装，以将应用 SDK 包括在内。 该工具通常用于处理公司内部开发的应用。 它可用于处理从应用商店下载的应用。 请参阅：
  - [使用 Microsoft Intune 应用包装工具为移动应用程序管理准备 iOS 应用](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
  - [使用 Intune 应用包装工具为移动应用程序管理准备 Android 应用](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

某些托管应用（比如用于 iOS 和 Android 的 Outlook 应用）支持**多身份**。 这意味着 Intune 仅对公司帐户或应用程序中的数据应用管理设置。

例如，使用 Outlook 应用：
- 如果用户配置公司和个人电子邮件帐户，则 Intune 仅对公司帐户应用管理设置，并不管理个人帐户。
- 如果设备已停用或已取消注册，则仅从设备中删除公司的 Outlook 数据。
- 使用的公司帐户必须与用于向 Intune 注册设备的帐户相同。

Word、Excel 和 PowerPoint 也都支持多身份，除了仅在管理和编辑来自 OneDrive 或 SharePoint 等服务的企业身份数据时应用策略限制。

## 使用移动应用管理策略在 Intune 中创建和部署应用

- 步骤 1：获取指向策略托管应用的链接，或创建已包装的应用。
- 步骤 2：将应用发布到你的云存储空间。
- 步骤 3：创建移动应用管理策略。
- 步骤 4：选择将应用与移动应用管理策略相关联的选项，然后部署该应用。
- 步骤 5：监视应用部署。

### 步骤 1：获取指向策略托管应用的链接，或创建已包装的应用
- **获取策略托管应用的链接** - 从应用商店查找并记录你想要部署的策略托管应用的 URL。
例如，Microsoft Word for iPad 应用的 URL 是 [https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8](https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8)
- **创建已包装的应用** - 使用主题[通过 Microsoft Intune 应用包装工具为移动应用程序管理准备 iOS 应用](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)和[通过 Microsoft Intune 应用包装工具为移动应用程序管理准备 Android 应用](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)中的信息创建已包装的应用。 该工具创建你将应用发布到云存储空间将使用的经过处理的应用。

### 步骤 2：将应用上传到你的云存储空间
发布托管的应用时，过程有所差异，具体取决于你发布的是策略托管的应用，还是使用 Microsoft Intune App Wrapping Tool for iOS 进行处理的应用。

有关将应用上传到云存储空间所需的完整步骤，请参阅[在 Microsoft Intune 中为移动设备添加应用](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune#add-the-app)。

### 步骤 3：创建移动应用管理策略
Azure 门户是用于创建 MAM 策略的推荐管理控制台。 Azure 门户支持以下 MAM 方案：
- 在 Intune 中注册的设备
- 由第三方 MDM 解决方案管理的设备
- 不受任何 MDM 解决方案管理的设备 (BYOD)。

有关使用 Azure 门户创建 MAM 策略的详细信息，请参阅[使用 Microsoft Intune 创建和部署移动应用管理策略](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)。

如果你当前正在使用 Intune 管理控制台管理你的设备，则可以创建一个 MAM 策略，来支持在 Intune 中使用 [Intune 管理控制台](https://docs.microsoft.com/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console#-step-3-create-a-mobile-application-management-policy)注册的设备的应用。


### 步骤 4：部署应用，选择将应用与移动应用程序管理策略相关联的选项
如果你正在使用 Azure 门户，则[将 MAM 策略部署到用户](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune#deploy-a-policy-to-users)。

如果你正在使用 Intune 门户，则[部署该应用](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune#deploy-an-app)，确保你选择“移动应用管理”页面上的移动应用管理策略，以将其与应用关联。

如果设备从 Intune 取消注册，策略也不会从应用中删除；任何应用了策略的应用都将保留策略设置，即使卸载应用并重新安装也将如此。

#### 应用已部署在设备上时应该如何操作

也存在这样一种情况：当你部署应用时，目标用户或设备之一已经安装了非托管版本的应用，例如用户从应用商店安装了 Microsoft Word。

在这种情况下，必须要求用户手动卸载非托管的版本，才能安装所配置的托管版本。

但是，对于运行 iOS 9 及更高版本的设备，Intune 将自动要求用户提供许可以接管现有应用。 如果用户同意，则应用将由 Intune 管理，并将应用你为其关联的任何 MAM 策略。


### 步骤 5：通过 MAM 策略监视应用部署
通过 Intune 控制台使用以下程序来监视应用的部署并解决任何策略冲突。

1. 在 [Microsoft Intune 管理控制台](https://manage.microsoft.com/)中，单击“组”。
2. 执行以下步骤之一：
  -  单击**“所有用户”**，然后双击你想要检查其设备的用户。 在“用户属性”页面，单击“设备”，然后双击你想要检查的设备。
  -  单击“所有设备”>“所有移动设备”。 在“设备组属性”页面，单击“设备”，然后双击你想要检查的设备。
3. 从“移动设备属性”页面，单击“策略”以查看已部署到设备的 MAM 策略列表。
4. 选择你想要查看其状态的 MAM 策略。 你可以在底部窗格查看策略详细信息，并展开其节点以显示其设置。
5.  在各个 MAM 策略的“状态”列下，将显示“符合”、“符合（待定）”或“错误”。 如果所选择的策略有一项或多项冲突设置，将会在该字段中显示“错误”。
6.  发现了冲突后，你可以将冲突策略设置修改为使用相同设置，或对应用和用户仅部署一个策略。

> [!NOTE]
> 你可以通过 [Azure 门户](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)或 [Intune 控制台](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune)了解有关监视应用的更多常规信息。

## 后续步骤

创建并部署与 MAM 策略关联的应用后，可以了解有关 [MAM 最终用户体验](end-user-experience-mam.md)的详细信息。 这将帮助你为可能出现的任何问题做好准备。



<!--HONumber=Nov16_HO2-->


