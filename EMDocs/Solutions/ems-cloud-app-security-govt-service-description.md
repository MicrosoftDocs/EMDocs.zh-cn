---
title: Microsoft Cloud App Security 政府服务说明
description: Microsoft Cloud App Security 政府服务说明旨在用作我们的产品/服务的概述
keywords: ''
author: shsagir
ms.author: shsagir
manager: rkarlin
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.suite: ems
ms.openlocfilehash: c8b0bf7c4e4d687f8441c0aba71ebf55d6a108a2
ms.sourcegitcommit: 422f43a00933c66f17c85de243a1a3cf1a08cda2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "101831473"
---
# <a name="microsoft-cloud-app-security-government-service-description"></a>Microsoft Cloud App Security 政府服务说明

## <a name="how-to-use-this-service-description"></a>如何使用此服务说明

《 Microsoft Cloud App Security 美国政府服务说明 ' 旨在提供 GCC (DoD) 环境中的服务产品的概述，并涵盖了商业产品/服务的功能差异。 有关适用于 GCC 客户的 Microsoft Cloud App Security 的详细信息，请参阅 [MICROSOFT 365 GCC 客户的 EMS](ems-govt-service-description.md#ems-for-us-gcc-high-and-dod-customers)。

## <a name="getting-started-with-microsoft-cloud-app-security-for-us-government-offerings"></a>适用于美国政府产品/服务的 Microsoft Cloud App Security 入门

适用于 GCC 高客户和 DoD 客户的 Microsoft Cloud App Security 产品基于 Microsoft Azure 政府云而构建，旨在与 Microsoft 365 GCC 高和 DoD 环境之间进行操作。 有关服务以及如何使用这些服务的完整详细信息，请参阅 [Microsoft Cloud App Security 公开文档](/cloud-app-security/)。 应将公共文档用作部署和操作服务的起点，并提供以下服务说明详细信息以及来自 GCC 高级或 DoD 环境中的功能和功能的更改。

若要开始使用，请使用 " [基本设置](/cloud-app-security/general-setup) " 页访问 Microsoft Cloud App Security GCC 高版或 DoD 门户，并确保配置了 [网络要求](/cloud-app-security/network-requirements) 。 若要将 Cloud App Security 配置为使用你自己的密钥来加密它在静止时收集的数据，请参阅 [使用你自己的密钥加密 Cloud App Security 静态数据 (BYOK) ](ems-cloud-app-security-govt-service-byok.md)。 有关其他详细说明，请按照操作方法指南中的其他步骤进行操作。

> [!NOTE]
> 数据加密当前仅适用于特定 Microsoft Cloud App Security 政府产品/服务。

## <a name="feature-variations-in-microsoft-cloud-app-security-us-government-offerings"></a>Microsoft Cloud App Security 美国政府产品/服务的功能差异

除非另有说明，否则新功能版本（包括预览功能，如 [Microsoft Cloud App Security 的新增](/cloud-app-security/release-notes)功能）将在 Microsoft Cloud App Security 商业环境中的三个月发行版中提供，除非另有说明。

## <a name="api-connector"></a>API 连接器

目前不支持用于 AWS GovCloud 的 API 连接器和其他可能提供单独的政府云实例的 API 连接的应用程序。 支持适用于第三方应用程序的商业云实例的 API 连接器。

Azure 连接器和 Microsoft 365 连接器适用于每个服务的美国政府实例。

## <a name="notifications-and-automation"></a>通知和自动化

此时不支持警报的管理员电子邮件通知，以及在检测到违规时发送给用户的通知。

## <a name="azure-sentinel-integration"></a>Azure Sentinel 集成

目前不支持 Microsoft Cloud App Security 和 Azure Sentinel 之间的集成。

## <a name="other-integrations"></a>其他集成

以下集成不可用：

- 用于终结点的 Microsoft Defender
- 以 Microsoft 安全分数形式呈现 Microsoft Cloud App Security 控件

## <a name="next-steps"></a>后续步骤

若要详细了解 Cloud App Security 并探索如何开始了解，请参阅 [Cloud App Security 公用文档](/cloud-app-security/)。