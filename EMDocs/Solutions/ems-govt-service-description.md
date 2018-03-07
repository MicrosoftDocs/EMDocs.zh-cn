---
title: "适用于美国政府的企业移动性 + 安全性服务说明"
description: "EMS GCC 高级版计划需要每月订阅，并向每个用户授予许可证。"
keywords: 
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: ems
ms.technology: 
ms.assetid: de61a788-f45d-47bb-a047-e92b64b1ee03
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: da6b79835b9891b15fcb97d90f6d6263f231b356
ms.sourcegitcommit: 6399d25da998e54605082faff5f8b2304a851e4e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>适用于美国政府的企业移动性 + 安全性服务说明 
鉴于美国公共部门的独特要求变得愈加严格，Microsoft 为我们的美国政府客户创建了企业移动性 + 安全性计划。 本文档概述了特定于 EMS 计划的功能。  

## <a name="how-to-use-this-service-description"></a>如何使用本服务说明 
适用于美国政府的 EMS 服务说明旨在概述我们的产品/服务，并将涵盖以下内容：(1) 此产品/服务包含的服务和功能，(2) 政府产品/服务与我们现有的商业产品/服务有何不同，以及 (3) 我们当前的符合性承诺。 本文档定义了相较于 EMS 商业产品/服务的独特承诺以及各种差异。  

## <a name="ems-offers-for-us-government-and-office-365-interoperability"></a>适用于美国政府的 EMS 产品/服务与 Office 365 互操作性 
Office 365 当前在 GCC 和 GCC 高级版环境中都可用。 要了解有关这些产品/服务的详细信息，请参阅 Office 365 政府服务说明。 EMS 商业产品/服务可与 Office 365 GCC 完全互操作，此产品/服务当前以 FedRAMP 中等认证为目标。 EMS GCC 高级版产品/服务基于 Microsoft Azure 政府云而构建，旨在与 Office 365 GCC 高级版和 Office 365 DoD 产品/服务互操作。 EMS GCC 高级版产品/服务以 FedRAMP 高级认证为目标。  

|EMS 产品/服务|相应的 Office 365 政府产品/服务|符合性承诺|
|-----------|-----------|-----------|
|EMS（商业）</br>在 E3 和 E5 中可用|Office 365 GCC|FedRAMP 中等|
|EMS GCC 高级版</br>在 E3 和 E5 中可用|Office 365 GCC 高级版|FedRAMP 高级| 

> [!Note]    
> 实现 FedRAMP 符合性的目标日期是 2018 日历年。 

## <a name="about-ems-for-us-government"></a>关于适用于美国政府的 EMS 
EMS GCC 高级版计划需要每月订阅，并向每个用户授予许可证。 使用 EMS GCC 高级版的组织获益于以下独特功能：  

- 组织的内容与 Microsoft 商业 EMS 服务中的内容逻辑隔离。 

- 组织的内容存储在美国。 

- 只有经过筛选的 Microsoft 人员才可访问包含用户内容的 Microsoft 系统。 

- EMS GCC 高级版符合美国公共部门客户要求的常见认证和资格认可。 

## <a name="customer-eligibility"></a>客户资格 
EMS 政府产品/服务可供以下客户使用：(1) 美国联邦、州、地方、部落和属地政府实体，以及 (2) 处理需符合政府法规和要求的数据，且经过资格验证，适合使用 EMS 来满足这些要求的其他实体。 资格验证由 Microsoft 进行，验证过程中会确认处理的数据受政府管控。 验证可能需要证明已在美国国务院注册登记，或得到对处理数据有特定要求的政府实体的引荐。 此产品/服务仅限于拥有至少 500 个席位的客户。 续订客户的 EMS 合同时，需要重新验证资格。 对 EMS 资格有疑问的实体应咨询其帐户团队。  

## <a name="location-of-customer-data"></a>客户数据的位置 
EMS GCC 高级版服务从物理位置位于美国的数据中心提供。 所有内容都在物理位置仅位于美国的数据中心静态存储。  

## <a name="ems-gcc-high-and-third-party-services"></a>EMS GCC 高级版和第三方服务 
有多种 EMS 服务能够与第三方应用程序和服务无缝协作。 这些第三方应用程序和服务可能涉及在 EMS 基础结构之外的第三方系统上存储、传输和处理组织的客户内容，因此未涵盖在我们的符合性和数据保护承诺之内。 建议在评估第三方服务是否适用于你所在组织时查看第三方提供的隐私和符合性声明。  

## <a name="parity-with-ems-commercial-offerings"></a>EMS 商业产品/服务的奇偶校验 
尽管我们的目标是在 EMS GCC 高级版产品/服务中向政府客户提供所有商业特性和功能，但仍需要强调的是，某些功能还不可用。  
    
以下是截至 2018 年 2 月 EMS GCC 高级版与商业产品/服务之间已知的现有差异：  

- Microsoft Cloud App Security 目前暂未包含在 GCC 高级版的 EMS E5 计划中。   

- Azure Active Directory B2B。 

- 预配置了应用的 Azure Active Directory 库不用。 

- MFA FedRAMP 审核不同于 Azure AD FedRAMP 审核，并且延迟。 启动时，MFA 未使用 FedRAMP 认证，客户必须选择使用此服务。 

- 基于组的授权。 此功能当前在商业云中以预览版提供。 此功能在商业云中正式发布后，我们还会在 Azure Active Directory Premium GCC 高级版中提供此功能。 

- Office 365 移动应用尚未包含在 Office 365 GCC 高级版产品/服务中，因此 Intune 的移动应用程序管理功能未启用 

- AIP 更新  