---
# required metadata

title: 移动设备管理设计注意事项指南
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 7083b6b8-27a3-427b-b505-25d007d63cdd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 移动设备管理设计注意事项指南

由于移动设备管理 (MDM) 解决方案有许多不同的设计和配置选项，因此有时难以确定哪个解决方案最符合组织的需求。 此设计指南将帮助你了解 MDM 设计要求，并且将详细介绍一系列你可以遵循的步骤和任务，以设计最符合组织的业务和技术需求的 MDM 解决方案。 

## 入门

在这些步骤和任务中，本指南将介绍组织可以使用的相关技术和功能选项以满足功能和服务质量（例如可用性、可伸缩性、性能、可管理性和安全性）级别要求。

具体而言，本指南的目标是帮助你回答以下问题：

- 为了最好地满足我的业务要求，我需要回答哪些问题以推动移动设备管理解决方案采用？
- 为了针对我的组织设计移动设备管理解决方案，我应该完成的活动序列是什么？
- 哪些 Microsoft 移动性管理技术和配置选项可用于帮助我满足要求，如何权衡这些选项的优劣？

**本指南适用于谁？** 负责为中型或大型组织设计移动设备管理解决方案的信息技术架构师和专业人员。

**本指南将如何帮助你？** 你可以使用本指南了解如何设计能够管理公司和用户所拥有的不同外形规格的设备的移动设备管理解决方案。

![混合 Intune 和 System Center Configuration Manager MDM 解决方案的示例](./media/MDM_Figure_01.png)
**混合 Intune 和 System Center Configuration Manager MDM 解决方案的示例**

上图是混合管理解决方案的示例，在该方案中它利用云服务与本地功能集成，以便管理所有类型的设备，而不考虑设备位置。 尽管这是一个非常常见的方案，但每个组织的 MDM 设计可能由于每个组织的独特管理要求而与示例不同。
 
本指南详细介绍一系列你应该遵循的步骤，以协助你设计满足你的组织的独特要求的自定义 MDM 解决方案。 在以下步骤和任务中，本指南涵盖了你可用于满足 MDM 的功能和服务质量级别要求的相关技术和功能选项。 

尽管本指南可帮助你设计 MDM 解决方案，但它不讨论管理解决方案的具体实现或操作选项。 你可以使用位于本指南末尾的**后续步骤和其他资源**部分中提供的链接在 docs.microsoft.com 和 TechNet 库中查找[ Microsoft Intune ](/Intune/)、[适用于 Office 365 的移动设备管理](https://technet.microsoft.com/library/ms.o365.cc.devicepolicy.aspx)和 [Microsoft System Center Configuration Manager](https://technet.microsoft.com/library/cc507089.aspx) 的部署和配置步骤。

**假设：**具有使用 Microsoft Intune、System Center 2012 R2 Configuration Manager (ConfigMgr)、Windows Server 2012 R2 和运行 Android、iOS 和 Windows Phone 的移动设备的经验。 你可能在初始 MDM 测试或有限生成环境中部署过其中一个解决方案。 在本指南中，我们假设你正在查找这些解决方案如何单独或在集成的解决方案中满足你的业务需求。

## MDM 设计注意事项
本指南涵盖一组你可以遵循的步骤和任务，以设计最符合你的要求的解决方案。 这些步骤将按顺序呈现。 但是，由于你的设计日趋成熟或设计选择发生冲突，你在后续步骤中了解的设计注意事项可能会提示你更改在你之前的步骤中所做的决策。 我们将在本指南中向你警报潜在的设计冲突。

只有在为了将本指南中的所有注意事项纳入考虑而循环访问以下步骤足够多的次数之后，你才会开发出最符合要求的移动设备管理设计。 

- [步骤 1 - 确定你的移动设备管理要求](mdm-step-1-identify-your-mobile-device-management-requirements.md)
- [步骤 2 - 规划移动设备管理](mdm-step-2-plan-for-mobile-device-management.md)
- [步骤 3 - 计划保护移动设备](mdm-step-3-plan-enhancing-mobile-devices-protection.md)
- [步骤 4 - 规划软件型服务移动设备管理](mdm-step-4-plan-for-software-as-a-service-mobile-device-management.md)
- [后续步骤和其他资源](mdm-next-steps-and-additional-resources.md)
        
## 正在查找可下载的版本？
可在 [ TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)中获取此完整指南的可下载副本。


<!--HONumber=Jun16_HO1-->


