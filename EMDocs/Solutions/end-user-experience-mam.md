---
title: "MAM 的最终用户体验"
description: 
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bbc9f6ea-fc92-468d-bb5b-60c67949ca28
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 276a4ee6ceab6b39b9add2ea844cdf03f142a253
ms.openlocfilehash: 4d1db666c95ef845802952369eb0d505ef4a3dd0


---

# 移动访问管理策略的最终用户体验
仅当在工作环境中使用应用时，才应用 MAM 策略。 阅读以下示例方案，帮助你对用户进行培训，使其了解托管应用如何工作。

本部分提供了以下最终用户体验的示例：

- 方案：在 iOS 设备上访问 OneDrive
- 方案：在 Android 设备上访问 OneDrive

有关其他特定的最终用户体验的信息，请参阅以下文章：

- [使用具有多身份支持的应用](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#using-apps-with-multi-identity-support)
- [管理用户帐户](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#managing-user-accounts)
- [使用权限管理共享应用查看媒体文件](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)

## 方案：在 iOS 设备上访问 OneDrive

1. 用户启动“OneDrive”应用以打开登录页。
> [!NOTE]
> 在个人设备上，最终用户通常要下载应用。 如果设备由 MDM 解决方案托管，则你可将应用部署到该设备。

2. 用户键入其工作帐户用户名，并重定向到“O365 身份验证”页以输入工作凭据。

  Azure AD 成功验证凭据后，将应用 MAM 策略。
3. 系统会提示用户为该应用设置 **PIN**（如果为此应用配置策略）。

4.  设置并确认 PIN 后，用户可以访问他们位于 **OneDrive for Business** 的文件。
> [!NOTE]
> 更改已部署的策略后，下次打开应用时将应用所做的更改。

## 方案：在 Android 设备上访问 OneDrive
1. 用户启动“OneDrive”应用以打开登录页。
> [!NOTE]
> 在个人设备上，最终用户通常要下载应用。 如果设备由 MDM 解决方案托管，则你可将应用部署到该设备。

2.  用户键入其工作帐户用户名，并重定向到“O365 身份验证”页以输入工作凭据。

  Azure AD 成功验证凭据后，将应用 MAM 策略。

3.  如果将策略设置设置为需要使用 **PIN **才能访问 **OneDrive** 应用，则 **OneDrive** 应用会自动启动并将提示用户设置 **PIN**。

4.  设置并确认 PIN 后，用户即可继续使用 **OneDrive**，它现由应用策略托管。

## 后续步骤
你可以阅读有关其他最终用户体验的更多信息，包括[使用具有多身份支持的应用](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#using-apps-with-multi-identity-support)、[管理用户帐户](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#managing-user-accounts)以及[通过 Rights Management 共享应用查看媒体文件](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)。



<!--HONumber=Jul16_HO1-->


