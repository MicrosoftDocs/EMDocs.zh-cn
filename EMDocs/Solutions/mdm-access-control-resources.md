---
title: "对资源的访问控制"
description: "移动设备管理的访问控制设计注意事项。"
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 10/18/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 5967876b-3c08-4498-a0a6-0225b562d35f
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: cc449bca094772759983cc924b3294a4f6b44d83
ms.openlocfilehash: 80a435883f8df7ea7f6dde46e40f80e873ea617e


---

# 对资源的访问控制

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

已使用 Active Directory 对用户进行身份验证和授权的组织已管理对特定资源的访问权限，方法是使用 Active Directory 中的组来划分和控制对资源的访问。  

若要管理对特定资源的控制，你首先对用户的访问进行身份验证和授权，然后验证用户对目标资源所具有的控制类型。 在下图中，为访问文件夹的用户 Bob 显示了此操作。

![身份验证流](./media/MDM_Figure_13.png)

## 基本身份验证和授权流

传统的访问控制列表 (ACL) 非常有限，并且不会考虑用户状态的其他方面，例如他尝试访问此资源时所在的位置。 如果你的组织在授予对资源的访问权限之前需要包含更多的变量，可以使用在 Windows Server 2012 中本地提供的[动态访问控制](https://technet.microsoft.com/library/dn408191.aspx)。 Windows 10 支持运行状况证明，这在提供数据访问权限之前有助于 IT 人员控制设备的运行状况的状态。 远程运行状况证明服务执行一系列测量检查。 它验证安全相关的数据点，包括启动状态（安全启动、调试模式等），以及管理安全性的组件状态（BitLocker、设备保护等）。 然后，它通过向设备发回运行状况加密的 blob 来传递设备的运行状况状态。 有关详细信息，请参阅[控制基于 Windows 10 的设备运行状况](https://technet.microsoft.com/library/mt592023.aspx)。

Intune 管理员可以在 [Intune 管理控制台](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)中查看 Windows 10 设备运行状况证明的状态。 设备运行状况证明让管理员能够确保客户端计算机具有可信 BIOS、TPM 和启动软件配置。 为了支持设备运行状况证明，客户端设备必须运行 Windows 10 并启用 TPM 2。 

对于许多自行充当云提供商（通过使用允许他们拥有私有云的技术）的公司，另一个选项是使用基于角色的访问控制 (RBAC)。 [Azure AD 允许 IT 人员使用 RBAC](http://azure.microsoft.com/documentation/articles/role-based-access-control-configure/) 控制对资源的访问权限。 并且由于 Azure AD 可以与本地 Active Directory 集成，所以你可以同时使用它们，以确定用户访问资源的方式。

资源也可以是应用，这意味着若要实现对资源的访问控制，你的 MDM 解决方案还必须能够控制如何安装和访问应用。 [Intune 中的移动应用程序管理策略](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)可使你修改所部署的应用的功能，以帮助确保它们符合公司合规性和安全策略。 

使用下表作为参考协助你选择最符合组织的访问控制要求的 MDM 选项。

## Intune（独立版）

**优点**

- 应用的访问控制（安装和管理）
- 运行状况证明服务的条件访问

**缺点**

- 如果缺少与当前本地 MDM 平台的集成，将引入一个附加的管理接口供你使用
- 某些策略可能不适用于某些移动平台
 
## Office 365 的 MDM

**优点**

- 对电子邮件、Office Mobile、Office 应用和 OneDrive for Business 的访问控制

**缺点**

- 只允许对资源进行一小部分的访问控制
- 如果缺少与当前本地 MDM 平台的集成，将引入一个附加的管理接口供你使用
- 某些策略可能不适用于某些移动平台

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 应用的访问控制（安装和管理）
- 运行状况证明服务的条件访问

**缺点**

- 当你购买 Intune 订阅时，不包含 Azure AD 云服务

## 企业移动性 + 安全性

**优点**

- 应用的访问控制（安装和管理）
- 利用 Azure AD Premium 提供基于 RBAC 的访问控制
- 运行状况证明服务的条件访问

**缺点**

- 如果组织没有当前本地 ConfigMgr 基础结构，则需在集成前规划、安装和配置此平台



<!--HONumber=Oct16_HO3-->


