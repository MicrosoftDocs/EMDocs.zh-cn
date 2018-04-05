---
title: 保护企业文档运行 Microsoft Office 加载-Microsoft 365 企业 |Microsoft 文档
description: 描述如何使用 WIP 和 Intune 来保护企业数据在运行 Office 加载项的文档中。
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/14/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 5f43eba8b95b0eefaaef6e95bce6fd5d8c1f6695
ms.sourcegitcommit: a322bdd365c7d648c5241cf959dcd04b3815672d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2018
---
# <a name="use-wip-and-intune-to-protect-enterprise-data-in-documents-running-office-add-ins"></a>使用 WIP 和 Intune 保护运行 Office 加载项的文档中的企业数据。
组织中的用户使用 Office 加载项与组织数据进行交互时可能产生潜在风险，泄露某些数据。 用户正在运行 Office 加载项时，可使用 Windows 信息保护 (WIP) 和 Microsoft Intune 保护企业数据。

企业可使用 [WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)以前称为企业数据保护 (EDP)）保护知识产权和公司数据。 WIP 有助于防范企业应用和数据在企业自有设备和员工带到工作中的个人设备上的意外数据泄露，而无需对环境或其他应用进行更改。

[Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) 提供一组不同的工具，用于管理复杂的移动环境。 Intune 结合使用移动应用管理和设备管理选项，使 IT 管理员和最终用户能够灵活管理和提高移动生产力。

可以使用 Intune [创建和部署 WIP 策略](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/overview-create-wip-policy)。 使用 Intune 可以选择受保护的应用和 WIP 的保护级别，并在网络上查找企业数据。

使用 WIP 和 Intune：

-   即使数据下载到个人设备上，企业也能提供合理的企业数据实施策略。

-   企业可以运用上下文策略知识，告知用户如何防范数据意外泄露给非托管的应用和服务。

-   最终用户可以遵守公司数据策略，无需中断其典型工作流。

-   还可以在工作和个人工作效率之间无缝转换。

如果用户没有将个人和企业内容混合，WIP 和 Intune 会在后台自动运行并且实际上不可见。

[Office 加载项](https://dev.office.com/docs/add-ins/overview/office-add-ins) 是基于 Web 技术生成的。 它们将 Web 上的功能和信息带到 Office 应用程序中。 通过 Office.js 中可用的 API 与 Office 应用程序中的内容进行交互。 Office 加载项的核心原则包括：

-   安全性：Office JavaScript 平台体系结构确保加载项代码是沙盒化的，并在与主机 Office 应用程序相关的单独进程中运行。 当加载项不满足性能标准或存在潜在恶意行为时，这可使平台采取纠正措施，例如通知用户，或在某些情况下，禁用加载项。 此体系结构适用于支持 Office 加载项的所有平台。

-   复原性：加载项平台的“进程外”性质可确保加载项本身不影响主机 Office 应用程序的性能或用户体验。 这对保持 Office 快速响应用户操作至关重要。

-   跨平台：一次编写，到处运行 Office 运行项。 目前 Windows、Office Online、Mac 和 iPad 均支持加载项。 Android 和通用平台也即将支持加载项。

Office 加载项可与文档中的企业内容和潜在敏感内容集成。 作为应用程序扩展性的一部分，加载项继承了其来自主机应用程序策略的访问。 例如，如果 WIP 设置阻止 Word 访问企业内容，则加载项无法访问 Word 文档中的企业内容。

加载项的目标之一是为最终用户消除任何阻止的问题，同时还确保企业管理员可以阻止加载项（如需要）。 有关 Office 加载项启用数据保护的主要原则包括：

-   为 IT 管理员提供阻止加载项加载的方法。

-   尽量减少或消除管理员要求的工作，使加载项企业准备就绪。

-   在加载项使用期间，尽量减少为最终用户提供的提示和消息。

-   如果文档和加载项具有相同的上下文，消除对最终用户的提示。

## <a name="add-ins-and-wip"></a>加载项和 WIP

在环境中启用 WIP 时，可以为 Office 加载项启用以下方案：

-   Office 加载项使用文档上下文激活。 对于 Outlook，加载项的上下文基于当前的活动邮箱。 激活加载项之前，在信任提示中明确定义加载项权限。 用户决定特定文档中的加载项是否适用，以及是否允许加载项运行。

-   管理员可以使用组策略来阻止所有 Office 应用商店加载项或所有 Office 加载项。这意味着用户可以激活来自 [SharePoint 或 Office 365 企业目录](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)的仅受信任的加载项。

-   管理员可以使用移动设备管理 (MDM) 阻止防火墙级别的加载项。 请注意，这不适用于移动或自带设备办公 (BYOD) 方案。

-   加载项应用企业和个人上下文之间的复制粘贴操作。 例如，用户复制企业上下文加载项并粘贴到个人文档时，会显示默认跨上下文复制粘贴的提示。

下表列出了启用 WIP 时企业和个人上下文以及文档中需要的加载项行为。

> [!NOTE]
> - 主机应用程序内部和外部的剪切、复制和粘贴操作在所有方案中均按预期工作。
> - 数据传输到加载项服务未在所有方案中受到保护。

|**文档或邮箱类型**|**个人上下文中的加载项**|**企业上下文中的加载项**|
|:----------------|:-------------------------------------------------|:---------------------------------------------------|
|个人     |加载项在个人上下文中加载。<br><br>不允许导航到企业 URL（即使是在自己的应用域中）。<br><br>允许导航到个人 URL|加载项无法加载或激活。<br><br>如果升级了文档的上下文（例如：通过将其保存到企业位置）：<br><br>- 允许导航到企业 URL。<br><br>- 允许导航到个人 URL。|
|企业   |加载项在企业上下文中加载。<br><br>允许导航到企业 URL。<br><br>允许导航到个人 URL。|加载项在企业上下文中加载。<br><br>允许导航到企业 URL。<br><br>允许导航到个人 URL。|
|未保存      |加载项在个人上下文中加载。<br><br>不允许导航到企业 URL（即使是在自己的应用域中）。<br><br>允许导航到个人 URL。|加载项在企业上下文中加载，文档默认转换到企业上下文。 这意味着文档必须保存到企业位置。<br><br>允许导航到企业 URL。允许导航到个人 URL。            |


## <a name="add-ins-and-intune"></a>加载项和 Intune

在 Office for iPad 上，Office 加载项当前支持 Word、Excel 和 PowerPoint。 Outlook 当前支持 iOS（iPad 和 iPhone）上的加载项。 Outlook 管理员可以在默认情况下关闭加载项，包括开发者安装的加载项，并仅启用其组织认可的特定加载项。 下表概述了在 Office for iOS 设备上运行的加载项的数据保护方案支持，这些设备使用 Intune 应用保护工具。

> [!NOTE]
> 有关在 Android 和 iOS 设备上运行的 Outlook 加载项的信息，请参阅[管理用户对 Outlook 加载项的访问](https://technet.microsoft.com/library/jj943757(v=exchg.150).aspx)和 [Outlook 加载项](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx)。

|**文档或邮箱类型**|**具有 Intune 应用保护的适用于 iOS 的个人上下文中的加载项<sup>*</sup>**|**具有 Intune 应用保护的适用于 iOS 的企业上下文的加载项<sup>*</sup>**|
|:-----|:-----|:-----|
|个人|加载项的使用情况不受个人文档中的 Intune 应用保护的影响。|加载项的使用情况不受个人文档中的 Intune 应用保护的影响。|
|企业|允许激活个人加载项。<br><br>Intune 应用保护策略可以保护加载项和设备上的其他应用程序之间的剪切、复制、粘贴和数据传输方案。<br><br>数据传输到加载项服务不受保护。|允许激活企业加载项。 管理员可以通过 Office 管理工具控制加载项的发布类型[（Office 365 集中部署）](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f)。<br><br>Intune 应用保护策略可以保护加载项和设备上的其他应用程序之间的剪切、复制、粘贴和数据传输方案。<br><br>数据传输到加载项服务不受保护。|

>**<sup>*</sup>** 管理员可以使用 [Office 365 集中部署](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f)将 Word、Excel 和 PowerPoint 加载项直接从 Office 365 管理中心或使用 PowerShell 脚本部署到个人用户、组或组织。 用户在 Windows、Mac 或 Office Online 上打开 Office 应用程序时，加载项自动安装到其功能区。

## <a name="summary"></a>“摘要”

考虑到关于 Office 加载项的原则，管理员可以通过 WIP 和 Intune 管理企业数据，并提供最终用户完成其工作所需的工具。 这就有可能导致企业数据在组织边界外部泄露。 Office JavaScript API 当前并未提供相关方法，因此开发人员无法识别在 Office 文档和加载项之间传输的数据类型。 他们需要向用户提供多个提示，在某些情况下，有可能将个人文件错误地标记为企业文件，这可能对用户体验造成负面影响，并且与数据保护原则不一致。

Microsoft 致力于保护客户数据并继续投资于 Intune 和 WIP 技术创新，增强客户体验。

## <a name="learn-more"></a>了解详细信息

-   [Windows 信息保护 (WIP) 的一般指南和最佳做法](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/guidance-and-best-practices-wip)

-   [什么是 Intune？](https://docs.microsoft.com/intune/introduction-intune)

-   [设备注册方法概述](https://docs.microsoft.com/sccm/mdm/plan-design/device-enrollment-methods)

-   [更改 MDM 机构](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority)

-   [准备好配置面向 Windows 10 的应用保护策略](https://docs.microsoft.com/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)
