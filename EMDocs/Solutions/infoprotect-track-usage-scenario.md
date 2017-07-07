---
title: "跟踪共享数据的使用情况并对数据滥用做出响应 | Microsoft Docs"
description: "介绍如何利用 Azure 权限管理功能通过企业移动性 + 安全性来跟踪共享数据的使用情况以及响应数据滥用。"
author: yuridio
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c7e6e01a-5796-4bd7-a0c5-847ecfc08a1e
ms.reviewer: v-craic
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: bc112d81a2b0e59f9ae67efe2a914b0c64ac76ba
ms.openlocfilehash: 81e6b6479dcca1a82b37cfc4c832f36e33ac1b7b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/07/2017



---

# <a name="track-usage-of-shared-data-and-respond-to-data-abuse"></a>跟踪共享数据使用情况并对数据滥用做出响应

对共享数据的可见性和控制对于跟踪数据使用情况或滥用至关重要。 当前，数据共享范围很广，组织需要在其域外共享数据以满足业务需求。

在这种背景下，用户不仅需要共享文档，而且还要监视谁正在访问文档并在必要时能够撤销访问，这将成为一项常规操作。 IT 管理员希望在与一组授权用户共享数据时拥有与当前类似的体验 - 他们希望控制数据并对数据使用或滥用采取适当的措施。 继续阅读以了解有关企业移动性 + 安全性如何帮助处理这种情况的详细信息。

## <a name="how-can-enterprise-mobility--security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？
企业移动性 + 安全性 (EMS) 是唯一一个不仅保护设备自身上的公司数据，另外还通过标识、设备、应用和数据四重保护措施来提供保护的综合性云解决方案。 EMS 帮助用户解决移动优先、云优先世界中的一个关键挑战 - 如何在保持控制和能够对问题快速响应采取行动的同时共享数据。 使用 EMS，可以让员工在组织内外安全地进行协作。 EMS 允许文档所有者和管理员跟踪对共享的敏感文件进行的操作活动。 他们可以查看操作活动，例如收件人打开文件或未授权的用户被拒绝访问文件。 用户还可以查看访问文件的地理位置。 只需单击一下，用户便可以撤销对共享文件的访问。

### <a name="recommended-solution"></a>建议的解决方案
通过集成 Azure 权限管理，你可以跟踪用户使用受保护文档的方式。 如有必要（即需要停止对这些文件的共享），你还可以撤消对这些文件的访问权限。 此功能使用 RMS 组、共享受保护选项和跟踪使用情况，适用于 Office 应用程序（Word、Excel、Outlook 和 PowerPoint）。 在 Windows 系统中，还可以使用文件资源管理器，对所有其他受支持的设备，可以使用 web 浏览器跟踪使用情况。 跟踪和撤销是文档生命周期监视和响应阶段的一部分，如下图所示：

![图形显示了 Azure 权限管理中的文档生命周期。](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig1.png)

观看此短视频，快速了解 Azure 信息保护如何简化对文档使用情况的跟踪。

<iframe width="675" height="480" src="https://sec.ch9.ms/ch9/76ac/35499c0a-859c-4a3e-9a5c-fa4e5d0e76ac/AzureRMSDocumentTrackingandRevocation_high.mp4 " frameborder="0" allowfullscreen></iframe>

#### <a name="how-to-implement-this-solution"></a>实现本解决方案的方式
如果已经使用[在内部和外部共享敏感数据](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data)这种方案来配置 Azure 权限管理和客户端应用程序，那么并不需要配置跟踪共享数据的使用情况这项功能。 现在只需选择跟踪文档的方式。 可用选项有：

1. 使用 Office 跟踪使用情况
- 使用浏览器跟踪使用情况
- 撤消对共享文档的访问权限

### <a name="how-to-track-usage-of-shared-data-and-respond-to-data-abuse"></a>如何跟踪共享数据使用情况并对数据滥用做出响应
在下面的部分中，可以根据特定方案选择如何跟踪共享数据的使用情况。

#### <a name="scenario-1-track-usage-using-microsoft-office"></a>方案 1：使用 Microsoft Office 跟踪使用情况
如果用户希望获取有关使用 Office 应用程序（Word、Excel 和 PowerPoint）保护的文档使用情况的详细信息，可以通过 RMS 组，选择“共享受保护”选项，然后单击“跟踪使用”，如下图所示：

![图形显示了用户在 Office 应用程序中设置 “跟踪使用” 选项的方式。](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig2.png)

有关此功能的详细信息，请参阅[使用 RMS 共享应用程序跟踪和撤销文档](https://docs.microsoft.com/information-protection/rms-client/sharing-app-track-revoke)。

#### <a name="scenario-2-track-usage-using-browser"></a>方案 2：使用浏览器跟踪使用情况
在某些情况下，你的设备上可能没有安装 Office 应用程序，但仍需要监控文档使用情况。 请通过[支持的浏览器](https://docs.microsoft.com/rights-management/rms-client/sharing-app-track-revoke)转到[文档跟踪站点](http://go.microsoft.com/fwlink/?LinkId=529562)使用凭据登录，选择想要跟踪的文档后，你将看到使用情况统计信息，如下面屏幕中所示：

![图形显示了通过 Web 浏览器得到文档使用统计信息。](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig3.png)

在此屏幕中，可以看到文件共享的某段月份里的浏览数和被拒绝访问数。 尽管每个磁贴都有一个显示访问该文件的用户的摘要信息，你还可以在单击磁贴获取更多信息。 对于上一屏幕中的示例，选择拒绝访问时将显示以下结果：

![图形显示了来自 web 浏览器的文档拒绝访问统计信息。](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig4.png)

#### <a name="scenario-3-revoke-access-to-shared-document"></a>方案 3：撤销对共享文档的访问权限

监视文档时，掌握使用情况是了解用户行为的重要步骤，它的重要价值表现在可根据监视文档时发现的情况采取相应的行动。 例如，阅读使用情况报告后发现有效用户在尝试访问此文档时被拒绝访问。 此时，你应该采取纠正措施来解决此问题。

还有一些响应安全事件的场景。 例如，发现广泛共享的某个文档包含有公司机密信息，并且人力资源部要求 IT 撤销对此文档的访问。 [撤消某个文档时](https://docs.microsoft.com/rights-management/rms-client/sharing-app-track-revoke)，它并不会删除你共享的文档，但获得授权的用户将不再能够打开该文档。 若要撤销访问权限，只需单击位于跟踪使用情况页面上“撤销访问权限”就会看到类似于下面屏幕的窗体：

![图形显示了“撤销访问”窗体，它可以撤销对文档的访问权限。](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig5.png)

你可以启用此选项以通知收件人已撤销对此文档的访问权限，还可以包含一条消息解释撤销的原因。

