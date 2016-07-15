---
title: "指定你的隐私要求"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: d02d3ec2-706a-4e03-977c-b7c06cbd4ebd
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d43860e838a40de05bdec73b00b6721ee634d7e5
ms.openlocfilehash: 519482cadc7f0054883b70dd0de20e25380ec1a6


---

# 指定你的隐私要求

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。


在上一步中，你定义了设备管理任务，其中包括设备管理和内容分发管理。 在此任务中，目标是定义对将驻留在移动设备上的公司内容的隐私要求。 

>[!TIP] 有关移动设备的内容分发的详细信息，请参阅混合环境中的移动设备和计算机的简化管理解决方案。

组织的隐私与合规性要求将因行业、适用法规和业务类型而异。 例如，你可能希望你的 MDM 解决方案允许你在移动设备上执行基本的硬件清单、软件清单、文件收集和软件分发。 默认情况下，通常支持硬件清单和软件分发。 

请记住，适用于客户端计算机的清单和软件分发的隐私问题也适用于移动设备。 

在选择移动设备管理解决方案前，请考虑你的独特隐私要求。 例如，请考虑如下事项：

- 客户端隐私：允许用户使用他们的移动设备连接到和使用公司资源也意味着他们必须了解组织的隐私策略以及这对他们的隐私有何影响。
    - 你是否需要为用户提供你公司的隐私策略，隐私策略应包括哪些内容？
        - 如果是，MDM 解决方案是否包括易于为用户提供隐私策略的功能？
    - MDM 解决方案是否将用户的移动设备信息或数据存储在云中？
        - 如果是，用户的隐私在云中如何维护？ 
- 谁有权访问数据？
- 如何使他们的数据保持隐私？
- 数据分类与合规性：定义公司数据如何构成以及它将如何被保护至关重要。 采用策略和机制来为数据分类应是计划的一部分，以便在管理移动设备时确保隐私。
    - 你是否可以标识或分类将驻留在移动设备上的公司文档或数据？
        - 如果是，支持哪些类型的数据或文档权限或许可？
    - 无论用户正在使用何种移动设备，该分类是否与数据或文档同步？
    - 哪些类型的数据或文档能够（或无法）被分类？
    - 合规性要求是否会影响你如何选择移动设备管理平台？
        - 如果是，请确保在选择移动设备管理平台之前枚举这些要求。

阅读 [Microsoft Online Services 隐私声明](http://www.microsoft.com/server-cloud/products/intune-trust-center/privacy.aspx)以更好地了解 Microsoft Cloud 服务（包括 Intune）如何维护用户隐私。


<!--HONumber=Jun16_HO4-->


