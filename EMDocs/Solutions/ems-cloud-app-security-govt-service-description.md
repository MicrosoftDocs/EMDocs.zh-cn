---
title: Microsoft Cloud App Security 政府服务说明
description: Microsoft Cloud App Security 政府服务说明用于概述我们提供的产品/服务
keywords: ''
author: shsagir
ms.author: shsagir
manager: rkarlin
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.suite: ems
ms.openlocfilehash: 3e122d51c6711a8638e81c4539b666835425ff4f
ms.sourcegitcommit: 76cad8e05a1a149fa5e344e680e6f11c08d89110
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79133927"
---
# <a name="microsoft-cloud-app-security-government-service-description"></a>Microsoft Cloud App Security 政府服务说明

## <a name="how-to-use-this-service-description"></a>如何使用本服务说明

Microsoft Cloud App Security 美国政府服务说明用于概述 GCC High 环境中的服务产品，并介绍与商用产品/服务的功能差异。

若要详细了解面向 GCC 客户的 Microsoft Cloud App Security，请参阅[面向美国 Office 365 GCC 客户的 EMS](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description#ems-for-us-office-365-gcc-customers)。

## <a name="getting-started-with-microsoft-cloud-app-security-for-us-government-gcc-high"></a>适用于美国政府 GCC High 的 Microsoft Cloud App Security 入门

Microsoft Cloud App Security GCC High 产品/服务基于 Microsoft Azure 政府云生成，旨在与 Office 365 GCC High 互操作。 若要全面地详细了解此服务及其用法，请参阅 [Microsoft Cloud App Security 公共文档](https://docs.microsoft.com/cloud-app-security/)。 应首先阅读公共文档以开始部署和操作服务，并参考以下服务说明，其中详细说明了 GCC High 环境的功能及其变化。

若要开始使用，请使用[基本设置](https:/docs.microsoft.com/cloud-app-security/general-setup)页访问 Microsoft Cloud App Security GCC High 门户，并确保已按[网络要求](https://docs.microsoft.com/cloud-app-security/network-requirements)中的内容完成配置。 若要了解其他详细说明，请按操作指南中的其他步骤操作。

## <a name="feature-variations-in-microsoft-cloud-app-security-gcc-high"></a>Microsoft Cloud App Security GCC High 中的功能变化

除非另有说明，否则在 Microsoft Cloud App Security 商业环境中发布新功能版本（包括在 [Microsoft Cloud App Security 新增功能](https://docs.microsoft.com/cloud-app-security/release-notes)中记录的预览功能）后的三个月内，将在 GCC High 中提供。

## <a name="api-connector"></a>API 连接器

目前不支持用于 AWS GovCloud 和其他连接了 API 的应用程序（可能同时会提供单独的政府云实例）的 API 连接器。 支持适用于第三方应用程序的商业云实例的 API 连接器。

Azure 连接器和 Office 365 连接器适用所有服务的美国政府实例。

## <a name="data-loss-prevention-dlp-features"></a>数据丢失防护 (DLP) 功能

可通过 Microsoft Cloud App Security 内置 DLP 引擎进行内容检查，并支持检查敏感数据，如信用卡或社会安全号码，以及许多其他敏感数据类型。 详细了解 Cloud App Security 中的[内置内容检查](https://docs.microsoft.com/cloud-app-security/content-inspection-built-in)。

**不支持下列 DLP 集成：**

- Microsoft 信息保护标签，它提供用于 Office 365 和 Azure 信息保护的统一标签。
- 与 Microsoft 数据分类服务 (DCS) 的本机集成

## <a name="conditional-access-app-control"></a>条件访问应用控件

Microsoft Cloud App Security 条件访问应用控件（它使组织能够使用 Microsoft Cloud App Security 反向代理功能实时监视和控制用户会话）不可用。
对于连接了 API 的应用程序，仍支持活动、文件和异常情况检测策略。 有关更多详细信息，请参阅[如何在 Microsoft Cloud App Security 中使用策略来控制云应用](https://docs.microsoft.com/cloud-app-security/control-cloud-apps-with-policies)。

## <a name="notifications-and-automation"></a>通知和自动化

目前不支持发生警报时的管理员电子邮件通知，也不支持在检测到违规时向用户发送通知。

## <a name="security-configuration-assessments"></a>安全配置评估

不支持 Azure 和 AWS 的安全配置评估。

## <a name="other-integrations"></a>其他集成

不提供以下集成：

- Microsoft Defender 高级威胁防护
- 在 Microsoft 安全功能分数中显示 Microsoft Cloud App Security 控件

## <a name="next-steps"></a>后续步骤

若要详细了解 Cloud App Security 并探索如何开始操作，请参阅 [Cloud App Security 公共文档](https://docs.microsoft.com/cloud-app-security/)。
