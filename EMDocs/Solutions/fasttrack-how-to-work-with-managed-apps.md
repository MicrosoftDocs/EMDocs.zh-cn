---
title: 如何使用组织管理的移动应用程序
description: 如何使用组织管理的移动应用
keywords: ''
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: 174348f0-dbc6-4204-8626-3c6f38b7bbde
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: 29aaab0743bbc42ec3a6297e5c8174dbdc977fe7
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196502"
---
# <a name="how-to-use-mobile-apps-managed-by-your-organization"></a>如何使用组织管理的移动应用

## <a name="accessing-onedrive-on-an-ios-device"></a>在 iOS 设备上访问 OneDrive

本部分使用 OneDrive for Business 作为示例来演示 Intune 管理的应用程序上的用户体验如何稍有不同。

1. 启动 **OneDrive for Business** 应用以打开登录页。

   ![显示用于 iOS 的 OneDrive for Business 登录页面的屏幕截图。](./media/ft-useMngdApps-1-launchOnedrive.png)
   > [!NOTE]
   > 在个人设备上，最终用户通常要下载应用。 如果设备由 MDM 解决方案托管，则你可将应用部署到该设备。

2. 键入你的工作帐户用户名。 你将会重定向到“O365 身份验证” 页，以便输入工作凭据。

   ![显示 iOS 用户在 Office 365 登录页上输入凭据的屏幕截图。](./media/ft-useMngdApps-2-enterName.png)
3. 凭据成功通过 Azure AD 进行的身份验证后，将应用 MAM 策略，并将要求你重启 **OneDrive for Business** 应用。

   ![显示必须重启 OneDrive 的屏幕截图。](./media/ft-useMngdApps-3-restart.png)
   > [!NOTE]
   > “需要重启”对话框仅在未注册 Intune 的设备上显示。

4. 重新启动 **OneDrive for Business** 应用。 该应用将启动，并会开启 MAM 策略。 现在将提示你为该应用设置“PIN” 。 （如果你为此配置了该策略）。

   ![系统提示 iOS 用户设置应用的 PIN 的屏幕截图。](./media/ft-useMngdApps-4-enterPIN.png)
5. 设置 PIN 并确认后，即可访问 **OneDrive for Business** 上的文件。

   ![显示 iOS 中的 OneDrive for Business 上可访问的各种文件的屏幕截图。](./media/ft-useMngdApps-5-accessFiles.png)
   > [!NOTE]
   > 更改已部署策略时，将在下次打开该应用时应用更改。

## <a name="accessing-onedrive-on-an-android-device"></a>在 Android 设备上访问 OneDrive

本部分使用 OneDrive for Business 作为示例来演示 Intune 管理的应用程序上的用户体验如何稍有不同。
1. 启动 **OneDrive for Business** 应用以打开登录页。
   > [!NOTE]
   > 在个人设备上，最终用户通常要下载应用。 如果设备由 MDM 解决方案托管，则你可将应用部署到该设备。

2. 键入你的工作帐户用户名。 你将会重定向到“O365 身份验证”页，以便输入工作凭据。

   ![显示 Android 用户在 Office 365 登录页上输入凭据的屏幕截图。](./media/ft-useMngdApps-6-enterCreds.png)
3. 凭据成功通过 Azure AD 进行的身份验证后，如果尚未在设备上安装公司门户应用，则会显示一条带有安装指令的消息。 点击“获取应用”以继续。
   > [!NOTE]
   > Android 设备上与 MAM 策略关联的所有应用都需要公司门户应用。 对于未在 Intune 中注册的设备，应用必须安装在设备上，而无需启动或登录应用。

4. 你现将位于“Google Play” 应用商店，可在其中下载和安装“公司门户” 应用。

   ![系统提示 Android 用户转到 Google Play 应用商店获取 Intune 公司门户的屏幕截图。](./media/ft-useMngdApps-7-installPortal.png)

   公司门户应用有助于保护数据安全。

   ![系统提示 Android 用户安装 Intune 公司门户的屏幕截图。](./media/ft-useMngdApps-8-intunePortal.png)

5. 完成安装后，选择“接受”以接受条款。
6. **OneDrive for Business** 应用将自动启动。
7. 如果将策略设置设为需要使用 PIN 才能访问 **OneDrive for Business** 应用，则下次打开 OneDrive for Business 时，将提示你设置“PIN”。

   ![系统提示 Android 用户为应用设置 PIN 的屏幕截图](./media/ft-useMngdApps-9-setNewPIN.png)
8. 设置并确认 PIN 后，即可继续使用 **OneDrive for Business**，它现由应用策略管理。

### <a name="want-to-learn-more"></a>了解更多信息？

请参阅 [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)（企业移动性 + 安全性）。
