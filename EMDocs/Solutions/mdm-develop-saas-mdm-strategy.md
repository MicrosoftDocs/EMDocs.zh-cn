---
title: "制定 SaaS 移动设备管理策略"
description: "本文旨在帮助客户制定适用于使用 Microsoft 企业移动性 + 安全性实现的移动设备管理的服务型软件策略。"
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: b3cefcc5-b045-48f9-91f5-6d282a4428f3
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 735874e0f5c30628fbc4bdcdce18e6db3a2ec735


---

# <a name="develop-saas-mobile-device-management-strategy"></a>制定 SaaS 移动设备管理策略

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

## <a name="identify-your-saas-solution-requirements"></a>确定你的 SaaS 解决方案要求

根据你对任务 1 中的问题的回答，你应该能够确定需要在移动设备管理解决方案中支持的 SaaS 解决方案。 下面的表 20 将有助于你了解每个 SaaS 解决方案的优点和缺点：

## <a name="intune-standalone"></a>Intune（独立版）

**优点**

- 作为多租户提供，公有云体系结构
- 扩展以支持最多 50,000 台移动设备
- 不需要对本地基础结构、硬件或软件进行任何额外投资
- 每天进行更新和功能改进。 每月进行主要的特性和功能增强。
- 服务可以分配给特定地理位置的数据中心
- 数据中心故障转移可以限制于特定地理位置
- 经认证并且符合大部分行业和政府标准服务级别协议 (SLA)，受到财务支持，如果服务或功能不可用，将免除每月费用

**缺点**

- 不支持私有云实例
- 如果你需要支持 50,000 台以上的移动设备，你需要将 Itune 连接到 ConfigMgr 以管理其他设备

## <a name="mdm-for-office-365"></a>Office 365 的 MDM

**优点**

- 与 Office 365 商业租户紧密集成，为移动设备和 Office 365 租户服务（Exchange Online、SharePoint Online 和 Skype for Business Online）提供一个单一管理控制台。
- 在 Office 365 多租户（公用）或私人（专用）平台类型中提供
- 没有额外的用户或设备授权成本，默认包含在 Office 365 商业（企业、公司、教育和政府）计划中

**缺点**

- 不支持管理非移动操作系统
- （仅）在将本地管理平台用于非移动设备时，预配移动设备还有其他管理界面。

## <a name="hybrid-intune-with-configmgr"></a>混合版（带 ConfigMgr 的 Intune）

**优点**

- 除了 Intune 独立版的所有优点外，还包括以下优点：Intune（基于云的设备管理服务）与 ConfigMgr（本地设备管理平台）之间的集成
- 通过 Intune 连接性支持移动设备的高级设备预配选项
- 通过平台扩展（自动或自定义）扩展到本地 ConfigMgr 基础结构的新 Intune 服务特性和功能。

**缺点**

- 要求其他配置要求，以将 Intune 与本地 ConfigMgr 基础结构相连接。
- 对于尚未配置当前 ConfigMgr 基础结构的组织，需要在与 Intune 集成之前进行规划、安装和配置。

若要了解在每个平台中进行选择性擦除后删除哪些数据以及对设备上的剩余数据的影响，请务必阅读文章**[通过 Microsoft Intune 使用远程擦除、远程锁定或密码重置帮助保护数据](https://technet.microsoft.com/library/jj676679.aspx)**。 如果你有混合环境，请参考文章[如何使用 Configuration Manager 远程擦除移动设备](https://technet.microsoft.com/library/dn956981.aspx)以了解如何使用 ConfigMgr 完成此任务。

有关 SaaS 解决方案功能和要求的更多详细信息，请务必查看 **[Microsoft Intune 的服务说明](https://technet.microsoft.com/library/dn600286.aspx)**主题，以了解适用于 [ ffice 365](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) 的 MDM 与[混合](https://technet.microsoft.com/library/jj884158.aspx) Intune 和 Configmgr 基础结构中的 SaaS 支持之间的差异。



<!--HONumber=Nov16_HO4-->


