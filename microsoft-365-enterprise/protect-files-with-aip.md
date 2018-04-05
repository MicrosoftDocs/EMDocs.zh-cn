---
title: 保护 SharePoint Online Azure 的信息保护文件 |Microsoft 文档
description: 应用 Azure 的信息保护，以保护高度机密的在线 SharePoint 工作组网站中的文件。
services: active-directory
keywords: Office 365, Windows 10, 企业移动性和安全性, Microsoft 365 企业版
documentationcenter: ''
author: JoeDavies-MSFT
manager: laurawi
ms.assetid: ''
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.workload: ''
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 11/15/2017
ms.author: josephd
ms.openlocfilehash: ec88a40392e8bc530a40c35a1d8dadd1be8eb4f3
ms.sourcegitcommit: a322bdd365c7d648c5241cf959dcd04b3815672d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2018
---
# <a name="protect-files-with--azure-information-protection"></a>使用 Azure 信息保护来保护文件

## <a name="introduction"></a>简介

使用本文中的步骤配置 Azure 信息保护 (AIP)，为高度机密的 SharePoint Online 团队网站中的文件提供加密和权限。 

即使从网站下载文件，加密和权限保护也会遍历该文件。 有关高度机密的 SharePoint Online 团队网站的详细信息，请参阅[保护 SharePoint Online 网站和文件](secure-sharepoint-online-sites-and-files.md)。

> [!NOTE]
> 将 Azure 信息保护加密应用于 Office 365 中存储的文件时，该服务无法处理这些文件的内容。 共同创作、电子数据展示、搜索、Delve 和其他协作功能将无法正常使用。 数据丢失防护 (DLP) 策略只适用于元数据（包括 Office 365 标签），但并不适用于这些文件的内容（如文件内的信用卡号）。

## <a name="configure-azure-information-protection"></a>配置 Azure 信息保护

首先，请按照[使用 Office 365 订阅的 Office 365 管理中心激活 Azure RMS](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) 中的说明操作。

接下来，通过执行以下步骤，使用新作用域内策略以及高度机密的 SharePoint Online 团队网站的保护和权限子标签来配置 Azure 信息保护：

1. **Office 365 门户**拥有安全管理员或公司管理员角色的帐户登录。有关帮助信息，请参阅[登录到 Office 365 的位置](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
2. 在浏览器的单独选项卡中，转到 Azure 门户 ([https://portal.azure.com](https://portal.azure.com/))。
3. 如果是首次配置 Azure 信息保护，请参阅[这些说明](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time)。
4. 在列表窗格中，单击“更多服务”，键入“信息”，然后单击“Azure 信息保护”。
5. 在“Azure 信息保护”边栏选项卡上，选择“作用域内策略”>“+ 添加新策略”。
6. 在“策略名称”中键入新策略的名称，并在“描述”中键入新策略的描述。
7. 单击“选择获取此策略的用户或组”>“用户/组”，然后选择高度敏感的 SharePoint Online 团队网站的网站成员访问组。
8. 单击“选择”>“确定”。
9. 对于“高度机密”标签，请单击省略号 (…)，然后单击“添加子标签”。
10. 在“名称”中键入子标签的名称，并在“描述”中键入标签的描述。
11. 在“为包含此标签的文档和电子邮件设置权限”中，单击“保护”。
12. 在“保护”部分中，单击“Azure (云密钥)”。
13. 在“保护”边栏选项卡中，在“保护设置”下，单击“+ 添加权限”。
14. 在“添加权限”边栏选项卡的“指定用户和组”下，单击“+ 浏览目录”。
15. 在“AAD 用户和组”窗格中，选择高度敏感的 SharePoint Online 团队网站的网站成员访问组，然后单击“选择”。
16. 在“从预设中选择权限”下，清除“打印、复制和提取内容”和“转接”复选框。
17. 单击 **“确定”** 两次。
18. 在“子标签”边栏选项卡上，根据需要配置视觉标记，然后单击“保存”。
19. 关闭“新作用域内策略”边栏选项卡。
20. 在“Azure 信息保护 - 作用域内策略”边栏选项卡上，单击“发布”，然后单击“是”。

下面是高度机密的 SharePoint Online 团队网站的配置结果。

 ![高度机密](./media/protect-files-with-aip/hc_w_aip.png)

现在可以开始创建文档并使用 Azure 信息保护和新的标签来保护它们。

必须在设备或基于 Windows 的计算机上[安装 Azure 信息保护客户端](https://docs.microsoft.com/information-protection/rms-client/install-client-app)。 可以编辑脚本，使安装自动化，也可手动安装客户端。 

有关详细信息，请参阅下列资源：

* [Azure 信息保护的客户端](https://docs.microsoft.com/information-protection/rms-client/use-client)
* [安装 Azure 信息保护客户端](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
* [手动安装的下载页](https://www.microsoft.com/download/details.aspx?id=53018)

安装完成后用户即可运行，然后使用其 Office 365 帐户从 Office 应用程序（如 Microsoft Word）登录。 新的“信息保护”栏可用于选择标签。 

请确保用户知道 SharePoint Online 团队网站以及用于保护其高度机密文件的标签。

>[!Note]
>如果有多个高度敏感的 SharePoint Online 团队网站，应创建多个 Azure 信息保护作用域内策略以及多个包含上述设置的子标签，另外每个子标签的权限设置为特定 SharePoint Online 团队网站的网站成员访问组。
>

## <a name="next-steps"></a>后续步骤

[云应用和混合解决方案](https://technet.microsoft.com/library/dn262744.aspx)
