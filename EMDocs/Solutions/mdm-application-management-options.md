---
# required metadata

title: 应用程序管理选项
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 1f77eba2-8e27-4e08-b2f2-e71e3d776cf4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 应用程序管理选项

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

移动应用程序管理 (MAM) 策略有助于防止公司数据泄漏到移动设备上的使用者应用或服务。 通常情况下，仅会在移动设备管理解决方案中已注册的设备上强制执行这些策略。 Intune 现已扩展其 MAM 功能，当中包括了由其他移动设备管理解决方案管理的设备以及未在任何设备管理系统中注册的设备。

如下图所示，如果你已有 MDM 解决方案，Intune MAM 可帮助你管理和保护 Office 应用程序和 Office 365 数据的安全，而无需取消对员工设备的注册并且无需在共存或迁移方案中将这些设备重新注册在 Intune MDM 中：

![使用 Intune MAM 策略的移动设备的应用程序管理隔离概述](./media/Intune_without_enrollment.png)

**使用 Intune MAM 策略的移动设备的应用程序管理隔离概述**

Intune MAM 功能不是整个 MDM 解决方案的一种替代方案。 许多设备管理方案（如 VPN、Wi-Fi、证书管理、应用程序部署和配置设备级别的安全设置）都需要使用 MDM 协议。

对于使用 ConfigMgr 和 Intune 的混合部署，移动应用管理策略还可用于保护不由 Intune 管理的设备上的应用。 你可以使用这项新功能，为连接到 Office 365 服务的应用应用移动应用管理策略。 连接到内部部署 Exchange 或 SharePoint 的应用不支持此操作。 若要使用此功能，必须使用 Azure 预览门户。

根据你对步骤 1 中的问题的回答，你应该能够确定想要在移动设备管理解决方案中如何管理应用程序。 以下列表显示每个应用管理选项的优缺点。

## Intune（独立版）

**优点**

- 支持在以下设备上管理应用程序：在 Intune 中注册的设备、在其他管理解决方案中注册的设备，或未在任何管理解决方案中注册的设备
- 将公司数据与为 Intune 启用的应用内的客户个人数据中分隔。 其中包括 Office Mobile 应用、已采用 Intune SDK 的第三方应用，或由 Intune 包装的业务线应用
- 可以在公司应用之间通过剪切/复制/粘贴来共享公司数据，同时防止将公司数据共享到个人应用
- 关键数据丢失防护策略，如每个应用的 PIN、另存为控件和应用之间的托管数据共享。
- 这些功能在 Microsoft Word、Excel、PowerPoint、Outlook、OneNote 和 OneDrive for Business 中受到支持
- 管理通过企业批量采购计划的 Apple 批量采购计划购买的 iOS 应用
- 在 Android 和 iOS 设备上受支持

**缺点**

- 在 Windows Phone 上不受支持

## Office 365 的 MDM

- 当前不支持

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- Intune 独立版的所有优点

**缺点**

- 需要其他配置，以将 Intune 与本地 ConfigMgr 基础结构相连接
- 对于尚未配置当前 ConfigMgr 基础结构的组织，需要在与 Intune 集成之前进行规划、安装和配置

通过查看以下 Intune 和 ConfigMgr 内容来了解有关移动应用程序管理选项的详细信息：在 Microsoft Intune 控制台中配置和部署移动应用程序管理策略。 此外，要确保检查在 Intune MAM 策略下可使用的 Microsoft 应用列表以及 Intune 的兼容合作伙伴应用的扩展列表。

<!--HONumber=Apr16_HO2-->


