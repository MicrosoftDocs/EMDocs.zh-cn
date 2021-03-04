---
title: 适用于美国政府的企业移动性 + 安全性服务说明
description: EMS GCC 高级版计划需要每月订阅，并向每个用户授予许可证。
author: shsagir
ms.author: shsagir
manager: dougeby
ms.date: 03/03/2021
ms.topic: article
ms.service: microsoft-intune
ms.suite: ems
ms.openlocfilehash: 4626ceebf9e2dcc09d609cc4623c733f76458e7c
ms.sourcegitcommit: 422f43a00933c66f17c85de243a1a3cf1a08cda2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "101831537"
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>适用于美国政府的企业移动性 + 安全性服务说明

鉴于美国公共部门的独特要求变得愈加严格，Microsoft 为我们的美国政府社区客户创建了企业移动性 + 安全性计划 (EMS)。 本文档概述了特定于这些 EMS 计划的功能。

## <a name="how-to-use-this-service-description"></a>如何使用此服务说明

"美国政府服务说明" 的 EMS 设计用于概述我们适用的产品/服务，并将介绍： (1) 哪些服务和功能包含在不同的产品/服务中， (2) 美国政府产品/服务与我们的商业产品/服务有何不同，以及 (的当前符合性授权。

## <a name="customer-eligibility"></a>客户资格

美国政府产品/服务可供以下客户使用：(1) 美国联邦、州、地方和部落政府实体，以及 (2) 处理需符合政府法规和要求的数据，且经过资格验证，适合使用服务来满足这些要求的其他实体。 资格验证由 Microsoft 进行，验证过程中会确认处理的数据受政府管控。 适用于 GCC、GCC 高 (DoD 的 EMS 计划 DoD) 客户是每月订阅，并按用户许可。 对资格有疑问的实体应咨询其帐户团队。

## <a name="ems-offers-for-us-government-and-microsoft-365-interoperability"></a>EMS 为美国政府和 Microsoft 365 互操作性提供

有关企业移动性 + 安全性中的每个产品及其计划的详细信息，请访问 [文档资源](/enterprise-mobility-security/) 并 [比较计划和定价](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing)。

|EMS 美国政府版产品/服务|托管服务的位置|Microsoft 365 政府社区云 (GCC) 提供 () |
|-----------|-----------|-----------|
|EMS for GCC</br>*可用于 E3 和 E5**|Azure 商业云|Microsoft 365 GCC|
|EMS for GCC 高级版</br>*可用于 E3 和 E5**|Azure 政府云|Microsoft 365 GCC 高</br>Microsoft 365 DoD|
|用于 DoD 的 EMS</br>*可用于 E3 和 E5**|Azure 政府云|Microsoft 365 DoD|

> [!Note]
> * E5 产品/服务仅限 Azure AD Premium 2 和 Azure 信息保护 P2 (，以及针对 GCC 和 DoD 客户的 Microsoft Intune) 。 Microsoft Cloud App Security 当前不包含在产品/服务的 Microsoft 365 GCC 客户中。 但是，在购买 EMS E5 许可证时，GCC 客户可以选择添加 Microsoft Cloud App Security 的商业产品/服务。

## <a name="ems-for-us-gcc-customers"></a>适用于美国 GCC 客户的 EMS

Azure Active Directory P1/P2、Microsoft Intune 和 Azure 信息保护 P1/P2 在 Azure 商业环境中托管，并可与 Microsoft 365 GCC 平台互操作。 这些服务的认证 FedRAMP-高。

购买 EMS E5 SKU 后，GCC 客户可以选择 Microsoft Cloud App Security 的附加商业产品/服务。 Microsoft Cloud App Security 是一种商业产品/服务，可 (ATO) 运行，但可能不符合其他 [GCC 相容性](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc#us-government-community-compliance) 特性，例如 CJIS 背景屏蔽、IRS 1075，以及由美国政府屏蔽人员访问客户内容。  Microsoft 产品和服务的符合性服务/产品列表可在 [ 信任中心](https://www.microsoft.com/trustcenter/compliance/complianceofferings)找到。

## <a name="ems-for-us-gcc-high-and-dod-customers"></a>适用于美国 GCC 和 DoD 客户的 EMS

适用于美国 GCC 和 DoD 客户的 EMS 产品基于 Microsoft [Azure 政府](/azure/azure-government/documentation-government-welcome) 云而构建，旨在与 Microsoft 365 GCC 的高级和 DoD 环境进行操作。 EMS E5 套件适用于 GCC 高客户和 DoD 客户。 Azure Active Directory P1/P2、Microsoft Intune、Azure 信息保护 P1/P2、Microsoft Cloud App Security 和用于标识的 Defender 身份验证 FedRAMP-高。

基于不同需求和管理需求，GCC 高和 DoD 客户可以使用一组单独的终结点。 下表列出了可用于我们的 GCC (的 EMS 管理门户，具体取决于服务可用性) ：

- Microsoft 365 门户： https://portal.office365.us 用于用户、组和许可证管理的 (") 
- Azure/Intune 管理门户：https://portal.azure.us
- Intune Web 公司门户：https://portal.manage.microsoft.us
- Microsoft Cloud App Security 门户： https://portal.cloudappsecurity.us
- 用于标识门户的 Defender： https://portal.atp.azure.us

### <a name="parity-with-commercial"></a>与商业的奇偶校验

虽然我们的目标是向政府客户提供所有商业特性和功能，但仍有一些功能在 Azure 政府版环境中不可用。 从2019年11月起，我们的商业产品/服务与适用于适用于 GCC 11 月的知名客户的产品/服务之间存在已知的现有差距：

- Azure Active Directory：
  - 有关当前 Azure 政府中不可用功能的列表，请访问 Azure 政府文档站点的 [Azure Active Directory Premium 页面](/azure/azure-government/documentation-government-services-securityandidentity#azure-active-directory-premium-p1-and-p2)。
- Azure 信息保护：
  - 有关 Azure 政府版中当前不可用的功能的列表，请访问 [Azure 信息保护高级版](./ems-aip-premium-govt-service-description.md) 页面。
- Microsoft Intune：
  - https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-intune-govt-service-description)有关 Azure 政府版中当前不可用的功能的列表，请访问 [Microsoft Intune] 页面 (。
- 用于标识的 Defender：
  - 有关 Azure 政府版中当前不可用的功能的列表，请访问用于 [标识的 Defender](./ems-mdi-govt-service-description.md) 页。
- Microsoft Cloud App Security：
  - 有关 Azure 政府版中当前不可用的功能的列表，请访问 [Microsoft Cloud App Security](./ems-cloud-app-security-govt-service-description.md) 页。

## <a name="location-of-customer-data"></a>客户数据的位置

### <a name="us-government-gcc-customers"></a>美国政府版客户

当前提供给美国政府客户的 EMS 服务 (Azure AD P1/P2、Intune 和 Azure 信息保护 P1/2) 是从物理位置位于美国的数据中心提供的。 贵组织的客户数据存储在美国中。 购买 EMS E5 许可证后，GCC 客户还可以选择 Microsoft Cloud App Security 的附加商业产品/服务。  (这不是美国 GCC 服务，并且不符合) 的所有 GCC 属性。 有关 Microsoft 在与 Microsoft Cloud App Security （商业服务）上存储静态客户数据的位置的信息，请参阅 [联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。

### <a name="us-government-gcc-high-and-dod-customers"></a>美国政府版和 DoD 客户

对于美国政府版，使用 EMS 作为高和 DoD 产品/服务的组织从以下功能中受益：

- 贵组织的客户内容与 Microsoft 商业服务中的客户内容在物理上是隔离的。
- 组织的客户内容存储在美国境内。
- 只有经过筛选的 Microsoft 人员才能访问组织的客户内容。
- 符合美国公共部门客户（包括美国国防部安全要求指导原则、防御联邦收购条例 (DFARS) 和国际流量 (ITAR) 的认证和资格认可

有关详细信息，请参阅[ Microsoft 信任中心](https://products.office.com/where-is-your-data-located?ms.officeurl=datamaps&geo=All#office-ContentAreaHeadingTemplate-bkjgypc)页。

### <a name="third-party-apps-and-services"></a>第三方应用和服务

有多种 EMS 服务能够与某些第三方应用程序和服务无缝协作。 这些第三方应用程序和服务可能涉及在 EMS 基础结构之外的第三方系统上存储、传输和处理组织的数据或内容，因此不包括在我们的符合性和数据保护承诺之内。 建议在评估第三方应用和服务是否适用于你所在组织时查看这些第三方提供的隐私和符合性声明。

有关详细信息，请参阅 [Microsoft 365 政府](https://www.microsoft.com/microsoft-365/government)。
