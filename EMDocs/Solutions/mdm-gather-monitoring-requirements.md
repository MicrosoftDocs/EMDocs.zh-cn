---
title: "收集监视要求"
description: "本文帮助确定使用企业移动性 + 安全性规划和设计 Microsoft 移动设备管理解决方案时的移动设备管理监视选项。"
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac136523-8089-409b-b74d-2d4c0ce399d4
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 2a03416cf8255a29c0394746b3d5285057163d15


---

# <a name="gather-monitoring-requirements"></a>收集监视要求

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

为了确保用户和设备遵守你的企业策略和安全策略，监视和捕获移动设备的状态和事件信息十分重要。 这对于必须遵守政府法规要求和行业合规性指南的组织而言尤为重要。

报告还可以提供有关组织中软件、硬件和软件许可证的有价值的信息，以帮助管理清单。

在制定监视和报告指南时，要意识到用户隐私的重要性（尤其是在用户可以在组织的移动设备管理解决方案中注册个人所有的设备时）。 你的组织不应捕获、监视、报告或共享任何个人活动或者信息。

一般来说，移动设备管理解决方案将监视分为两个常规领域：

- **日志记录：**捕获和存储移动设备和移动设备应用程序状态及信息。
- **报告：**显示报告和通知，包括可以根据需要创建的标准和可自定义的报告，以及自动摘要和仪表板状态报告。

## <a name="monitoring-planning-questions"></a>监视计划问题

回答以下有关计划设备监视的问题：

- 你需要何种类型的可用于移动设备的常规报告？
 - 设备清单？
 - 设备使用情况？
 - 设备访问？
 - 设备应用程序？
- 报告需要共享吗？
 - 在 IT 角色间共享？
 - 还是在 IT 组织外部共享？
 - 远程访问（在企业网络外部）？
- 你需要标识关于设备的哪类问题？
- 需要处理哪类在监视中捕获到的事件？ 在哪个时间段？
- 你需要自定义的按需报告吗？
- 当设备取消注册时，应该捕获特定清单和报告事件吗？
- 设备取消注册后，应该存档/维护旧的清单和报告事件吗？

>[!TIP]
>请务必记录下每个答案，并了解答案背后的基本原理。 之后的任务将详细阐述可用选项以及每个选项的优点/缺点。  回答这些问题将帮助你选择最符合你的业务需求的选项。



<!--HONumber=Nov16_HO4-->


