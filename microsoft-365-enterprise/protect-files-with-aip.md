---
title: "使用 Azure 信息保护保护文件 | Microsoft Docs"
description: "应用 Azure 信息保护来保护高度机密的 SharePoint Online 团队网站中的文件。"
services: active-directory
keywords: "Office 365, Windows 10, 企业移动性和安全性, Microsoft 365 企业版"
documentationcenter: 
author: JoeDavies-MSFT
manager: laurawi
ms.assetid: 
ms.prod: microsoft-365-enterprise
ms.service: 
ms.workload: 
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/28/2017
ms.author: josephd
ms.openlocfilehash: 34758e152a483a2bada03aeb4c4b5ee3327fb469
ms.sourcegitcommit: 5b34af60e3aac19d618f1c6297da91e2c050a374
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2017
---
# <a name="protect-files-with--azure-information-protection"></a>使用 Azure 信息保护来保护文件

## <a name="introduction"></a>简介

使用本文中的步骤配置 Azure 信息保护 (AIP)，为高度机密的 SharePoint Online 团队网站中的文件提供加密和权限。 

即使从网站下载文件，加密和权限保护也会遍历该文件。 有关高度机密的 SharePoint Online 团队网站的详细信息，请参阅[保护 SharePoint Online 网站和文件](secure-sharepoint-online-sites-and-files.md)。

## <a name="configure-azure-information-protection"></a>配置 Azure 信息保护

首先，请按照[使用 Office 365 订阅的 Office 365 管理中心激活 Azure RMS](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) 中的说明操作。

接下来，通过执行以下步骤使用高度机密的 SharePoint Online 团队网站的保护和权限来配置“AIP 高度机密”标签：

1. 使用具有安全管理员或公司管理员角色的帐户登录到 Office 365 门户。 如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
2. 在浏览器的单独选项卡中，转到 Azure 门户 ([https://portal.azure.com](https://portal.azure.com/))。
3. 在列表窗格中，单击“更多服务”，键入“信息”，然后单击“Azure 信息保护”。
4. 在“Azure 信息保护 - 全局策略”边栏选项卡，在标签列表下，单击“高度机密”。
5. 在“标签: 机密”边栏选项卡，在“为包含此标签的文档和电子邮件设置权限”中，单击“保护”。
6. 在“保护”部分中，单击“Azure RMS”。
7. 在“保护”边栏选项卡中，在“保护设置”下，单击“+ 添加权限”。
8. 在“添加权限”边栏选项卡的“指定用户和组”下，单击“+ 浏览目录”。
9. 在“AAD 用户和组”窗格中，选择高度敏感的 SharePoint Online 团队网站的网站成员访问组，然后单击“选择”。
10. 在“从预设中选择权限”下，清除“打印、复制和提取内容”和“转接”复选框。
11. 单击 **“确定”** 两次。
12. 在“标签: 高度机密”边栏选项卡中，单击“保存”。
13. 在“Azure 信息保护 - 全局策略”边栏选项卡中，单击“发布”。

下面是高度机密的 SharePoint Online 团队网站生成的配置。

 ![高度机密](./media/protect-files-with-aip/hc_w_aip.png)

现在可以开始创建文档并使用 Azure 信息保护和“高度机密”标签来保护它们。

必须在设备或基于 Windows 的计算机上[安装 Azure 信息保护客户端](https://docs.microsoft.com/information-protection/rms-client/install-client-app)。 可以编辑脚本，使安装自动化，也可手动安装客户端。 

有关详细信息，请参阅下列资源：

* [Azure 信息保护的客户端](https://docs.microsoft.com/information-protection/rms-client/use-client)
* [安装 Azure 信息保护客户端](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
* [手动安装的下载页](https://www.microsoft.com/download/details.aspx?id=53018)

安装完成后用户即可运行，然后使用其 Office 365 帐户从 Office 应用程序（如 Microsoft Word）登录。 可以从新的“敏感”工具栏选择“高度机密”标签。 

请确保用户知道用于存储高度机密文件的 SharePoint Online 团队网站。

>[!Note]
>如果有多个高度敏感的 SharePoint Online 团队网站，必须创建多个 Azure 信息保护标签，并包括上述设置，另外每个标签的权限设置为特定 SharePoint Online 团队网站的网站成员访问组。
>

## <a name="next-steps"></a>后续步骤
[Microsoft 针对政治宣传活动、非营利组织和其他敏捷型组织的安全指南](https://technet.microsoft.com/library/mt493213.aspx)

[保护 SharePoint Online 网站和文件](secure-sharepoint-online-sites-and-files.md)

[在政治宣传活动开发/测试环境中创建团队网站](secure-sharepoint-online-sites-dev-test.md)

[云应用和混合解决方案](https://technet.microsoft.com/library/dn262744.aspx)






