---
# required metadata

title: 制定你的事件响应要求
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 6f9fd9b3-492b-48e1-871c-e5abefe1293a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 制定你的事件响应要求

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

尽管许多组织已经制定了事件响应 (IR) 计划，你应当检查以确保此计划包括移动设备以及当在这些设备上报告某个事件时需要执行什么步骤。 如果你的公司刚刚增加移动解决方案，则很可能当前 IR 计划未涵盖移动设备。 
如果你的组织没有 IR 计划，则与你的安全团队紧密合作以了解要求，从而正确提出恰当的问题并针对你的需求选择最佳的 MDM 解决方案很重要。 
 
>[!TIP]阅读[响应 IT 安全事件](https://technet.microsoft.com/library/cc700825.aspx)以更好地了解 IR 计划的最低要求。

在设计 MDM 解决方案时，请询问以下问题，确保在发生事件时可以管理移动设备。

- 你的组织是否有现有事件响应计划？
    - 如果是，它是否包含用于处理受损移动设备的进程和过程？
- 事件响应策略是否涵盖最终用户报告已丢失其移动设备的方案？
    - 是否允许擦除整个设备以避免数据泄露？ 
        - 如果是，你的公司是否对驻留在移动设备上的数据具有备份策略？
- 你的组织是否在公司拥有的设备和个人拥有的设备丢失时对其具有不同的过程？
    - 如果是，这些过程是什么？
    - 这些过程是否会影响 MDM 解决方案的选择？
- 如果用户丢失其个人拥有的移动设备，但他们未授权公司擦除整个设备，MDM 解决方案是否允许选择性设备擦除？
- 当移动设备受到破坏，并且你需要阻止该设备将恶意应用扩散到公司网络时，MDM 解决方案是否允许你强制执行可快速包含受损设备的策略？
- MDM 解决方案是否允许你针对潜在攻击进行规划，以便采取预防措施来解决问题？
- MDM 解决方案是否允许你使用管理控制台标识某个文件何时受恶意软件感染？



<!--HONumber=Apr16_HO2-->


