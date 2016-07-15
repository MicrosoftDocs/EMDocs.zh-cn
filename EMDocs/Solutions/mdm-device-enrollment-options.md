---
title: "设备注册选项"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 54082b94-1d21-44d5-9fba-af6e04397def
ms.reviewer: 
ms.suite: ems
ms.sourcegitcommit: a16e90093c7571f3c098ce815a2b70ae03c080e3
ms.openlocfilehash: 90604329992f8ecb881ac1b83358af16de5b65cb


---


# 设备注册选项

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

在 Microsoft Intune 中注册设备（无论它是独立版本还是已连接到 System Center 2012 R2 Configuration Manager (ConfigMgr)），要求你准备用于设备的服务。 在 Office 365 的 MDM 中注册移动设备还要求你激活 MDM、配置基本设置，以及将每位用户包含在下次他们在其移动设备上登录到 Office 365 时的注册消息的[安全策略](https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx)响应中。 他们必须在用于访问 Office 365 电子邮件和文档的每台移动设备上完成注册和激活步骤。

Intune 独立版本需要配置为定义移动设备管理机构解决方案，这既可以是 Intune 也可以是本地 ConfigMgr 基础结构。 这仅表示“你想要使用哪个管理平台来管理已注册 Intune 的设备 – 是 Intune *还是* ConfigMgr？” 请务必了解[选择最佳选项对你的组织的影响](/Intune/deploy-use/enroll-devices-in-microsoft-intune)，因为管理解决方案一经选定将无法轻易更改。 如果你以后需要更改此配置，必须联系 Microsoft 支持人员获取帮助。 Office 365 租户可以更轻松地指定和更改 Office 365 的 MDM 与 Intune 之间的 MDM机构。 通过更改用户的许可证分配，可以轻松地切换用户级别管理机构。 

对于大多数已使用 ConfigMgr 管理电脑、服务器和其他设备的组织而言，通过 Intune 连接本地解决方案并且通过 ConfigMgr 管理设备通常是最佳选择。 若要将移动设备管理机构分配给 ConfigMgr，你需要创建 [Intune 订阅](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0)，并选择允许 ConfigMgr 管理 Intune 订阅和已注册 Intune 的设备的选项。 也可以[从 ConfigMgr 控制台中](https://technet.microsoft.com/library/jj884158.aspx)创建 Intune 订阅。

此外，在能够注册运行不同类型的移动操作系统的某些类型的移动设备之前，你将需要根据特定的配置要求准备 Intune 服务或 Office 365 的 MDM。 例如，如果你计划注册基于 Apple iOS 的设备，则在**[注册基于 iOS 的设备前，你需要使用 Apple 推送通知 (APN) 服务证书配置](https://technet.microsoft.com/library/dn408185.aspx)** Intune。 如果未配置 Intune，它将无法与 APN 服务和基于 iOS 的设备通信。 运行 **[Android](https://technet.microsoft.com/library/dn764960.aspx)** 或 **[Windows Phone](https://technet.microsoft.com/library/dn764959.aspx)** 操作系统的移动设备具有单独的注册要求。

对步骤 1 中的问题的回答将帮助你决定你希望设备如何在移动设备管理解决方案中注册。 下表比较了每个注册方案的优缺点：

| 领域  | 管理员注册设备 | 用户自助注册设备 |
| ------------- | ------------- | ------------ |
| 成本 | 如果是有经验的管理员执行设备注册，支持/帮助人员成本可能会降低 | 支持成本或支持人员呼叫次数可能会增加，因为缺乏经验的用户可能在注册期间需要私人帮助 |
| 方便  | 每台设备均可在没有任何用户交互的情况下进行注册，从而减少了设备注册错误。 用户可能不得不跟你一起安排时间放置和选取移动设备，这需要进行设备注册计划和跟踪。| 在大多数情况下，设备注册比集中注册过程要快。 也许对设备所有者/用户而言，这一方案更为方便灵活。 |
| Administration | 更易于支持更复杂、自动化、批量或高度自定义的设备注册。 管理员密切控制所有设备的注册情况，这可在注册过程开始时有效地预筛选任意设备或用户。 | 将相对简单的管理任务转移到你的用户，可节省时间、计划、跟踪和管理开销。 |
| 安全 | 如果支持 BYOD 策略，则在未提供相应的安全控制时，管理员将更有可能看到或公开敏感的用户个人信息。 | 现代移动设备的用户可能觉得这种集中既管理繁琐又不方便，使得用户定义的解决方法可能会危及注册安全和合规性过程 |

你的组织可能想要同时使用这两个注册方案，以便可以灵活地针对不同的部门或情况使用不同的方法。 如果是这样，你的移动设备管理解决方案必须能同时支持这两个方案。


<!--HONumber=Jul16_HO2-->


