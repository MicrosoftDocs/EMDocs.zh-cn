---
title: "数据分隔"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 50bd37fe-30b5-4a45-9c36-0b907dd13cc2
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e23cdad577738a72b6dc8423a5ba6cf7af29bfb
ms.openlocfilehash: 64cd77f7930216f38786451b56037f49d97b095a


---

# 数据分隔

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

数据分隔不仅对你的组织很重要，对于保护用户个人信息的隐私也很重要。 数据分隔有助于你从属于用户的设备中删除所有公司应用和数据，而不会影响该用户的个人数据（请参见下图）。

![数据分隔](./media/MDM_Figure_10.png)

## 用户的个人数据与公司的数据隔离

通过使 MDM 解决方案部署的所有应用、公司数据和策略保持分离，可以在必要时使用选择性擦除从设备中删除这些内容，而不会影响用户的个人内容和应用。 

>[!TIP] 
> 有关远程擦除在其他平台（如 iOS 和 Android）中的运行方式的详细信息，请阅读[通过 Microsoft Intune 使用完全擦除或选择擦除来帮助保护数据](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) 

移动设备数据管理的选择性擦除包含在 Windows Server 2012 R2 和 Windows 8.1 中。 它的工作原理是将帮助 Exchange Server 和 Microsoft Intune 管理员管理设备上的企业数据和开发可使用 [Windows 选择性擦除](https://technet.microsoft.com/library/dn486874.aspx)功能的应用的资源链接起来。  Windows Phone 8 和更高版本支持在内部存储中分离数据。

![数据分隔](./media/MDM_Figure_11.png)

通过下载[ Windows Phone 8.1 安全概述](http://www.microsoft.com/download/details.aspx?id=42509)阅读有关 Windows Phone 8.1 安全功能的详细信息。

如果用户在其移动设备上在个人帐户和公司帐户之间切换，则数据分隔可能难以实现。 在 BYOD 方案中，用户通常使用多个凭据在其设备上执行不同的任务。 

企业数据保护 (EDP) 提供了数据隔离，但既不使用容器也不需要特殊版本的应用程序访问业务数据，然后使用另一个实例访问个人数据。 没有容器、分区或特殊文件夹以物理方式分隔个人和业务数据。 相反，Windows 10 Mobile 是标识企业数据的访问控制代理，因为它对企业是加密状态。 

EDP 通过对企业数据进行加密提供数据分隔。 有关详细信息，请参阅[企业数据保护 (EDP) 概述](https://technet.microsoft.com/library/dn985838.aspx)。 Intune EDP 策略将管理受 EDP 保护的应用、企业网络位置、保护级别和加密设置的列表。

当用户安装并登录到在 Intune 托管的设备上支持多个标识（多标识）的应用（如 Outlook）时，Intune 将检查他们正在使用的帐户是否与设备上的托管帐户匹配。 如果该帐户是托管帐户，并且还存在针对该应用和用户的策略，则该策略设置将保护该帐户中的数据。 当用户将个人帐户添加到应用时，这些帐户将超出 Intune 管理和保护范围。 这允许应用程序的个人使用，而不会损害公司保护。 有关 Intune 中的多身份功能的详细信息，请阅读[通过 Microsoft Intune 使用移动应用程序管理策略保护数据](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)。 

下表比较了不同的 MDM 解决方案提供的选择性擦除功能，以帮助你选择最符合你的组织的数据分隔要求的 MDM 解决方案。

## Intune（独立版）

**优点**

- 允许你执行选择性擦除以仅删除位于移动设备上的公司数据
- 允许你执行恢复出厂设置并完全擦除移动设备
- 对多标识应用的支持

**缺点**

- 不包括移动设备存储的本机加密
- 没有与当前本地 MDM 平台的集成意味着将增加一个管理接口供你使用

## 包含 MDM 的 Office 365

**优点**

- 允许你执行恢复出厂设置并完全擦除 Android、Windows Phone 和 iOS 设备
- 允许你在 Android、Windows Phone 和 iOS 设备上执行选择性擦除，从而仅从移动设备中删除公司数据

**缺点**

- 没有与当前本地 MDM 平台的集成意味着将增加一个管理接口供你使用

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 允许你执行选择性擦除以仅从移动设备中删除公司数据
- 允许你执行恢复出厂设置并完全擦除移动设备
- 对多标识应用的支持
- 用于管理基于云的和本地移动设备的单一管理控制台

**缺点**

- 如果组织没有当前本地 ConfigMgr 基础结构，则需在集成前规划、安装和配置此平台

若要了解如何在对每个移动设备平台进行选择性擦除后删除和保留数据，请务必阅读文章[通过 Microsoft Intune 使用完全擦除或选择擦除来帮助保护数据](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune)。 如果你有混合环境，请参考文章[如何使用 Configuration Manager 远程擦除移动设备](https://technet.microsoft.com/library/dn956981.aspx)以了解如何使用 ConfigMgr 完成此任务。


<!--HONumber=Jul16_HO3-->


