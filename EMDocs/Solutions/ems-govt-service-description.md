---
title: 适用于美国政府的企业移动性 + 安全性服务说明
description: EMS GCC 高级版计划需要每月订阅，并向每个用户授予许可证。
keywords: ''
author: shsagir
ms.author: shsagir
manager: dougeby
ms.date: 01/12/2020
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.suite: ems
ms.openlocfilehash: e82e70f920fe56634d47cdb3a89e64c844c9540a
ms.sourcegitcommit: 76cad8e05a1a149fa5e344e680e6f11c08d89110
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79133944"
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>适用于美国政府的企业移动性 + 安全性服务说明
鉴于美国公共部门的独特要求变得愈加严格，Microsoft 为我们的美国政府社区客户创建了企业移动性 + 安全性计划 (EMS)。 本文档概述了特定于这些 EMS 计划的功能。

## <a name="how-to-use-this-service-description"></a>如何使用本服务说明
适用于美国政府的 EMS 服务说明旨在概述我们提供的适用产品/服务，包含以下内容：(1) 不同产品/服务中包含的服务和功能；(2) 适用于美国政府的产品/服务与商业产品/服务的区别；(3) 我们当前的合规性授权。

## <a name="customer-eligibility"></a>客户资格
美国政府产品/服务可供以下客户使用：(1) 美国联邦、州、地方和部落政府实体，以及 (2) 处理需符合政府法规和要求的数据，且经过资格验证，适合使用服务来满足这些要求的其他实体。 资格验证由 Microsoft 进行，验证过程中会确认处理的数据受政府管控。 适用于 GCC、GCC High 和 DOD 客户的 EMS 计划需要每月订阅，并向每个用户授予许可证。 对资格有疑问的实体应咨询其帐户团队。 

## <a name="ems-offers-for-us-government-and-office-365-interoperability"></a>适用于美国政府的 EMS 产品/服务与 Office 365 互操作性

有关企业移动性 + 安全性中的每个产品及其计划的详细信息，请访问[文档资源](https://docs.microsoft.com/enterprise-mobility-security/)和[比较计划和定价](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing)。

|EMS 美国政府产品/服务|托管服务的位置|可互操作的 Office 365 政府社区云 (GCC) 产品/服务|
|-----------|-----------|-----------|
|EMS for GCC</br>*在 E3 和 E5 中可用**|Azure 商业云|Office 365 GCC|
|EMS for GCC 高级版</br>*在 E3 和 E5 中可用**|Azure 政府云|Office 365 GCC 高级版</br>Office 365 DOD|
|EMS for DoD</br>*在 E3 和 E5 中可用**|Azure 政府云|Office 365 DOD|

> [!Note]
> \* E5 产品/服务目前仅限于面向 GCC 和 DoD 客户的 Azure AD Premium 2 和 Azure 信息保护 P2（除了 Microsoft Intune 以外）。 目前，面向 Office 365 GCC 或 DoD 客户的产品/服务中不包含 Microsoft Cloud App Security 和 Azure 高级威胁防护 (Azure ATP)。  但是，GCC 客户可以选择在购买 EMS E5 许可证时，附加 Microsoft Cloud App Security 的商业产品/服务和 Azure ATP。

## <a name="ems-for-us-gcc-customers"></a>面向美国 GCC 客户的 EMS
Azure Active Directory P1/P2、Microsoft Intune 和 Azure 信息保护 P1/P2 托管在 Azure 商业环境中，且可以与 Office 365 GCC 平台互操作。  这些服务经过 FedRAMP-High 认证，且满足所有 [GCC 符合性](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc#us-government-community-compliance)属性。

GCC 客户可以选择在购买 EMS E5 SKU 时，附加 Microsoft Cloud App Security 的商业产品/服务和 Azure ATP。 Microsoft Cloud App Security 和 Azure ATP 是由 Azure Commercial FedRAMP High Authorization to Operate (ATO) 涵盖的商业服务/产品，但可能不符合其他 [GCC 符合性](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc#us-government-community-compliance)属性，例如 CJIS 背景筛查、IRS 1075 以及由美国政府筛选的人员访问客户内容。  Microsoft 产品和服务的符合性服务/产品列表可在 [ 信任中心](https://www.microsoft.com/en-us/trustcenter/compliance/complianceofferings)找到。  

## <a name="ems-for-us-gcc-high-and-dod-customers"></a>面向美国 GCC High 和 DoD 客户的 EMS
面向美国 GCC High 和 DoD 客户的 EMS 产品/服务基于 Microsoft [Azure 政府](https://docs.microsoft.com/azure/azure-government/documentation-government-welcome)云而构建，旨在与 Office 365 GCC High 和 DoD 环境互操作。 EMS E5 套件适用于 GCC High 和 DoD 客户，但 Microsoft Cloud App Security 和 Azure 高级威胁防护仅适用于 GCC High 客户。 Azure Active Directory P1/P2、Microsoft Intune、Azure 信息保护 P1/P2、Microsoft Cloud App Security 和 Azure ATP 是经认证的 FedRAMP（高级）。

GCC High 和 DoD 客户可根据不同的要求和管理需求使用 Intune 的一组独立终结点。 下面是美国 GCC High 和 DoD 客户可使用的 EMS 管理门户的列表。 取决于服务可用性：

- Office 365 门户： https://portal.office365.us （用于管理用户、组和许可证）
- Azure/Intune 管理门户： https://portal.azure.us
- Intune Web 公司门户： https://portal.manage.microsoft.us
- Microsoft Cloud App Security 门户： https://portal.cloudappsecurity.us  
- Azure 高级威胁防护 (Azure ATP) 门户： https://portal.atp.azure.us  

### <a name="parity-with-commercial"></a>等同于商业版 
尽管我们的目标是在适用于美国政府的产品/服务中向政府客户提供所有商业特性和功能，但 Azure 政府环境中某些功能还不可用。 可在以下产品页面上查看截至 2019 年 11 月面向 GCC High 和 DoD 客户提供的商业产品/服务和 EMS 产品/服务之间现有的已知差距： 
- Azure Active Directory： 
  - 有关当前 Azure 政府中不可用功能的列表，请访问 Azure 政府文档站点的 [Azure Active Directory Premium 页面](https://docs.microsoft.com/azure/azure-government/documentation-government-services-securityandidentity#azure-active-directory-premium-p1-and-p2)。 
- Azure 信息保护： 
  - 有关 Azure 政府中当前不可用功能的列表，请访问 [Azure 信息保护高级版](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)页面。 
- Microsoft Intune： 
  - 有关 Azure 政府中当前不可用功能的列表，请访问 [Microsoft Intune] 页面 (https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-intune-govt-service-description) )。 
- Azure 高级威胁防护：
  - 有关 Azure 政府中当前不可用功能的列表，请访问 [Azure ATP](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-azure-atp-govt-service-description) 页面。
- Microsoft Cloud App Security：
  - 有关 Azure 政府中当前不可用功能的列表，请访问 [Microsoft Cloud App Security](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description) 页面。

## <a name="location-of-customer-data"></a>客户数据的位置

### <a name="us-government-gcc-customers"></a>美国政府 GCC 客户
当前可用于美国政府客户的 EMS 服务（Azure AD P1/P2、Intune 和 Azure 信息保护 P1/2）是由物理位置位于美国的数据中心提供的。 组织的客户静态数据存储在美国。 GCC 客户也可以选择在购买 EMS E5 许可证时，附加 Microsoft Cloud App Security 和 Azure ATP 商业产品/服务。 （它们不是美国 GCC 服务，不符合所有 GCC 属性。）若要了解 Microsoft 存储与 Microsoft Cloud App Security 相关的客户静态数据的位置，查看[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。 要了解 Microsoft 存储与 Azure ATP（也是一种商业服务）相关的客户静态数据的位置，请参阅 Azure ATP 的[产品文档](https://docs.microsoft.com/azure-advanced-threat-protection/atp-technical-faq#do-i-have-the-flexibility-to-select-where-to-store-my-data)。

### <a name="us-government-gcchigh-and-dod-customers"></a>美国政府 GCC High 和 DoD 客户
使用面向美国政府 GCC High 和 DoD 产品/服务的 EMS 的组织可从以下功能中获益： 
- 组织的客户内容与 Microsoft 商业服务中的客户内容物理隔离。 
- 组织的客户内容存储在美国。 
- 只有经过筛选的 Microsoft 人员才可访问组织的客户内容。 
- 符合美国公共部门客户必须符合的认证和认可，包括美国国防部安全要求指南、国防联邦采购补充条例 (DFARS) 和国际武器贸易条例 (ITAR) 

有关详细信息，请参阅[ Microsoft 信任中心](https://products.office.com/en-us/where-is-your-data-located?ms.officeurl=datamaps&geo=All#office-ContentAreaHeadingTemplate-bkjgypc)页。 

### <a name="third-party-apps-and-services"></a>第三方应用和服务

有多种 EMS 服务能够与某些第三方应用程序和服务无缝协作。 这些第三方应用程序和服务可能涉及在 EMS 基础结构之外的第三方系统上存储、传输和处理组织的数据或内容，因此未涵盖在我们的符合性和数据保护承诺之内。 建议在评估第三方应用和服务是否适用于你所在组织时查看这些第三方提供的隐私和符合性声明。

有关详细信息，请参阅 [Microsoft 365 政府] (https://docs.microsoft.com/enterprise-mobility-security/) )。 