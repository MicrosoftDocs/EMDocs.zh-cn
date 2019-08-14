---
title: 适用于美国政府的企业移动性 + 安全性服务说明
description: EMS GCC 高级版计划需要每月订阅，并向每个用户授予许可证。
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/07/2019
ms.topic: article
ms.prod: ''
ms.service: ems
ms.suite: ems
ms.openlocfilehash: 43e2c8a925a42f2ff39802989dcca6fe231ea168
ms.sourcegitcommit: 393421ada426fc958125e310b92e9a84b31a9c2d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2019
ms.locfileid: "68937358"
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>适用于美国政府的企业移动性 + 安全性服务说明 
鉴于美国公共部门的独特要求变得愈加严格，Microsoft 为我们的美国政府客户创建了企业移动性 + 安全性计划 (EMS)。 本文档概述了特定于 EMS 计划的功能。  

## <a name="how-to-use-this-service-description"></a>如何使用本服务说明 
适用于美国政府的 EMS 服务说明旨在概述我们的产品/服务，并将涵盖以下内容：(1) 此产品/服务包含的服务和功能，(2) 政府产品/服务与我们的商业产品/服务有何不同，以及 (3) 我们当前的符合性承诺。 本文档定义了相较于 EMS 商业产品/服务的独特承诺以及各种差异。  

## <a name="ems-offers-for-us-government-and-office-365-interoperability"></a>适用于美国政府的 EMS 产品/服务与 Office 365 互操作性 

|EMS 美国政府产品/服务|托管服务的位置 |相应的 Office 365 政府产品/服务|符合性承诺|
|-----------|-----------|-----------|
|EMS for GCC</br>在 E3 和 E5 中可用*|Azure 商业云|Office 365 GCC|FedRAMP 中等|
|EMS for GCC 高级版</br>在 E3 和 E5 中可用*|Azure 政府云|Office 365 GCC 高级版|FedRAMP 高级| 

> [!Note]    
> E5 目前仅限于 Azure AD P2 和 Azure 信息保护 P2。  目前，GCC 或 GCC 高级版产品/服务中不包含 Microsoft Cloud App Security 和 Azure 高级威胁防护。  但是，GCC 客户可以选择在购买 EMS E5 SKU 时，附加 Microsoft Cloud App Security 的商业产品/服务和 Azure ATP 产品/服务（不符合相同的符合性标准）。

Office 365 当前在 GCC、GCC 高级版以及 DOD 环境中都可用。 要了解有关这些产品/服务的详细信息，请参阅 [Office 365 政府服务说明](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)。 

## <a name="ems-for-gcc"></a>EMS for GCC

EMS 商业产品/服务可与 Office 365 GCC 完全互操作。  Azure Active Directory P1/P2、Intune 和 Azure 信息保护 P1/P2 是此产品/服务经认证的 FedRAMP（中级）并满足 [GCC 条件](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。

## <a name="ems-for-gcc-high"></a>EMS for GCC 高级版

EMS for GCC 高级版产品/服务基于 Microsoft Azure 政府云而构建，旨在与 Office 365 GCC 高级版产品/服务互操作。 Azure Active Directory P1/P2、Intune 和 Azure 信息保护 P1/P2 是此产品/服务经认证的 FedRAMP（高级）。 （我们的目标是在 2019 日历年将 Microsoft Cloud App Security 和 Azure 高级威胁防护添加到此产品/服务中，等待 FedRAMP（高级）授权。）

GCC 高级版客户可根据不同的要求和管理需求使用 Intune 的一组独立终结点。  下面是 EMS 客户可使用的管理门户列表：
* Office 365 门户：[https://portal.office365.us](https://portal.office365.us)（用于管理用户、组和许可证）
* Azure/Intune 管理门户：[https://portal.azure.us](https://portal.azure.us)
* Intune Web 公司门户：[https://portal.manage.microsoft.us](https://portal.manage.microsoft.us)

使用 EMS for GCC 高级版的组织获益于以下独特功能：
* 组织的内容与 Microsoft 商业 EMS 服务中的内容物理隔离。
* 组织的内容存储在美国。
* 只有经过筛选的 Microsoft 人员才可访问包含用户内容的 Microsoft 系统。
* EMS GCC 高级版符合美国公共部门客户要求的常见认证和资格认可。

## <a name="customer-eligibility"></a>客户资格 
EMS 政府产品/服务可供以下客户使用：(1) 美国联邦、州、地方和部落政府实体，以及 (2) 处理需符合政府法规和要求的数据，且经过资格验证，适合使用 EMS 来满足这些要求的其他实体。 资格验证由 Microsoft 进行，验证过程中会确认处理的数据受政府管控。 EMS GCC 和 GCC 高级版的计划需要每月订阅，并向每个用户授予许可证。 对 EMS 资格有疑问的实体应咨询其帐户团队。  

## <a name="location-of-customer-data"></a>客户数据的位置 
适用于美国政府的 EMS 服务从物理位置位于美国的数据中心提供。 所有内容都在物理位置仅位于美国的数据中心静态存储。  

有多种 EMS 服务能够与某些第三方应用程序和服务无缝协作。 这些第三方应用程序和服务可能涉及在 EMS 基础结构之外的第三方系统上存储、传输和处理组织的客户内容，因此未涵盖在我们的符合性和数据保护承诺之内。 建议在评估第三方应用和服务是否适用于你所在组织时查看这些第三方提供的隐私和符合性声明。

## <a name="parity-with-ems-commercial-offerings"></a>EMS 商业产品/服务的奇偶校验 
尽管我们的目标是在适用于美国政府的 EMS 产品/服务中向政府客户提供所有商业特性和功能，但仍需要强调的是，某些功能还不可用。  
    
以下是截至 2019 年 2 月 EMS GCC 高级版与商业产品/服务之间已知的现有差异：  

- Microsoft Intune：

  - 仅支持独立部署。 它不支持使用 System Center Configuration Manager (SCCM) 进行混合设置。

  - 不支持旧版 PC 管理（使用 Intune 代理）。 通过现代 MDM 渠道支持 Windows 10 的管理。

  - 不支持本地 Exchange 连接器。

  - Configuration Manager 1906 及更高版本支持共同管理。

  - 虽然计划正在进行中，但目前政府客户无法使用 Windows Autopilo 和适用于企业的 Store 功能。

  - 政府客户无法使用某些 Office 365 移动应用。  可以在 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)上找到相关详细信息。

  - 目前政府客户无法使用 Lookout 移动威胁检测和电信费用管理合作伙伴解决方案。

- Azure 信息保护：

  - 有关当前不可用功能的列表，请访问 Azure 政府文档站点内的 [Azure 信息保护高级版页面](ems-aip-premium-govt-service-description.md)。

- Azure Active Directory：

  - 有关当前 Azure 政府中不可用功能的列表，请访问 Azure 政府文档站点的 [Azure Active Directory Premium 页面](/azure/azure-government/documentation-government-services-securityandidentity#azure-active-directory-premium-p1-and-p2)。
