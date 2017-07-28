---
title: "确定 SaaS 连接要求"
description: "本文帮助确定使用企业移动性 + 安全性解决方案规划实施移动设备管理时的服务型软件连接要求。"
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6afbce4c-7500-4387-a19c-dff52c152097
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 9cc654fadde9494e364d3bc1513bc5bf3c78f6a2
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2017
---
# <a name="identify-saas-connectivity-requirements"></a>确定 SaaS 连接要求

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

你连接本地基础结构的方式将影响使用所有 MDM 解决方案管理用户和设备身份的方式：Intune、适用于 Office 365 的 MDM 与混合 Intune 和 ConfigMgr 部署。 Intune 和适用于 Office 365 的 MDM 都利用了由 Azure Active Directory 服务提供的目录服务体系结构。 当你设计移动设备管理解决方案中的身份管理支持时，与 Azure 的集成为你提供了很大的灵活性。

如下面的列表所示，将本地目录服务与 Azure 连接是启用单一登录和统一目录帐户管理的关键要求。 单一登录使用户可以更加容易地连接到在本地和云中的公司资源。 使用单个位置可使管理员更轻松地管理帐户。 对于移动访问，在 Azure 和本地目录服务之间同步目录帐户属性和凭据可允许用户在其移动设备上进行身份验证，以访问由适用于 Office 365 的 MDM 或 Intune 管理的资源。

![集成身份管理的概述](./media/MDM_Figure_15.png)

**集成身份管理的概述**

根据你对任务 2 中的问题的回答，你应该能够确定 SaaS 解决方案需要如何连接到移动设备管理解决方案的本地客户端管理平台。 下面的列表将帮助你了解将本地基础结构与 SaaS 解决方案连接的优点和缺点。

## <a name="intune-standalone"></a>Intune（独立版）

**优点**

- 与 Azure Active Directory 紧密集成，用于管理用户和设备身份和身份验证
- 支持可利用现有本地帐户凭据的用户凭据自我管理和单一登录体验
- 支持对数千个预先集成的 SaaS 应用程序进行单一登录访问
- 通过为本地和云应用程序强制执行基于规则的多因素身份验证 (MFA) 来支持应用程序访问安全性

**缺点**

- 高级目录服务连接性特性和功能需要与 Azure Active Directory Premium 配对

## <a name="mdm-for-office-365"></a>Office 365 的 MDM

**优点**

- 与 Office 365 租户集成，后者使用 Azure Active Directory 主干管理用户和设备身份和身份验证
- 作为将服务与 Office 365 连接的一部分，可以连接本地目录服务
- 支持可利用现有本地帐户凭据的用户自我管理和单一登录体验
- 通过使用 Azure MFA 服务支持设备注册的多重身份验证

**缺点**

- 不支持与其他 SaaS 解决方案或应用程序的移动应用程序管理集成

## <a name="hybrid-intune-with-configmgr"></a>混合版（带 ConfigMgr 的 Intune）

**优点**

- 除了 Intune 独立版的所有优点外，还包括以下优点：
 - 通过 ConfigMgr 基础结构与本地目录服务直接集成

**缺点**

- 对于尚未配置当前 ConfigMgr 基础结构的组织，将需要在与 Intune 集成前进行规划、安装和配置
- 对于具有 ConfigMgr 的组织，需要满足其他本地部署要求和配置更改。
