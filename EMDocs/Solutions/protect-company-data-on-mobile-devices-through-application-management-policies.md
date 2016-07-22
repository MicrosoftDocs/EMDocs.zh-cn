---
title: "通过 MDM 保护使用 MAM 的公司数据"
description: 
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 6c7088a9-ca88-4ff2-97a6-f842691fd3c7
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 276a4ee6ceab6b39b9add2ea844cdf03f142a253
ms.openlocfilehash: e925f84d1e885c8427dbd13eb060e8e2761aaeb6


---

# 通过应用程序管理策略保护移动设备上的公司数据
保护公司数据至关重要，而随着更多员工使用其移动设备访问公司资源（包括电子邮件和电子邮件附件），这成为了越来越具有挑战性的任务。 作为 IT 管理员，你要确保即使在那些移动设备不在公司的物理位置范围中时，公司数据也受到保护。

本指南着重于在托管应用程序应用于两个 Intune MDM 部署时对它的启用：

- 作为使用 Intune 的云管理解决方案
- 作为带 Configuration Manager 的集成服务

这允许你通过移动应用程序管理 (MAM) 策略创建和部署应用，以更好地保护公司数据。

本文档着重于最终用户设备在 MDM 的 Intune 中注册时创建基于 MAM 的策略。 请参阅[保护未在 Microsoft Intune 中注册的设备上的业务线应用和数据](https://docs.microsoft.com/en-us/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune)，了解有关设备本身未在 MDM 的 Intune 中注册时配置这些 MAM 策略的信息。

## 简介
托管应用是应用了移动应用程序管理策略的应用，这些策略使它们符合公司的安全要求。 有两个可用于管理移动应用的选项：
- **默认功能**，如“Apple Managed Open In”，此功能可通过控制允许打开特定文档及电子邮件附件的应用来保护企业数据
- **Intune App SDK**，它允许你限制功能并限制任何启用了 Intune App SDK 的应用的数据共享。 Intune 应用 SDK 的某些主要功能让你可以：
  - 管理另存为功能
  - 阻止剪切、复制和粘贴
  - 访问应用时要求进行身份验证
  - 从 Intune 托管应用擦除企业数据

  请参阅[Intune App SDK 概述](https://docs.microsoft.com/en-us/intune/develop/intune-app-sdk)，了解所有 SDK 功能的说明。

## 在开始之前
- **了解如何使用 Microsoft Intune 部署应用：** [了解](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune)有关 Intune 应用部署的基础知识。

- **评估所需实现：**面对用于管理移动设备的所有不同设计和配置选项时，难以确定可最好地满足公司需求的组合。 [移动设备管理设计注意事项指南](https://docs.microsoft.com/en-us/enterprise-mobility/Solutions/mdm-design-considerations-guide)可帮助你了解移动设备管理设计要求，并详细介绍了一系列步骤和任务，你可以遵循这些步骤和任务来设计最符合公司的业务和技术需求的解决方案。
- **了解高级别的最终用户体验：**实施解决方案后，将可以保护设备上的数据，无论公司是否对其进行管理。 只需实现应用级别策略，即可限制对公司资源的访问，并让数据处于 IT 部门的监控范围之内。

   > [!NOTE]
   > 有关此解决方案的最终用户体验的更详细描述，请参阅[最终用户体验](end-user-experience-mam.md)一文。

- **了解应用生命周期：**就像管理你的设备一样，应用都具有一个生命周期，从做准备到部署、监视、更新，再到最后停用。 Intune 在此生命周期的所有阶段都能为你提供帮助。 有关应用生命周期的详细信息，请参阅[应用生命周期概述](https://docs.microsoft.com/en-us/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune)。
- **了解可与 MAM 策略一起使用的 Microsoft 应用：**[Microsoft Intune 应用程序合作伙伴](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)页包含有关来自 Microsoft 和其他公司的可用于移动应用程序管理策略的应用的最新信息。

  你可以使用 Microsoft Intune 应用包装工具修改内部应用的行为，从而允许配置应用的功能，而无需修改应用自身的代码。 有关更具体的信息，请参阅以下主题：
 - [使用 Microsoft Intune 应用包装工具为移动应用程序管理准备 iOS 应用](https://docs.microsoft.com/en-us/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
 - [使用 Intune 应用包装工具为移动应用程序管理准备 Android 应用](https://docs.microsoft.com/en-us/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

- **了解如何解决策略冲突：**如果在第一次部署到用户或设备时出现移动应用程序管理策略冲突，则冲突中指定的设置值将从部署到应用的策略中删除，并且应用将使用内置冲突值（**限制性最强**为默认值）。

  如果在后续部署到应用或用户时出现移动应用管理策略冲突，则冲突的指定设备值将不会更新到部署到应用的移动应用管理策略，并且应用将使用该设置的现有值。

  如果设备或用户收到两个冲突策略，则适用以下行为：
  - 如果策略已经部署到设备，则现有策略设置不会被覆盖。
  - 如果尚无策略部署到设备，并且两个冲突设置已经部署，则将使用设备内的默认设置。

## 后续步骤
熟悉了 MAM 的整个过程后，就可以开始[在 Intune 中使用移动应用程序管理策略](mam-intune.md)或[在 Configuration Manager 中使用移动应用程序管理策略](mam-configmgr.md)。 或者可以阅读了解 [MAM 策略的最终用户体验](end-user-experience-mam.md)。



<!--HONumber=Jul16_HO1-->


