---
# required metadata

title: 确定你的移动设备管理位置要求
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: c8824726-082e-417a-8522-183a69328ae4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 确定你的移动设备管理位置要求

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

位置要求是你在设计移动设备管理策略时应当仔细考虑的众多因素之一。 不管是从移动设备管理解决方案角度来看还是从设备自身来看，位置都很重要。 回答以下问题：

- 跟踪用户：对于某些类型的移动设备控件，你可能需要根据用户的位置实施可用于限制对公司资源的访问的策略。
    - 公司是否需要实施机制以提供地理围栏，或者根据设备的地理位置强制执行策略的能力？ 
    - 公司是否需要在用户访问公司资源时跟踪用户的地理位置？
- 管理模型：根据你部署的移动设备管理解决方案，管理可以分布在不同站点（位置）或集中于单个位置。 管理中心站点适合于大规模部署，并能集中管理和灵活地支持分布在全局网络基础架构中的设备。 主站点适用于较小的部署，尽管它适应未来发展的选项较少。 确定 MDM 控制是应该集中还是分散。
    - 公司是否需要集中式的管理模型？
    - 是否需要将设备管理解决方案放在本地？
        - 如果不是，是否可以将其放在云中？
        - 如果不可以，是否可以混合？
    - 公司是否需要分散式的模型，其中不同的位置应对设备管理的管理具有自主性？

>[!TIP] 请务必记下每个答案并了解答案背后的基本原理。 下一部分将详细阐述可用的选项以及每个选项的优点/缺点。  回答完这些问题后，你将可以选择最符合你业务需求的解决方案。



<!--HONumber=Apr16_HO2-->


