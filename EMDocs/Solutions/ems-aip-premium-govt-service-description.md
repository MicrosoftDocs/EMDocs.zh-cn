---
title: Azure 信息保护高级版政府服务说明
description: Azure 信息保护高级政府服务说明旨在作为我们的产品/服务的概述
keywords: ''
author: mlottner
ms.author: mlottner
manager: dougeby
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: rights-management
ms-suite: ems
ms.openlocfilehash: ee099c3e76ec5c6e2e32fd33d84c8b872abf16b3
ms.sourcegitcommit: d1b80e2cfecbeca4ed2a9a082acf0c3c34fd4ee1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82106757"
---
# <a name="azure-information-protection-premium-government-service-description"></a>Azure 信息保护高级版政府服务说明 

## <a name="how-to-use-this-service-description"></a>如何使用本服务说明 

Azure 信息保护高级版政府服务说明旨在作为我们在 GCC 高和 DoD 环境中的产品/服务的概述，与 Azure 信息保护高级商业产品/服务的不同之处。 若要详细了解适用于 GCC 的 Azure 信息保护，请参阅[美国政府和 Office 365 互操作性的 EMS 产品/服务](ems-govt-service-description.md#ems-offers-for-us-government-and-office-365-interoperability)的说明。

## <a name="azure-information-protection-premium-government-and-third-party-services"></a>Azure 信息保护高级版政府和第三方服务 

有多种 Azure 信息保护高级版服务能够与第三方应用程序和服务无缝协作。 这些第三方应用程序和服务可能涉及在 Azure 信息保护高级版基础结构之外的第三方系统上存储、传输和处理组织的客户内容，因此未涵盖在我们的符合性和数据保护承诺之内。 建议在评估第三方服务是否适用于你所在组织时查看第三方提供的隐私和符合性声明。 

## <a name="parity-with-azure-information-protection-premium-commercial-offerings"></a>与 Azure 信息保护高级版商业产品/服务具有相同的功能 

尽管我们的目标是在 Azure 信息保护高级版 GCC High 和 DoD 产品/服务中向政府客户提供所有商业特性和功能，但仍需要强调缺少了一些功能。 

这些功能也就是截至 2019 年 5 月 Azure 信息保护高级版 GCC High/DoD 与商业产品/服务之间已知的现有差异： 

* 文档跟踪和撤销当前不可用。 

* 只有 Office 365 Pro Plus（版本 9126.1001 或更高版本）才支持分类和标记加载项。 Office 2010、Office 2013 和其他 Office 2016 版本将不受支持。 

* 只有 Office 365 Pro Plus（版本 9126.1001 或更高版本）才支持信息权限管理 (IRM)。 Office 2010、Office 2013 和其他 Office 2016 版本将不受支持。 

* 当前不支持从 Active Directory Rights Management Services (AD RMS) 迁移到 Azure 信息保护。 

* 当前不支持在商业云中向用户共享受保护的文档和电子邮件。 包括商业云中的 Office 365 用户、商业云中的非 Office 365 用户以及具有个人 RMS 许可的用户。 

* 当前不支持在 SharePoint Online（受 IRM 保护的站点和库）中使用 Information Rights Management。 

* Rights Management 连接器当前不可用。

* AD RMS 的移动设备扩展当前不可用。


## <a name="configuring-azure-information-protection-for-gcc-high-and-dod-customers"></a>为 GCC High 和 DoD 客户配置 Azure 信息保护

### <a name="enable-rights-management-for-the-tenant"></a>为租户启用 Rights Management
必须为租户启用 Rights Management Service，才能正常加密。

* 检查是否启用了 Rights Management Service
  * 以管理员身份启动 PowerShell
  * 运行 `Install-Module aadrm`（如果未安装 AADRM 模块的话） 
  * 使用 `Connect-aadrmservice -environmentname azureusgovernment` 连接到服务
  * 运行 `(Get-AadrmConfiguration).FunctionalState` 并检查状态是否为 `Enabled`
* 如果功能状态为 `Disabled`，则运行 `Enable-Aadrm`

### <a name="dns-configuration-for-encryption-windows"></a>用于加密的 DNS 配置 (Windows)
Office 客户端应用必须连接到 GCC High/DoD 实例并从中启动，才能正常加密。 若要将客户端应用重定向到正确的服务实例，租户管理员必须使用 Azure RMS URL 的相关信息来配置 DNS SRV 记录。 如果没有 DNS SRV 记录，客户端应用会默认尝试连接到公有云实例，但连接会失败。

此外，假设用户将使用基于租户拥有域的用户名（例如：joe@contoso.us）登录，而不是 onmicrosoft 用户名（例如：joe@contoso.onmicrosoft.us）。 用户名中的域名用于将 DNS 重定向到正确的服务实例。

* 获取 Rights Management 服务 ID 
  * 以管理员身份启动 PowerShell 
  * 运行 `Install-Module aadrm`（如果未安装 AADRM 模块的话） 
  * 使用 `Connect-aadrmservice -environmentname azureusgovernment` 连接到服务
  * 运行 `(Get-aadrmconfiguration).RightsManagementServiceId`，以获取 Rights Management 服务 ID
* 登录 DNS 提供程序，并导航到域的 DNS 设置，以添加新的 SRV 记录
  * 服务 = `_rmsredir` 
  * 协议 = `_http` 
  * 名称 = `_tcp` 
  * 目标 = `[GUID].rms.aadrm.us`（其中，GUID 是 Rights Management 服务 ID） 
  * 端口 = `80` 
  * 优先级、权重、秒、TTL = 默认值 
* 在 [Azure 门户](https://portal.azure.us/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中，将自定义域与租户相关联。 这会在 DNS 中添加一个条目，在 DNS 设置中添加的值可能需要几分钟的时间才能得到验证。  
* 使用相应的全局管理员凭据登录 Office 管理中心，并添加域（例如：contoso.us）以用于创建用户。 在验证过程中，可能需要执行其他一些 DNS 更改。 验证完成后，即可创建用户。

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>用于加密的 DNS 配置（Mac、iOS、Android）
* 登录 DNS 提供程序，并导航到域的 DNS 设置，以添加新的 SRV 记录
  * 服务 = `_rmsdisco` 
  * 协议 = `_http` 
  * 名称 = `_tcp` 
  * 目标 = `api.aadrm.us` 
  * 端口 = `80` 
  * 优先级、权重、秒、TTL = 默认值 


### <a name="aip-apps-configuration"></a>AIP 应用配置

Windows 上的 AIP 应用需要有特殊的注册表项，才能将应用指向 GCC High/DoD 的正确服务实例。  

| 注册表节点 | HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP |
| --- | --- |
| 名称 | WebServiceUrl |
| 值 | https://api.informationprotection.azure.us |
| 类型 | REG_SZ (String) |


## <a name="firewalls-and-network-infrastructure"></a>防火墙和网络基础结构

如果你具有配置为允许特定连接的防火墙或类似的干预网络设备，请使用这些设置来确保 Azure 信息保护的流畅通信。

- 若要启用 Azure 信息保护经典客户端以下载标签和标签策略，请执行以下操作：允许通过 HTTPS **API.INFORMATIONPROTECTION.AZURE.US** URL。

- 请勿终止到**Rms.aadrm.us** URL 的 TLS 客户端到服务连接（例如，要执行数据包级别检查）。 

您可以使用以下 PowerShell 命令来帮助您确定客户端连接在到达 Azure Rights Management 服务之前是否终止：
 
    $request = [System.Net.HttpWebRequest]::Create("https://admin.aadrm.us/admin/admin.svc")
    $request.GetResponse()
    $request.ServicePoint.Certificate.Issuer

结果应显示发证 CA 来自 Microsoft CA，例如： `CN=Microsoft Secure Server CA 2011, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`。 如果你看到的颁发 CA 名称不是 Microsoft，则很可能是你安全的客户端到服务连接被终止，需要在防火墙上重新配置。


## <a name="service-tags"></a>服务标记

请确保允许访问以下**服务标记**的所有端口：
*    AzureInformationProtection
*    AzureActiveDirectory
*    AzureFrontDoor
