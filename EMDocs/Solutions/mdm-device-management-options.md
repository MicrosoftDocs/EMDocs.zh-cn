---
# required metadata

title: 设备管理选项
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: a25f7407-92a0-4588-b5f7-a7bad9cdd070

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 设备管理选项

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

通过 Intune 和 ConfigMgr 中心管理移动设备将围绕着管理策略进行。 策略用于定义移动设备的设置组，并且可使用模板进行创建或者为特定设备、用户或组进行自定义。 最佳管理实践是在管理解决方案中注册移动设备前创建管理策略。 这将确保根据在 IT 策略中定义的策略和过程即时管理设备。 这两种解决方案均允许配置以下策略类型：

- 配置策略：配置策略用于定义每台注册移动设备的常规组织设置。 这可能包括设备密码、应用程序、云策略和加密设置，但可以包括不同管理方面的**[许多其他设备设置](https://technet.microsoft.com/library/dn743712.aspx)**。 此外，不同类型的移动设备操作系统使用设备注册配置文件应用和配置配置策略的方式也不同。

>[!TIP]
>在为不同类型的设备、用户或组创建不同的策略时，很容易将互相冲突的策略设置应用到同一设备。 请确保已了解**[如何应用冲突的策略设置](https://technet.microsoft.com/library/dn743712.aspx)**。

- **合规性策略：**合规性策略强制执行移动设备访问（或被拒绝访问）公司资源或服务的组织要求。 这也包括设备密码和加密设置，还要确定移动设备是否取得根权限（“已越狱”）。 与配置策略一样，Intune 和 [ConfigMgr](https://technet.microsoft.com/library/dn376523.aspx) 合规性策略选项也会根据移动设备操作系统类型而有所不同。 如果你在 ConfigMgr 中创建合规性策略，请务必注意，在多部分过程中可配置更高的粒度级别：

 1. 创建[配置项目](https://technet.microsoft.com/library/gg712331.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)
 2. 创建[配置基线](https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)
 3. 将[配置基线](https://technet.microsoft.com/library/hh219289.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)部署到 ConfigMgr 用户或设备集合

- **条件访问策略：**条件访问策略定义电子邮件的访问权限管理方式，可单独使用或与合规性策略结合使用。 在部署条件访问策略之前，必须在 [Intune](/Intune/deployuse/restrict-access-to-email-and-o365-services-with-microsoft-intune) 或 [ConfigMgr](https://technet.microsoft.com/library/dn919655.aspx) 中配置到本地 Exchange Server 或 Exchange Online 服务的连接。 也可以为 Office 365 和 SharePoint Online 服务配置条件访问。

对步骤 1 中的问题的回答可以帮助你确定想要如何在移动设备管理解决方案中注册设备。 下面的列表将有助于你了解每个管理方案的优缺点。

## Intune（独立版）

**优点**

- 支持简化的管理用户和设备的策略控制，该策略控制现已被设备平台分隔。
- 支持 Android、iOS、Windows 10https://technet.microsoft.com/library/mt147406.aspx、Windows 8.x 和 Windows Phone 平台，也支持 Exchange ActiveSync。
- 提供简单的基于 Web 的管理控制台，并且该控制台可从任意位置进行访问。
- 支持基于组的策略，使管理量大类多的移动设备变得更简单
- 支持高级移动设备合规性功能，包括设备根和越狱检测
- 允许对所有移动设备进行选择性擦除或重置为完全出厂设置
- 包括可自定义的公司门户，允许以托管方式安全分配内部和第三方移动应用程序
- 将证书部署到移动设备
- 允许组织在移动应用程序中阻止剪切/复制/粘贴功能
- 支持强制使用托管的浏览器
- 支持使用设备 IMEI 号码来标识和标记企业拥有的设备，以便与个人拥有的设备的策略分配分开

**缺点**

- 用户帐户在 Intune 服务中注册设备的其他许可要求和成本

## Office 365 的 MDM

**优点**

- Office 365 租户中集成的基于 Web 的管理控制台
- 支持基于组的策略，使管理量大类多的移动设备变得更简单
- 支持高级移动设备合规性功能，包括设备根和越狱检测
- 允许对所有移动设备进行选择性擦除或重置为完全出厂设置

**缺点**

- 不支持高级移动设备管理功能，包括：
 - 预配和管理证书、电子邮件、VPN、无线配置文件
 - 注册和管理设备集合
- 不支持某些移动应用程序管理功能：
 - 将业务线应用程序部署到移动设备
 - 启用 Office 移动应用程序的安全数据访问
 - 将企业数据安全扩展到移动设备的业务线应用
 - 托管的浏览器或其他内容查看应用程序

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 除了 Intune 独立版的所有优点外，还包括以下优点：
 - 提供一个窗格的管理企业资源的半透明视图，包括基于角色的管理和脚本（通过 PowerShell）的灵活性

**缺点**

- 需要其他配置，以将 Intune 与本地 ConfigMgr 基础结构相连接
- 对于尚未配置当前 ConfigMgr 基础结构的组织，需要在与 Intune 集成前进行规划、安装和配置
- 当前不支持适用于 Android 设备的 VPN 和电子邮件配置文件
- 当前不支持托管的浏览器支持

<!--HONumber=Apr16_HO2-->


