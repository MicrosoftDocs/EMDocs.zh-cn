---
title: Azure 信息保护高级版政府服务说明
description: Azure 信息保护高级政府服务说明旨在作为我们的产品/服务的概述
keywords: ''
author: batamig
ms.author: bagol
manager: rkarlin
ms.date: 03/07/2021
ms.topic: article
ms.prod: ''
ms.service: rights-management
ms-suite: ems
ms.openlocfilehash: 9b997c904b751a1137c33cc9322aaa8101d008b4
ms.sourcegitcommit: c91598c63b0fdcb725556c957a726209009ebbfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2021
ms.locfileid: "102443924"
---
# <a name="azure-information-protection-premium-government-service-description"></a>Azure 信息保护高级版政府服务说明

> [!NOTE]
> 若要提供统一且简化的客户体验，Azure 门户中的 **Azure 信息保护经典客户端** 和标签管理将于2021年9月31日 **在 azure 门户中** 被弃用。 
>
>此时间范围允许当前的 Azure 信息保护 GCC、GCC 和 DoD 客户使用 Microsoft 信息保护统一标签平台过渡到我们的统一标签解决方案。 有关详细信息，请参阅[官方弃用通知](https://aka.ms/aipclassicsunset)。

## <a name="how-to-use-this-service-description"></a>如何使用本服务说明

Azure 信息保护统一标签适用于 GCC、GCC 高和 DoD 客户。

Azure 信息保护高级版政府服务说明旨在作为我们在 GCC 高和 DoD 环境中的产品/服务的概述，与 Azure 信息保护高级商业产品/服务的不同之处。

若要详细了解适用于 GCC 和 GCC 高客户的 Azure 信息保护，请参阅 [美国政府和 Microsoft 365 互操作性的 EMS 产品/服务](ems-govt-service-description.md#ems-offers-for-us-government-and-microsoft-365-interoperability)的说明。

## <a name="azure-information-protection-premium-government-and-third-party-services"></a>Azure 信息保护高级政府版和第三方服务

某些 Azure 信息保护高级服务提供与第三方应用程序和服务无缝协作的功能。

这些第三方应用程序和服务可能涉及在 Azure 信息保护高级基础结构之外的第三方系统上存储、传输和处理组织的客户内容，因此不会在法规遵从性和数据保护承诺范围内进行处理。

请确保查看第三方在为组织的适当使用这些服务时提供的隐私和符合性声明。

## <a name="parity-with-azure-information-protection-premium-commercial-offerings"></a>与 Azure 信息保护高级商业产品/服务的奇偶校验

我们的目标是向政府 Azure 信息保护高级版 GCC 和 DoD 客户提供所有商业特性和功能，请注意以下缺少的功能列表。

从2020年7月起，Azure 信息保护高级版 GCC 高/DoD 和商业产品/服务之间已知的现有差距如下：

* 文档跟踪和吊销当前不可用。

* 仅 (版本9126.1001 或更高版本) Microsoft 365 应用支持分类和标记外接程序。 不支持 Office 2010，Office 2013 和其他 Office 2016 版本。

* 仅 Rights Management 版本9126.1001 或更高版本 (的 Microsoft 365 应用支持 (IRM) 的信息。 不支持 Office 2010，Office 2013 和其他 Office 2016 版本。

* 目前无法将受保护的文档和电子邮件共享给商业云中的用户。 包括商业云中的 Microsoft 365 应用用户、商业云中的非 Microsoft 365 应用用户以及具有个人 RMS 许可证的用户。

* 当前不支持在 SharePoint Online（受 IRM 保护的站点和库）中使用 Information Rights Management。

* Rights Management 连接器当前不可用。

* AD RMS 的移动设备扩展当前不可用。


## <a name="configuring-azure-information-protection-for-gcc-high-and-dod-customers"></a>为 GCC High 和 DoD 客户配置 Azure 信息保护

以下配置详细信息适用于适用于 GCC 高级和 DoD 客户的所有 Azure 信息保护解决方案，其中包括统一标签解决方案。

- [为租户启用 Rights Management](#enable-rights-management-for-the-tenant)
- [用于加密的 DNS 配置 (Windows)](#dns-configuration-for-encryption-windows)
- [用于加密的 DNS 配置（Mac、iOS、Android）](#dns-configuration-for-encryption-mac-ios-android)
- [标签迁移](#label-migration)
- [AIP 应用配置](#aip-apps-configuration)

> [!IMPORTANT]
> 从2020年7月更新起，Azure 信息保护统一标签解决方案的所有 *新* 的 GCC 高客户都可以仅使用常规菜单和扫描仪菜单功能。

### <a name="enable-rights-management-for-the-tenant"></a>为租户启用 Rights Management

必须为租户启用 Rights Management Service，才能正常加密。

* 检查是否启用了 Rights Management Service
  * 以管理员身份启动 PowerShell
  * 运行 `Install-Module aadrm`（如果未安装 AADRM 模块的话）
  * 使用 `Connect-aadrmservice -environmentname azureusgovernment` 连接到服务
  * 运行 `(Get-AadrmConfiguration).FunctionalState` 并检查状态是否为 `Enabled`
* 如果功能状态为 `Disabled`，则运行 `Enable-Aadrm`

### <a name="dns-configuration-for-encryption-windows"></a>用于加密的 DNS 配置 (Windows)
为了使加密正常工作，Office 客户端应用程序必须连接到该服务的 GCC、GCC 高/DoD 实例，并从此处启动。 若要将客户端应用程序重定向到正确的服务实例，租户管理员必须使用有关 Azure RMS URL 的信息来配置 DNS SRV 记录。 如果没有 DNS SRV 记录，客户端应用程序将默认尝试连接到公有云实例，并失败。

而且，假设用户将基于租户所有者域 (登录用户名，例如： joe@contoso.us) ，而不是 onmicrosoft 用户名 (例如： joe@contoso.onmicrosoft.us) 。 用户名中的域名用于将 DNS 重定向到正确的服务实例。

* 获取 Rights Management 服务 ID
  * 以管理员身份启动 PowerShell
  * 如果未安装 AADRM 模块，请运行 `Install-Module aadrm`
  * 使用 `Connect-aadrmservice -environmentname azureusgovernment` 连接到服务
  * 运行 `(Get-aadrmconfiguration).RightsManagementServiceId`，以获取 Rights Management 服务 ID
* 登录到 DNS 提供程序，然后导航到域的 DNS 设置以添加新的 SRV 记录
  * 服务 = `_rmsredir`
  * 协议 = `_http`
  * 名称 = `_tcp`
  * 目标 = `[GUID].rms.aadrm.us`（其中，GUID 是 Rights Management 服务 ID）
  * 端口 = `80`
  * 优先级、权重、秒、TTL = 默认值
* 在 [Azure 门户](https://portal.azure.us/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中，将自定义域与租户相关联。 关联自定义域将在 DNS 中添加一个条目，这可能需要几分钟的时间来验证添加值。
* 用相应的全局管理员凭据登录到 Office 管理中心并添加域 (例如： contoso.us) 用于用户创建。 在验证过程中，可能需要执行其他一些 DNS 更改。 验证完成后，即可创建用户。

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>用于加密的 DNS 配置（Mac、iOS、Android）
* 登录到 DNS 提供程序，然后导航到域的 DNS 设置以添加新的 SRV 记录
  * 服务 = `_rmsdisco`
  * 协议 = `_http`
  * 名称 = `_tcp`
  * 目标 = `api.aadrm.us`
  * 端口 = `80`
  * 优先级、权重、秒、TTL = 默认值

### <a name="label-migration"></a>标签迁移

GCC 高和 DoD 客户需要使用 PowerShell 迁移所有现有标签。 传统的 AIP 迁移方法 **不适用于** GCC 高客户和 DoD 客户。

使用 [New-Label](/powershell/module/exchange/new-label) cmdlet 迁移现有敏感度标签。 在开始迁移之前，请确保按照 [使用安全 & 符合性中心连接和运行 cmdlet 的说明](/powershell/exchange/connect-to-scc-powershell#connect-to-the-security--compliance-center) 进行操作。

现有敏感度标签具有加密时的迁移示例：

```powershell
New-Label -Name 'aipscopetest' -Tooltip 'aipscopetest' -Comment 'admin notes' -DisplayName 'aipscopetest' -Identity 'b342447b-eab9-ea11-8360-001a7dda7113' -EncryptionEnabled $true -EncryptionProtectionType 'template' -EncryptionTemplateId 'a32027d7-ea77-4ba8-b2a9-7101a4e44d89' -EncryptionAipTemplateScopes "['allcompany@labelaction.onmicrosoft.com','admin@labelaction.onmicrosoft.com']"
```

### <a name="aip-apps-configuration"></a>AIP 应用配置

使用 Azure 信息保护客户端时，必须配置以下注册表项之一，将 Windows 上的 AIP 应用指向正确的主权云。 请确保为您的设置使用正确的值。

- [统一标签客户端的 AIP apps 配置](#aip-apps-configuration-for-the-unified-labeling-client)
- [经典客户端的 AIP apps 配置](#aip-apps-configuration-for-the-classic-client)
#### <a name="aip-apps-configuration-for-the-unified-labeling-client"></a>统一标签客户端的 AIP apps 配置

**相关** 内容：仅限 AIP 统一标签客户端

| 注册表节点 | HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP |
| --- | --- |
| 名称 - ** | CloudEnvType |
| **值** | **0** = 商业 (默认值)  <br>**1** = GCC <br>**2** = GCC 高 <br>**3** = DoD|
| 类型 | REG_DWORD |
| | |

> [!NOTE]
>
> - 如果此注册表项为空、不正确或丢失，则该行为将恢复为默认 (**0** = 商用) 。
> - 如果键为空或不正确，则还会将打印错误添加到日志中。
> - 请确保在卸载后不删除注册表项。

#### <a name="aip-apps-configuration-for-the-classic-client"></a>经典客户端的 AIP apps 配置

**相关** 内容：仅限 AIP 经典客户端


| 注册表节点 | HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP |
| --- | --- |
| 名称 - ** | WebServiceUrl |
| **“值”** | https://api.informationprotection.azure.us |
| **Type** | REG_SZ (String) |
| | |

## <a name="firewalls-and-network-infrastructure"></a>防火墙和网络基础结构

如果你具有配置为允许特定连接的防火墙或类似的干预网络设备，请使用以下设置来确保 Azure 信息保护的流畅通信。

- **Tls 客户端到服务连接**：请勿终止到 **RMS.AADRM.US** URL 的 tls 客户端到服务连接 (例如，要执行数据包级别检查) 。

    您可以使用以下 PowerShell 命令来帮助您确定客户端连接在到达 Azure Rights Management 服务之前是否终止：

    ```powershell
    $request = [System.Net.HttpWebRequest]::Create("https://admin.aadrm.us/admin/admin.svc")
    $request.GetResponse()
    $request.ServicePoint.Certificate.Issuer
    ```

    结果应显示发证 CA 来自 Microsoft CA（例如：`CN=Microsoft Secure Server CA 2011, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`）。 如果你看到的颁发 CA 名称不是 Microsoft，则可能是安全客户端到服务的连接被终止，需要在防火墙上重新配置。

- **下载标签和标签策略 (仅限 AIP 经典客户端)**：若要启用 Azure 信息保护经典客户端以下载标签和标签策略，请允许通过 HTTPS **api.informationprotection.azure.us** URL。

有关详细信息，请参阅：

- [Office 365 美国政府 DoD 终结点](/microsoft-365/enterprise/microsoft-365-u-s-government-dod-endpoints)
- [Office 365 美国政府版](/microsoft-365/enterprise/microsoft-365-u-s-government-gcc-high-endpoints)

## <a name="service-tags"></a>服务标记

请确保允许访问以下 **服务标记** 的所有端口：
*    **AzureInformationProtection**
*    **AzureActiveDirectory**
*    **AzureFrontDoor.Frontend**
