---
title: "设备监视选项"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 23cfc12a-fa96-4fb3-8de1-af4569e8cb71
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a16e90093c7571f3c098ce815a2b70ae03c080e3
ms.openlocfilehash: f543376b1e850c7d6e868c91d942aa8058e11b41


---

# 设备监视选项

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

监视和了解组织管理的所有移动设备的状态和配置有助于你发现问题和不遵守规定的情况，并管理设备清单。 如果没有对硬件、软件和合规性状态的详细报告，则无法确保设备策略是否存在以及是否正常运行。 主动监视有助于在小问题扩大化且开销增加前缓解这些问题。

[Intune ](/Intune/deploy-use/monitoring-and-reports-with-microsoft-intune)、[Office 365 的 MDM](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) 以及 Intune 和 ConfigMgr 的[混合部署](https://technet.microsoft.com/library/gg699377.aspx)都包括监视和报表，以帮助管理设备、用户以及你组织的策略和过程的合规性。 通过结合自定义报告使用内置报告，你可以在以下方面监视移动设备管理：

- 软件更新报告
- 软件清单报告
- 硬件清单报告
- 许可报告
- 不合规性报告

根据基础结构的设置方式，你可以创建各种报告来帮助监视组织。 基于 Intune 的监视和报告功能在 Office 365 的 MDM 和 Intune 独立部署报告中起主干作用。 在混合部署中，当 ConfigMgr 连接到 Intune 时，这些报告还可以与 ConfigMgr 的报告功能紧密集成。 每个产品均具有不同但互补的报告功能，如下所示。 请务必了解每个移动设备管理解决方案报告功能的细微差别，以有助于确保选择拥有所需报告的解决方案。

![集成移动设备监视和报告](./media/MDM_Figure_05.png)

**集成移动设备监视和报告**

提供给任务 2 中的问题的答案可以帮助你确定移动设备的监视和报告需求。 下面的列表显示了每个 MDM 解决方案中的监视和报告功能的优缺点。

## Intune（独立版）

**优点**

- 监视概述/仪表板
- 在直接托管的网络设备上检测到错误时发出警报
- Intune 服务 RSS 源会通知你服务存在的问题和即将进行的维护
- 带有阈值的三级警报（严重、警告、信息）和电子邮件警报通知
- 可以按设备类型筛选警报
- 可以查看任何托管设备的状态
- 提供关于不符合 IT 策略的设备的报表
- 可以监视以下方面的详细信息：
 - System (系统)
 - 操作系统
 - 存储
 - Exchange ActiveSync
 - 系统机箱
 - Network (网络)
 - 服务

**缺点**

- 仅限电子邮件警报，无基于文本或语音的警报

## Office 365 的 MDM

**优点**

- 监视概述/仪表板
- 带有阈值的三级警报（严重、警告、信息）和电子邮件警报通知
- 可以按设备类型筛选警报
- 可以查看任何托管设备的状态
- 提供关于不符合 IT 策略的设备的报表

**缺点**

- 仅限移动设备合规性状态报告

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 除了 Instune 独立版的所有监视和报告功能外，还包括以下内容：
 - 适用于组织所有设备（包括非移动设备和未注册 Intune 的设备）的基于阈值的全面合并监视和报告
 - SQL Server Reporting Services (SSRS) 的高级报告功能和 Reporting Services 报告生成器提供的丰富创作体验

**缺点**

- 需要其他配置，以将 Intune 与本地 ConfigMgr 基础结构相连接
- 对于尚未配置当前 ConfigMgr 基础结构的组织，将需要在与 Intune 集成前进行规划、安装和配置

查看以下内容，了解有关移动设备监视选项的详细信息：

- Intune：**[如何监视移动设备](https://technet.microsoft.com/library/jj733634.aspx)**和[管理报告](/Intune/deploy-use/monitoring-and-reports-with-microsoft-intune)
- ConfigMgr：[监视移动设备](https://technet.microsoft.com/library/gg682128.aspx)和[管理报告](https://technet.microsoft.com/library/gg699377.aspx)
- Office 365 的 MDM：[概述和设备管理任务](https://technet.microsoft.com/en-us/library/ms.o365.cc.devicepolicy.aspx)


<!--HONumber=Jul16_HO3-->


