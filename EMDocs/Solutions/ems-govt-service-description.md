---
title: 适用于美国政府的企业移动性 + 安全性服务说明
description: EMS GCC 高级版计划需要每月订阅，并向每个用户授予许可证。
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: ems
ms.suite: ems
ms.openlocfilehash: a9f886f5d9d0851c79ab163cff22125c1aebd6f0
ms.sourcegitcommit: cfa80b7829abb2fca321ebb9cfcd96dbd8c06990
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "29721441"
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>适用于美国政府的企业移动性 + 安全性服务说明 
鉴于美国公共部门的独特要求变得愈加严格，Microsoft 为我们的美国政府客户创建了企业移动性 + 安全性计划 (EMS)。 本文档概述了特定于 EMS 计划的功能。  

## <a name="how-to-use-this-service-description"></a>如何使用本服务说明 
适用于美国政府的 EMS 服务说明旨在概述我们的产品/服务，并将涵盖以下内容：(1) 此产品/服务包含的服务和功能，(2) 政府产品/服务与我们现有的商业产品/服务有何不同，以及 (3) 我们当前的符合性承诺。 本文档定义了相较于 EMS 商业产品/服务的独特承诺以及各种差异。  

## <a name="ems-offers-for-us-government-and-office-365-interoperability"></a>适用于美国政府的 EMS 产品/服务与 Office 365 互操作性 
Office 365 当前在 GCC 和 GCC 高级版环境中都可用。 要了解有关这些产品/服务的详细信息，请参阅 Office 365 政府服务说明。 EMS 商业产品/服务可与 Office 365 GCC 完全互操作，此产品/服务当前以 FedRAMP 中等认证为目标。 

EMS GCC 高级版产品/服务基于 Microsoft Azure 政府云而构建，旨在与 Office 365 GCC 高级版和 Office 365 DoD 产品/服务互操作。 EMS GCC 高级版产品/服务以 FedRAMP 高级认证为目标。 （Microsoft Cloud App Security 和 Azure 高级威胁防护目前不在此优惠的范围内。）

|EMS 产品/服务|相应的 Office 365 政府产品/服务|符合性承诺|
|-----------|-----------|-----------|
|EMS（商业）</br>在 E3 和 E5 中可用|Office 365 GCC|FedRAMP - 中等*|
|EMS GCC 高级版</br>在 E3 和 E5 中可用|Office 365 GCC 高级版|FedRAMP 高级| 

> [!Note]    
> 实现 FedRAMP 符合性的目标日期是日历年 2018 年的 H2。 （*这不包括 Microsoft Cloud App Security 或 Azure 高级威胁防护的认证。）

## <a name="about-ems-for-us-government"></a>关于适用于美国政府的 EMS 
EMS GCC 高级版计划需要每月订阅，并向每个用户授予许可证。 使用 EMS GCC 高级版的组织获益于以下独特功能：  

- 组织的内容与 Microsoft 商业 EMS 服务中的内容物理隔离。 

- 组织的内容存储在美国。 

- 只有经过筛选的 Microsoft 人员才可访问包含用户内容的 Microsoft 系统。 

- EMS GCC 高级版符合美国公共部门客户要求的常见认证和资格认可。 

## <a name="customer-eligibility"></a>客户资格 
EMS 政府产品/服务可供以下客户使用：(1) 美国联邦、州、地方和部落政府实体，以及 (2) 处理需符合政府法规和要求的数据，且经过资格验证，适合使用 EMS 来满足这些要求的其他实体。 资格验证由 Microsoft 进行，验证过程中会确认处理的数据受政府管控。 此产品/服务仅限于拥有至少 500 个席位的客户。 对 EMS 资格有疑问的实体应咨询其帐户团队。  

## <a name="location-of-customer-data"></a>客户数据的位置 
EMS GCC 高级版服务从物理位置位于美国的数据中心提供。 所有内容都在物理位置仅位于美国的数据中心静态存储。  

## <a name="ems-gcc-high-and-third-party-services"></a>EMS GCC 高级版和第三方服务 
有多种 EMS 服务能够与第三方应用程序和服务无缝协作。 这些第三方应用程序和服务可能涉及在 EMS 基础结构之外的第三方系统上存储、传输和处理组织的客户内容，因此未涵盖在我们的符合性和数据保护承诺之内。 建议在评估第三方服务是否适用于你所在组织时查看第三方提供的隐私和符合性声明。  

## <a name="parity-with-ems-commercial-offerings"></a>EMS 商业产品/服务的奇偶校验 
尽管我们的目标是在 EMS GCC 高级版产品/服务中向政府客户提供所有商业特性和功能，但仍需要强调的是，某些功能还不可用。  
    
以下是截至 2018 年 9 月 EMS GCC 高级版与商业产品/服务之间已知的现有差异：  

- Azure Active Directory 的应用程序:

  - B2B

  - 预配置了应用的 Azure Active Directory 库不用。 

  - MFA FedRAMP 审核不同于 Azure AD FedRAMP 审核，并且延迟。 启动时，MFA 未使用 FedRAMP 认证，客户必须选择使用此服务。 

- Microsoft Intune：

  - 仅支持独立部署。 不支持使用 SCCM 的混合设置。

  - 不支持旧版 PC 管理（使用 Intune 代理）。 通过现代 MDM 渠道支持 Windows 10 的管理。

  - 不支持本地 Exchange 连接器。

  - 虽然计划正在进行中，但目前政府客户无法使用 Windows Autopilo 和适用于企业的 Store 功能。

  - 目前不提供共同管理支持，但政府客户将可以在以后使用此功能。


- Azure 信息保护：

  - 文档跟踪和撤销将不可用。

  - 只有 Office 365 Pro Plus（版本 9126.1001 或更高版本）才支持分类和标记加载项。 不支持 Office 2010，Office 2013 和其他 Office 2016 版本。

  - 只有 Office 365 Pro Plus（版本 9126.1001 或更高版本）才支持信息权限管理 (IRM)。 不支持 Office 2010，Office 2013 和其他 Office 2016 版本。

  - 不支持从 Active Directory Rights Management Services (AD RMS) 迁移到 Azure 信息保护。

  - 不支持 iOS 和 Android 上的 Azure 信息保护查看器应用。

  - 不支持在商业云中向用户共享受保护的文档和电子邮件。 包括商业云中的 Office 365 用户、商业云中的非 Office 365 用户以及具有个人 RMS 许可的用户。

  - SharePoint Online 不支持信息权限管理。 受 IRM 保护的站点和库将不可用。 

- 基于组的授权。 此功能当前在商业云中以预览版提供。 此功能在商业云中正式发布后，我们还会在 Azure Active Directory Premium GCC 高级版中提供此功能。

- 目前，GCC 高级版的 EMS E5 产品中不包含 Microsoft Cloud App Security 和 Azure 高级威胁防护。
