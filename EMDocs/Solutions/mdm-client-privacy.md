---
title: "客户端隐私"
description: "本文介绍一系列移动设备管理方案中应考虑的有关客户端隐私的设计注意事项。"
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c799a6c4-fe0a-4148-8e75-29e6ffdb7e6e
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 916404d1aaad5b4db01dff84c544e3364b7ec6ee


---

#<a name="client-privacy"></a>客户端隐私

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

当你的公司部署移动设备管理时，请务必注意用户隐私和组织隐私之间的界限。 理想情况下，你的组织应该已经有一个明确的隐私策略，指出用户在数据隐私方面的预期。 由于移动设备可能存储公司数据，并且这些设备将随用户而动，因此明确定义界限并让用户事先知道他们在维护组织隐私方面所起的作用很重要。
  
另一个注意事项是你将如何确保用户知道当他们在组织的 MDM 解决方案中注册其设备时会发生什么。 使用 [Microsoft Intune 公司门户](https://technet.microsoft.com/library/dn646957.aspx)，你可以自定义公司的隐私声明来包含一个 URL，该 URL 具有当用户使用托管设备时将收集用户的哪些信息的说明。
 
你还可以发布条款和条件，供用户在首次从其设备使用公司门户时查看，无论该设备是否已在 MDM 解决方案中注册。 用户必须接受这些条款才能访问公司门户。 当你更新条款和条件并希望用户查看和接受新条款时，你可以将新的条款和条件标记为新版本，并且用户将在下次访问公司门户时完成相同的接受过程。 

当你有将 ConfigMgr 与 Intune 连接的混合环境时，也可以使用相同的要求接受条款和条件的功能。 此外，ConfigMgr 可以使用合规性设置来确定设备是否符合你使用配置基线部署的配置项目。 如果某些设置不合规，可以自动修复它们。 

管理点会将符合性信息会发送到站点服务器，并存储在站点数据库中。 设备在将此信息发送到管理点时会对其进行加密，但信息不会以加密格式存储在站点数据库中。 信息将保留在数据库中，直到每 90 天站点维护任务“删除过期的配置管理数据”将其删除。  你还能够配置删除间隔。 此合规性信息不会被发送到 Microsoft。

由于 Intune 和 Office 365 是基于云的服务，因此用户可能还希望知道 Microsoft 如何为这些服务处理用户隐私。 你可以提供指针，指向这些服务相关的隐私信息，例如以下各项：

- Office 365 信任中心
- Microsoft Intune 信任中心

隐私对于用户和贵组织来说非常重要，使用的 MDM 解决方案必须十分恰当地平衡隐私需求之间的关系，并使用户了解贵组织的隐私策略和期望。 下表比较了不同 MDM 解决方案中提供的隐私要求帮助选项，它们可帮助你选择最适合贵组织隐私要求的 MDM 选项。

## <a name="intune-standalone"></a>Intune（独立版）

**优点**

- 使用 Intune 公司门户发布组织的隐私声明

**缺点**

- 它没有隐私策略的模板。 存在如下假设：你的组织已采用某个隐私策略，并且公司门户将只播发存储在其他位置的此策略。

## <a name="office-365-with-mdm"></a>包含 MDM 的 Office 365

**优点**

- 没有用于发布隐私声明的功能

**缺点**

- 没有用于发布隐私声明的功能

## <a name="hybrid-intune-with-configmgr"></a>混合版（带 ConfigMgr 的 Intune）

**优点**

- 使用 Intune 公司门户发布组织的隐私声明
- 从云和本地设备注册的移动设备的单个管理控制台

**缺点**

- 如果组织没有当前本地 ConfigMgr 基础结构，则需在集成前规划、安装和配置此平台




<!--HONumber=Nov16_HO4-->


