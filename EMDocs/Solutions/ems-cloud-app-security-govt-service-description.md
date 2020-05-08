---
title: Microsoft Cloud App Security 政府服务说明
description: Microsoft Cloud App Security 政府服务说明旨在用作我们的产品/服务的概述
keywords: ''
author: shsagir
ms.author: shsagir
manager: rkarlin
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.suite: ems
ms.openlocfilehash: 670d0cf9c07e0af3bbc282f0c5ca89a2b1c92da4
ms.sourcegitcommit: 9c743600314b5957bc8f70735e1d8d0cbdac0323
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82924483"
---
# <a name="microsoft-cloud-app-security-government-service-description"></a>Microsoft Cloud App Security 政府服务说明

## <a name="how-to-use-this-service-description"></a>如何使用此服务说明

《 Microsoft Cloud App Security 美国政府服务说明 ' 旨在作为 GCC 高环境中服务产品的概述，并涵盖商业产品/服务中的功能差异。

若要详细了解适用于 GCC 客户的 Microsoft Cloud App Security，请参阅[美国 Office 365 GCC 客户的 EMS](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description#ems-for-us-office-365-gcc-customers)。

## <a name="getting-started-with-microsoft-cloud-app-security-for-us-government-gcc-high"></a>适用于美国政府版的 Microsoft Cloud App Security 入门

Microsoft Cloud App Security GCC 的高产品/服务是在 Microsoft Azure 政府云的基础上构建的，旨在实现 Office 365 GCC 高的操作。 有关此服务以及如何使用该服务的完整详细信息，可在[Microsoft Cloud App Security 公开文档](https://docs.microsoft.com/cloud-app-security/)中找到。 应将公共文档用作部署和操作服务的起点，并提供以下服务说明详细信息，以及来自 GCC 高环境中功能或功能的更改。

若要开始，请使用 "[基本设置](https://docs.microsoft.com/cloud-app-security/general-setup)" 页访问 Microsoft Cloud App Security GCC 高门户，并确保配置了[网络要求](https://docs.microsoft.com/cloud-app-security/network-requirements)。 有关其他详细说明，请按照操作方法指南中的其他步骤进行操作。

## <a name="feature-variations-in-microsoft-cloud-app-security-gcc-high"></a>Microsoft Cloud App Security GCC 高

除非另有说明，否则新功能版本（包括预览功能，如[Microsoft Cloud App Security 的新增](https://docs.microsoft.com/cloud-app-security/release-notes)功能）将在 Microsoft Cloud App Security 商业环境中的三个月发行版中提供（除非另有说明）。

## <a name="api-connector"></a>API 连接器

目前不支持用于 AWS GovCloud 的 API 连接器和其他可能提供单独的政府云实例的 API 连接的应用程序。 支持适用于第三方应用程序的商业云实例的 API 连接器。

Azure 连接器和 Office 365 连接器适用于每个服务的美国政府实例。

## <a name="data-loss-prevention-dlp-features"></a>数据丢失防护（DLP）功能

通过 Microsoft Cloud App Security 内置 DLP 引擎提供内容检查，并支持检查敏感数据，如信用卡或社会保障号，这两者之间的其他敏感数据类型不同。 详细了解 Cloud App Security 中的[内置内容检查](https://docs.microsoft.com/cloud-app-security/content-inspection-built-in)。

**不支持以下 DLP 集成：**

- Microsoft 信息保护标签，提供跨 Office 365 和 Azure 信息保护的统一标签。
- 与 Microsoft 数据分类服务（DC）的本机集成

## <a name="conditional-access-app-control"></a>条件访问应用控制

Microsoft Cloud App Security 条件访问应用控制，这使组织能够使用 Microsoft Cloud App Security 反向代理功能实时监视和控制用户会话，而不能使用。
对于连接了 API 的应用程序，仍支持活动、文件和异常情况检测策略。 详细了解如何[通过 Microsoft Cloud App Security 中的策略来控制云应用](https://docs.microsoft.com/cloud-app-security/control-cloud-apps-with-policies)以获取其他信息。

## <a name="notifications-and-automation"></a>通知和自动化

此时不支持警报的管理员电子邮件通知，以及在检测到违规时发送给用户的通知。

## <a name="security-configuration-assessments"></a>安全配置评估

不支持 AWS 的安全配置评估。

## <a name="other-integrations"></a>其他集成

以下集成不可用：

- Microsoft Defender 高级威胁防护
- 以 Microsoft 安全分数形式呈现 Microsoft Cloud App Security 控件

## <a name="next-steps"></a>后续步骤

若要详细了解 Cloud App Security 并探索如何开始了解，请参阅[Cloud App Security 公用文档](https://docs.microsoft.com/cloud-app-security/)。
