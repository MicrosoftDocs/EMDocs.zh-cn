---
title: "通过 Intune 和 Configuration Manager 使用 Exchange 中的条件访问"
description: "将本地 Exchange 和 Exchange Online 并存的部署与 Configuration Manager 和 Intune 配合使用，来管理移动设备上的电子邮件访问和保护电子邮件数据。"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5ccd033f-bc31-4fae-b6bf-9e1c2722627f
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: c69cf9eebb89a734991d4e218e1bb9475246dc6f


---

# <a name="deploy-exchange-online-and-on-premises-with-microsoft-intune-and-configuration-manager"></a>将 Microsoft Intune 和 Configuration Manager 与 Exchange Online 和本地 Exchange Server 结合部署
你已通读了[有关保护公司电子邮件和文档的体系结构指南](architecture-guidance-for-protecting-company-email-and-documents.md)，现在可以继续部署解决方案。

在同时使用本地 Exchange 和 Exchange Online 来管理电子邮件配置文件的环境中，公司能够将他们现有的本地 Microsoft Exchange 组织的功能丰富的体验和管理控制扩展到云中。 这种“混合”类型部署为 Microsoft Office 365 中本地 Exchange Server 2013 组织和 Exchange Online 之间的单个 Exchange 组织提供了流畅的外观和感觉。 此外，此类型的部署可以充当完全转移到 Exchange Online 组织的中间步骤。

如果你已使用 Configuration Manager 以及本地 Exchange 和 Exchange Online 并存的部署，则你可以集成 Intune 来管理移动设备上的电子邮件访问和保护电子邮件数据。 你可以按照上述说明实施该解决方案，以便分别实施每个解决方案。

## <a name="prerequisites"></a>先决条件
要配置实现本地 Exchange 和 Exchange Online 的混合类型的环境，你的现有 Exchange 组织必须满足特定要求。 如果不能满足这些要求，则你无法完成在 Microsoft Office 365 的本地 Exchange 组织和 Exchange Online 组织之间配置混合部署所需的步骤。

请参阅[混合部署先决条件](https://technet.microsoft.com/library/hh534377.aspx)以查看创建和配置此类环境的要求。

## <a name="deployment-steps"></a>部署步骤
若要部署共存解决方案，请按照上述步骤部署[本地 Exchange Server](conditional-access-intune-configmgr-exchange.md) 和 [Exchange Online](conditional-access-intune-configmgr-exchange-online.md) 解决方案。

## <a name="where-to-go-from-here"></a>后续步骤
当你在移动设备上部署保护企业电子邮件和电子邮件数据的解决方案后，你可以了解有关[条件访问的最终用户体验](end-user-experience-conditional-access.md)的详细信息。 这将帮助你为最终用户注册其特定设备时可能出现的问题做好准备。



<!--HONumber=Jan17_HO2-->


