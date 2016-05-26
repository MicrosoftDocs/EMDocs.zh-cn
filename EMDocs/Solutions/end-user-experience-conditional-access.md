---
# required metadata

title: 条件访问的最终用户体验
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 3e186dd2-e17c-40d8-b160-48038b2c6593

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 条件访问的最终用户体验
当用户首次尝试访问设备上的电子邮件或随后同步时，将检查设备注册和合规性状态。 注册或修复合规性问题的过程是一种指导式体验。 将向最终用户显示注册设备并让其合规的必要步骤，用户无需联系 IT 支持人员：

-   **如果设备未注册**，登录页面将显示访问被拒绝并提示你进行注册。 注册时，设备会自动注册 Azure Active Directory。 Intune 检查设备是否合规，并提供修正措施以解决任何非合规性问题。 设备合规后，Intune 将使用 Azure Active Directory 设定设备的合规性状态。

-   **如果设备已注册但不合规**，则将向设备发送包含问题修正措施的链接。 最终用户纠正此问题后（例如设置密码、加密），管理合规性策略的 Intune 将在 Azure AD 中更新设备的合规性状态。

设备被评定为已注册且合规后，几分钟内即会进行电子邮件同步。

## Android

[本主题](end-user-experience-conditional-access-android.md)描述在启用条件访问并且最终用户首次尝试在其 Android 移动设备上访问电子邮件之后的注册体验。

## iOS

[本主题](end-user-experience-conditional-access-ios.md)描述在启用条件访问后，当最终用户首次尝试在其 iOS 移动设备上访问电子邮件时的用户体验。

## Windows Phone

[本主题](end-user-experience-conditional-access-winphone.md)描述在启用条件访问并且最终用户首次尝试在其 Windows Phone 上访问电子邮件之后的最终用户体验。


<!--HONumber=Apr16_HO4-->


