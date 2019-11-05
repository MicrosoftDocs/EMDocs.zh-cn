---
title: 适用于美国政府的企业移动性 + 安全性服务说明
description: EMS GCC 高级版计划需要每月订阅，并向每个用户授予许可证。
keywords: ''
author: mlottner
ms.author: mlottner
manager: dougeby
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.suite: ems
ms.openlocfilehash: e60ed45c1f7f97b340de644afe684a7d5cd95d89
ms.sourcegitcommit: fd344763857d03303006b9da4f6931ed320d27ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462507"
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>适用于美国政府的企业移动性 + 安全性服务说明
鉴于美国公共部门的独特要求变得愈加严格，Microsoft 为我们的美国政府社区客户创建了企业移动性 + 安全性计划 (EMS)。 本文档概述了特定于这些 EMS 计划的功能。

## <a name="how-to-use-this-service-description"></a>如何使用此服务说明
"美国政府服务说明" 的 EMS 设计用于概述我们适用的产品/服务，并将介绍：（1）哪些服务和功能包含在不同的产品/服务中产品/服务和（3）我们当前的符合性授权。

## <a name="customer-eligibility"></a>客户资格
美国政府产品/服务可供以下客户使用：(1) 美国联邦、州、地方和部落政府实体，以及 (2) 处理需符合政府法规和要求的数据，且经过资格验证，适合使用服务来满足这些要求的其他实体。 资格验证由 Microsoft 进行，验证过程中会确认处理的数据受政府管控。 适用于 GCC、GCC High 和 DOD 客户的 EMS 计划需要每月订阅，并向每个用户授予许可证。 对资格有疑问的实体应咨询其帐户团队。 

## <a name="ems-offers-for-us-government-and-office-365-interoperability"></a>EMS 为美国政府和 Office 365 互操作性提供

有关企业移动性 + 安全性中的每个产品及其计划的详细信息，请访问[文档资源](https://docs.microsoft.com/enterprise-mobility-security/)并[比较计划和定价](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing)。

|EMS 美国政府版产品/服务|托管服务的位置|可互操作的 Office 365 政府社区云 (GCC) 产品/服务|
|-----------|-----------|-----------|
|EMS for GCC</br>*在 E3 和 E5 中可用**|Azure 商业云|Office 365 GCC|
|EMS for GCC 高级版</br>*在 E3 和 E5 中可用**|Azure 政府云|Office 365 GCC 高级版</br>Office 365 DOD|
|用于 DOD 的 EMS</br>*在 E3 和 E5 中可用**|Azure 政府云|Office 365 DOD|

> [!Note]
> \* E5 产品/服务仅限 Azure AD Premium 2 和 Azure 信息保护 P2 （除了 Microsoft Intune）用于 GCC 和 DOD 客户。 Microsoft Cloud App Security 和 Azure 高级威胁防护（Azure ATP）当前不包含在 Office 365 GCC 或 DoD 客户的产品/服务中。  但是，购买 EMS E5 许可证后，GCC 客户可以选择使用 Microsoft Cloud App Security 和 Azure ATP 的附加商业产品/服务。

## <a name="ems-for-us-gcc-customers"></a>适用于美国 GCC 客户的 EMS
Azure Active Directory P1/P2、Microsoft Intune 和 Azure 信息保护 P1/P2 托管在 Azure 商业环境中，且可以与 Office 365 GCC 平台互操作。  这些服务经过 FedRAMP-High 认证，且满足所有 [GCC 符合性](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc#us-government-community-compliance)属性。

GCC 客户可以选择在购买 EMS E5 SKU 时，附加 Microsoft Cloud App Security 的商业产品/服务和 Azure ATP。 Microsoft Cloud App Security 和 Azure ATP 是 Azure 商业 FedRAMP 高授权操作（ATO）涵盖的商业产品/服务，但可能不符合其他[GCC 相容性](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc#us-government-community-compliance)特性，如 CJIS 背景屏蔽、IRS 1075 和访问美国政府屏蔽式人员的客户内容。  Microsoft 产品和服务的符合性服务/产品列表可在 [ 信任中心](https://www.microsoft.com/en-us/trustcenter/compliance/complianceofferings)找到。  

## <a name="ems-for-us-gcc-high-and-dod-customers"></a>适用于美国 GCC 和 DoD 客户的 EMS
适用于美国 GCC 和 DOD 客户的 EMS 产品基于 Microsoft [Azure 政府](https://docs.microsoft.com/azure/azure-government/documentation-government-welcome)云而构建，旨在与 OFFICE 365 GCC 高和 DOD 环境结合工作。 EMS E5 套件适用于 GCC 高客户和 DoD 客户，但是 Microsoft Cloud App Security 和 Azure 高级威胁防护仅适用于 GCC 高客户。 Azure Active Directory P1/P2、Microsoft Intune 和 Azure 信息保护 P1/P2 认证 FedRAMP-高。

基于不同需求和管理需求，GCC 高和 DOD 客户可以使用一组单独的终结点。 下面是可供我们的 GCC 高级和 DOD 客户使用的 EMS 管理门户列表。 取决于服务可用性：

- Office 365 门户： https://portal.office365.us （用于管理用户、组和许可证）
- Azure/Intune 管理门户： https://portal.azure.us
- Intune Web 公司门户： https://portal.manage.microsoft.us
- Microsoft Cloud App Security 门户： https://portal.cloudappsecurity.us  
- Azure 高级威胁防护（Azure ATP）门户： https://portal.atp.azure.us  

### <a name="parity-with-commercial"></a>与商业的奇偶校验 
虽然我们的目标是向政府客户提供所有商业特性和功能，但仍有一些功能在 Azure 政府版环境中不可用。 在以下产品页中提供了我们的商业产品/服务与适用于 GCC 11 月版和 DOD 客户之间的已知现有空缺： 
- Azure Active Directory： 
  - 有关当前 Azure 政府中不可用功能的列表，请访问 Azure 政府文档站点的 [Azure Active Directory Premium 页面](https://docs.microsoft.com/azure/azure-government/documentation-government-services-securityandidentity#azure-active-directory-premium-p1-and-p2)。 
- Azure 信息保护： 
  - 有关 Azure 政府版中当前不可用的功能的列表，请访问[Azure 信息保护高级版](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)页面。 
- Microsoft Intune： 
  - 有关 Azure 政府版中当前不可用的功能的列表，请访问 [Microsoft Intune] 页（ https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-intune-govt-service-description) 。 
- Azure 高级威胁防护：
  - 有关 Azure 政府版中当前不可用的功能的列表，请访问[AZURE ATP](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-azure-atp-govt-service-description)页面。
- Microsoft Cloud App Security：
  - 有关 Azure 政府版中当前不可用的功能的列表，请访问[Microsoft Cloud App Security](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description)页。

## <a name="location-of-customer-data"></a>客户数据的位置

### <a name="us-government-gcc-customers"></a>美国政府版客户
当前可用于美国政府客户的 EMS 服务（Azure AD P1/P2、Intune 和 Azure 信息保护 P1/2）是从物理位于美国中的数据中心提供的。 组织的客户静态数据存储在美国。 购买 EMS E5 许可证后，GCC 客户还可以选择添加 Microsoft Cloud App Security 和 Azure ATP 的商业产品/服务。 （这些是不是美国的 GCC 服务，不遵守所有的 GCC 属性。）有关 Microsoft 在与 Microsoft Cloud App Security （商业服务）上存储静态客户数据的位置的信息，请参阅[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。 要了解 Microsoft 存储与 Azure ATP（也是一种商业服务）相关的客户静态数据的位置，请参阅 Azure ATP 的[产品文档](https://docs.microsoft.com/azure-advanced-threat-protection/atp-technical-faq#do-i-have-the-flexibility-to-select-where-to-store-my-data)。

### <a name="us-government-gcchigh-and-dod-customers"></a>美国政府 GCCHigh 和 DoD 客户
对于美国政府版，使用 EMS 作为高和 DOD 产品/服务的组织从以下功能中受益： 
- 贵组织的客户内容与 Microsoft 商业服务中的客户内容在物理上是隔离的。 
- 贵组织的客户内容存储在美国中。 
- 对组织的客户内容的访问权限仅限于 Microsoft 人员的筛选。 
- 符合美国公共部门客户要求的认证和资格认可，包括美国国防部安全要求指导原则、防御联邦收购法规补充（DFARS）和国际交通Arm 条例（ITAR） 

有关详细信息，请参阅[ Microsoft 信任中心](https://products.office.com/en-us/where-is-your-data-located?ms.officeurl=datamaps&geo=All#office-ContentAreaHeadingTemplate-bkjgypc)页。 

### <a name="third-party-apps-and-services"></a>第三方应用和服务

有多种 EMS 服务能够与某些第三方应用程序和服务无缝协作。 这些第三方应用程序和服务可能涉及在 EMS 基础结构之外的第三方系统上存储、传输和处理组织的数据或内容，因此未涵盖在我们的符合性和数据保护承诺之内。 建议在评估第三方应用和服务是否适用于你所在组织时查看这些第三方提供的隐私和符合性声明。

有关详细信息，请参阅 [Microsoft 365 政府] （ https://docs.microsoft.com/enterprise-mobility-security/) 。 