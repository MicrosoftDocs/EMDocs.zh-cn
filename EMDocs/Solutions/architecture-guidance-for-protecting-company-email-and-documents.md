---
title: "有关保护公司电子邮件和文档的体系结构指南"
description: "在确保最终用户体验简单且不影响工作效率的同时，为公司提供数据保护。"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc9c7d79-d2ca-4cb2-8456-c7a88cbbf6fd
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0eacdea52150bc8282df618ae73c96724cec26c5
ms.openlocfilehash: 66732b444e6a449256a7929324d7b26e3e814f15


---

# 有关保护公司电子邮件和文档的体系结构指南
本主题首先概述了如何在确保最终用户体验简单且不影响工作效率的同时，为公司提供数据保护。 然后，我们将专门重点介绍如何使用 Microsoft 企业移动性 + 安全性解决方案，帮助提供对公司电子邮件的安全访问，以及帮助保护电子邮件和附件中的公司数据。

本节讨论用于保护公司电子邮件和文档的体系结构。 有关部署解决方案的指南，请参阅[详细了解如何部署用于保护公司电子邮件和文档的解决方案](learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents.md)。

> [!TIP]
> 请从 [TechNet 库](https://gallery.technet.microsoft.com/Managing-Access-and-Help-b7a05d0d/file/140056/1/Managing%20Access%20and%20Help%20Protect%20Corporate%20Email%20Data%20on%20Mobile%20Devices.pdf)中获取此完整主题的可下载副本。

员工希望使用自己的设备访问公司资源和实用工具。 IT 部门需要确保员工能够这样做，但同时保护好公司的敏感数据。 [自带设备办公](byod-design-considerations-guide.md) (BYOD) 带来了一项特殊挑战，即需要在个人设备上区分个人数据和工作数据，并防止有意或无意中共享公司数据。

**研究表明：**

-   全球 37% 的劳动力都采用移动办公方式

-   2014 年第 3 季度 53% 的电子邮件是在手机或平板电脑上打开的

-   61% 的员工在个人设备上处理个人事务和工作任务

考虑这一点：

-   电子邮件是所有设备上最常用的应用程序。

-   电子邮件中的内容和邮件附件可复制、共享或移动到 IT 部门监控范围之外的地方，进而危及公司安全。

由于最终用户想要使用自己的个人设备处理公司事务，且电子邮件是最常访问的应用程序，IT 部门的第一步是确保最终用户可以在其自己的设备上访问公司电子邮件，同时确保邮件中的敏感数据不会被泄露。

## 概述
Microsoft 推出了企业移动性 + 安全性 (EMS)，这是用于识别身份、管理移动设备、管理应用和保护数据的全面解决方案。 EMS 提供分层的安全模型，可让你的 IT 部门管理几乎任何设备对电子邮件、数据和企业应用程序的访问。

EMS 由以下云服务组成：

![显示 EMS 所含云服务的图形：Microsoft Azure AD Premium、Microsoft Intune 和 Microsoft Azure 信息保护](./media/ProtectEmail/Enterprise-Mobility-Suite.png)

使用 EMS 可从企业网络内外保护数据：

-   员工可使用自选的设备访问公司的电子邮件、工作相关的应用程序和公司数据，无需担心泄露公司的敏感信息。

-   公司数据在每个层级得到保护：用户、设备、应用程序以及数据本身。

-   IT 管理员可以确保只有受信任的用户通过托管的合规设备在托管的应用程序环境下才可以访问公司数据。

Intune 托管的应用包括 Office 移动应用，这正是此解决方案的核心。 利用 Office 移动应用，你可以在防止数据泄露的同时，帮助最大限度提高员工的工作效率。 例如，IT 管理员可以设置阻止策略，阻止将公司数据复制到 Dropbox 等个人云存储器。

当员工移动或更改作业或者丢失设备时，EMS 可帮助远程并选择性地擦除设备中的公司数据。 最终用户或 IT 管理员都可执行此操作。

## EMS 如何帮助保护你的数据
4 层的身份识别、设备、应用和数据安全模型旨在确保只有目标用户，通过满足你所配置的一组合规性策略的设备，在托管应用内才能访问公司资源。

![显示标识、设备、应用和数据的四层安全模型的图形](./media/ProtectEmail/Protecting_your_data.png)

保护数据始于建立和验证用户身份。 *Azure AD/* 是一款企业级身份验证和访问管理工具，可提供单一登录、多重身份验证、自助服务密码等功能。 它为安全模型的 **身份识别层** 提供功能。

构建于身份识别基线，IT 管理员可以使用 *Microsoft Intune* 确保移动设备已注册、托管并符合你的公司策略。 这是**设备层**。

第三层是采用由 Intune 托管的应用生态系统的**应用管理层**。 利用这个生态系统，用户可以提高工作效率并使用他们所需和所知的工具（如 Office），同时你的 IT 部门可以确保托管应用生态系统中的敏感数据不会泄露。

*Azure 信息保护（原 Azure RMS）*在安全模型的文件级别对数据进行保护。 应用于数据的安全策略与数据一起传送、帮助保护传输中和未使用数据的安全，不受访问数据的设备影响。 这是安全模型的**数据层**。

## 后续步骤
- [观看](https://www.youtube.com/watch?v=ltcZvm4VOFU) 这段视频，了解如何注册试用帐户并开始使用。

- 请阅读[移动设备管理设计注意事项指南](mdm-design-considerations-guide.md)，更好地了解移动设备管理设计要求。

- [详细了解如何部署用于保护公司电子邮件和文档的解决方案](learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents.md)。

此外，如果你希望了解有关 EMS 和 Azure Active Directory 的详细信息，你可以从以下这些文章中获取更多相关信息：
- [EMS 体系结构](https://azure.microsoft.com/documentation/infographics/enterprise-mobility/)

- [Azure Active Directory 是什么](/active-directory/active-directory-whatis)

- [Azure Active Directory 如何支持 Office 365、Microsoft Intune 和其他 Microsoft 服务？](/active-directory/active-directory-administer#what-is-an-azure-ad-tenant)

- [Azure Active Directory 如何帮你管理标识](/active-directory/active-directory-administer)

- [什么是 Azure 信息保护？](/information-protection/understand-explore/what-is-azure-rms)

- [应用程序如何支持 Azure 信息保护](/information-protection/understand-explore/applications-support)



<!--HONumber=Nov16_HO2-->


