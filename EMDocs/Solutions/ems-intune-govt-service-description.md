---
title: Microsoft Intune 政府服务说明
description: Intune 政府服务说明旨在用作我们的产品/服务的概述
keywords: ''
author: mlottner
ms.author: mlottner
manager: dougeby
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.suite: ems
ms.openlocfilehash: 83eab50cd4af65be5a28f3c0efaca7776ebd1fdb
ms.sourcegitcommit: 422f43a00933c66f17c85de243a1a3cf1a08cda2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "101831510"
---
# <a name="microsoft-intune-for-us-government-gcc-high-and-dod-service-description"></a>Microsoft Intune 美国政府版和 DoD 服务说明

## <a name="how-to-use-this-service-description"></a>如何使用此服务说明

Intune 美国政府服务说明旨在作为 GCC 高和 DoD 环境中服务产品的概述，并涵盖了商业产品/服务中的功能差异。

若要了解有关适用于 GCC 的 Intune 客户的详细信息，请参阅 [美国政府的 EMS 服务和 Microsoft 365 互操作性](ems-govt-service-description.md#ems-offers-for-us-government-and-microsoft-365-interoperability)。

## <a name="get-started-with-intune-for-us-government-gcc-high-and-dod"></a>适用于美国政府版和 DoD 的 Intune 入门

Intune GCC 高和 DoD 产品/服务是在 Microsoft Azure 政府云上构建的，旨在与 Microsoft 365 GCC 的高和 DoD 环境进行互操作。 有关此服务以及如何使用该服务的完整详细信息，请参阅 [Intune 公共文档](/intune/)。 公共文档应用作部署和操作服务的起点，并提供以下服务说明详细信息，以及从 GCC 高环境中的功能或功能进行的更改。

### <a name="feature-variations-in-intune-gcc-high-and-dod"></a>Intune GCC 高和 DoD 中的功能变化

- 适用于 GCC 高和 DoD 客户的 Intune 仅支持独立部署。
- 适用于 GCC 的 intune 高和 DoD 客户不支持通过 Intune 代理)  (旧版 PC 管理。 通过现代 MDM 渠道支持 Windows 10 的管理。
- 适用于 GCC 的 Intune 高和 DoD 客户不支持本地 Exchange Connector。
- Co-Management 支持仅适用于 Configuration Manager 版本1906或更高版本。
- 尽管计划正在进行，但目前尚不能使用 Windows Autopilot 和企业应用商店功能。
- 适用于 GCC 的 Intune 高不支持用于 macOS 设备的 Jamf Pro 和 Intune 集成。
- 适用于 GCC 的 Intune 高不支持 Android 和 iOS 设备的移动威胁防御连接器。
- Microsoft 端点管理器终结点分析和 Log Analytics 功能当前不适用于美国政府客户。
- 目前，我们的政府云客户无法使用诊断设置和工作簿。
- [使用 Windows 配置设计器的 windows 设备的批量注册](/mem/intune/enrollment/windows-bulk-enroll) 目前在 GCC High 中不受支持。
- 适用于 GCC 的 Intune 高不支持 [位置](/mem/intune/protect/use-network-locations) 功能。


## <a name="next-steps"></a>后续步骤
若要详细了解 Intune 并探索如何开始，请参阅 [Intune 公共文档](/intune/index)。