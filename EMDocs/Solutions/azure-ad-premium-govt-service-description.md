---
title: Azure Active Directory Premium 政府服务说明
description: Azure Active Directory Premium 政府计划需要每月订阅，并向每个用户授予许可证。
keywords: 标识
author: arob98
ms.author: mtillman
manager: mtillman
ms.date: 12/21/2017
ms.topic: get-started-article
ms.prod: ''
ms.service: active-directory
ms.technology: ''
ms.assetid: 112289b0-0336-4cc0-b471-42fc2c015c64
ms.reviewer: ''
ms.suite: ''
ms.custom: ''
ms.openlocfilehash: 7eb4740e44a5b4104de7d39667e9653e29213315
ms.sourcegitcommit: 4401a878f88cc60b3cfd90a915747fe37e333014
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
ms.locfileid: "30848166"
---
# <a name="azure-active-directory-premium-government-service-description"></a>Azure Active Directory Premium 政府服务说明

为了响应美国公共部门不断变化的独特需求，Microsoft 创建了 Azure Active Directory Premium 政府计划（也称为“Azure Active Directory Premium 政府”）。 本文档概述了特定于 Azure Active Directory Premium 政府的功能。 

## <a name="how-to-use-this-service-description"></a>如何使用本服务说明

Azure Active Directory Premium 政府服务说明用于概述我们的产品/服务，介绍了以下内容：(1) 此产品/服务包含的服务和功能，(2) 政府产品/服务与我们现有的商业产品/服务有何不同，以及 (3) 我们当前的符合性承诺。 本文档定义了相较于 Azure Active Directory Premium 商业产品/服务的独特承诺以及各种差异。

## <a name="about-azure-active-directory-premium-government-environments"></a>关于 Azure Active Directory Premium 政府环境

Azure Active Directory Premium 政府计划需要每月订阅，并向每个用户授予许可证。 使用 Azure Active Directory Premium 政府的组织可受益于下列独特的功能：

* 组织的内容与 Microsoft 商业 Azure Active Directory Premium 服务中的内容逻辑隔离。
* 组织的内容存储在美国。
* 只有经过筛选的 Microsoft 人员才可访问包含用户内容的 Microsoft 系统。
* Azure Active Directory Premium 政府符合美国公共部门客户要求的常见认证和资格认可。

## <a name="customer-eligibility"></a>客户资格 

Azure Active Directory Premium 政府可供以下客户使用：(1) 美国联邦、州、地方、部落和属地政府实体，以及 (2) 处理需符合政府法规和要求的数据，且经过资格验证，适合使用 Azure Active Directory Premium 政府来满足这些要求的其他实体。 资格验证由 Microsoft 进行，验证过程中会确认处理的数据受政府管控。 验证可能需要证明已在美国国务院注册登记，或得到对处理数据有特定要求的政府实体的引荐。 此产品/服务仅限于拥有至少 500 个席位的客户。 续订客户的 Azure Active Directory Premium 政府合同时，需要重新验证资格。 对 Azure Active Directory Premium 政府资格有疑问的实体应咨询其帐户团队。

## <a name="location-of-customer-data"></a>客户数据的位置

Azure Active Directory Premium 政府服务从物理位置位于美国的数据中心提供。 所有内容都在物理位置仅位于美国的数据中心静态存储。

## <a name="azure-active-directory-premium-government-and-third-party-services"></a>Azure Active Directory Premium 政府服务和第三方服务

有多种 Azure Active Directory Premium 服务能够与第三方应用程序和服务无缝协作。 这些第三方应用程序和服务可能涉及在 Azure Active Directory Premium 基础结构之外的第三方系统上存储、传输和处理组织的客户内容，因此未涵盖在我们的符合性和数据保护承诺之内。 建议在评估第三方服务是否适用于你所在组织时查看第三方提供的隐私和符合性声明。

## <a name="azure-active-directory-premium-government-offers-and-office-365-interoperability"></a>Azure Active Directory Premium 政府产品/服务和 Office 365 互操作性

Office 365 当前在 GCC 和 GCC 高级版环境中都可用。 要了解有关这些产品/服务的详细信息，请参阅 Office 365 政府[服务说明](https://technet.microsoft.com/library/mt774581.aspx)。 Azure Active Directory Premium 商业产品/服务可与 Office 365 GCC 完全互操作，此产品/服务当前以 FedRAMP 中等认证为目标。 Azure Active Directory Premium GCC 高级版产品/服务基于 [Microsoft Azure 政府云](https://docs.microsoft.com/azure/azure-government/documentation-government-welcome)而构建，旨在与 Office 365 GCC 高级版和 Office 365 DoD 产品/服务互操作。 Azure Active Directory Premium GCC 高级版产品/服务以 FedRAMP 高级认证为目标。

|Azure Active Directory Premium 政府产品/服务|相应的 Office 365 政府产品/服务|符合性承诺|
|-----------|-----------|-----------|
|Azure Active Directory Premium P1/P2（商业）|Office 365 <br/> GCC|FedRAMP 中等|
|Azure Active Directory Premium P1/P2 GCC 高级版|Office 365 <br/> GCC 高级版|FedRAMP 高级|

> [!NOTE]
> 实现 FedRAMP 符合性的目标日期是日历年 2018 年

## <a name="parity-with-azure-active-directory-premium-commercial-offerings"></a>与 Azure Active Directory Premium 商业产品/服务具有相同的功能

尽管我们的目标是在 Azure Active Directory Premium GCC 高级版产品/服务中向政府客户提供所有商业特性和功能，但仍需要强调缺少了一些功能。 

这些功能即截至 2017 年 12 月 Azure Active Directory Premium GCC 高级版与商业产品/服务之间已知的现有差异： 
* Azure Active Directory B2B。
* 预配置了应用的 Azure Active Directory 库不用。
* MFA FedRAMP 审核不同于 Azure AD FedRAMP 审核，并且延迟。 启动时，MFA 未使用 FedRAMP 认证，客户必须选择使用此服务。
* 基于组的授权。 此功能当前在商业云中以预览版提供。 此功能在商业云中正式发布后，我们还会在 Azure Active Directory Premium GCC 高级版中提供此功能。

