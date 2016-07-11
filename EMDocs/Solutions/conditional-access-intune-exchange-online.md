---
title: "结合使用条件访问、Microsoft Intune 和 Exchange Online"
description: 
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8cfe421b-52c9-4d44-8df1-15c82375c335
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4e6a2c100c63ff21b7ccb89d59517dd63195b657
ms.openlocfilehash: 82b00a5ce54a25b50563c9e5ef3c33b3c648639d


---

# 使用 Intune 部署 Exchange Online

你已通读了[有关保护公司电子邮件和文档的体系结构指南](architecture-guidance-for-protecting-company-email-and-documents.md)，现在可以继续部署解决方案。

为了使 Intune 直接管理移动设备，用户需将设备注册到 Intune 中。

## 部署步骤
请按照以下步骤使用 Intune 解决方案部署 Exchange Online：

### 步骤 1：创建合规性策略，并部署到用户。
合规性策略定义设备必须遵从的规则和设置，以便将设备视为符合条件访问策略。 请按照[在 Microsoft Intune 中创建合规性策略](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)中的步骤创建和部署合规性策略。

如果你希望在 iOS 设备不再属于公司之后，你能够从该设备中删除所有公司的电子邮件，那么你必须创建并部署电子邮件配置文件，然后设置合规性策略，该策略指定由 Intune 管理电子邮件配置文件。 你必须将电子邮件配置文件部署到此合规性策略针对的同一用户集。

![显示“创建符合性策略向导”的“规则”页面的屏幕截图，你可以在该页面指定电子邮件配置文件必须由 Intune 管理。](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

如果你指定此合规性策略，则已设置电子邮件帐户的用户必须手动删除它，之后 Intune 会通过[条件访问的最终用户体验](end-user-experience-conditional-access.md)中描述的注册过程将其重新添加。

> [!IMPORTANT]
> 如果你尚未部署合规性策略，但是启用了 Exchange 条件访问策略，则将允许设定为目标的所有设备进行访问。

### 步骤 2：评估条件访问策略的影响。
如果已通过使用 [Microsoft Intune Service to Service Connector](/intune/deploy-use/intune-service-to-service-exchange-connector) 在 Intune 和 Exchange 之间配置了连接，则可以使用**移动设备清单报告**来标识将在配置条件访问策略之后被阻止访问 Exchange 的 EAS 邮件客户端。

请按照[评估条件访问策略的效果](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)中的说明确定会受到条件访问策略影响的用户。

### 步骤 3：为条件访问策略配置用户组。
将条件访问策略的目标设定为不同的用户组，具体取决于策略类型。 这些组包含将作为目标的用户，或从策略中免除的用户。 如果将某个用户设定为策略的目标，则其使用的每个设备必须合规才能访问电子邮件。

有关详细信息，请参阅[为条件访问策略配置用户组](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)。

### 步骤 4：配置条件访问策略。
Exchange Online 的条件访问策略使用下面的流来评估是允许还是阻止设备。

![显示 Exchange Online 的条件访问策略如何评估是允许还是阻止设备的流程图。](./media/ProtectEmail/conditional-access-8-1.png)

请按照[配置条件访问策略](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)下提供的信息设置你的条件访问策略。



## 报表

### 监视遵从性和条件性访问策略
查看被 Exchange 阻止的设备：

在 Intune 仪表板上，单击“被 Exchange 阻止的设备”磁贴，以显示被阻止的设备的数目以及指向相关详细信息的链接。
![在 Intune 仪表板上显示“被 Exchange 阻止的设备”磁贴的屏幕截图。](./media/ProtectEmail/intune-sa-6blocked-devices.PNG)



## 后续步骤
当你在移动设备上部署保护企业电子邮件和电子邮件数据的解决方案后，你可以了解有关[条件访问的最终用户体验](end-user-experience-conditional-access.md)的详细信息。 这将帮助你为最终用户注册其特定设备时可能出现的问题做好准备。



<!--HONumber=Jul16_HO1-->


