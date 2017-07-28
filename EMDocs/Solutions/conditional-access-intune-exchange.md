---
title: "通过 Intune 和本地 Exchange Server 使用条件访问"
description: "使用 Intune 解决方案进行 Exchange 内部部署。"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2a64e898-4c60-48bf-ae14-b05e091e0533
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 042bc3afbb5e0ce919b3a07dcbdba6ae27cacaa7
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2017
---
# <a name="deploy-exchange-on-premises-with-intune"></a>使用 Intune 部署 Exchange 内部部署

你已通读了[有关保护公司电子邮件和文档的体系结构指南](architecture-guidance-for-protecting-company-email-and-documents.md)，现在可以继续部署解决方案。

为了使 Intune 能够直接管理移动设备，用户需要将设备注册到 Intune 中。

## <a name="deployment-steps"></a>部署步骤
请按照以下步骤使用 Intune 解决方案部署 Exchange 内部部署：

### <a name="step-1-install-and-configure-the-microsoft-intune-on-premises-exchange-server-connector"></a>步骤 1：安装和配置 Microsoft Intune 本地 Exchange Server 连接器。

对于用户未注册的移动设备，你可以使用 Exchange Connector 启用 Exchange ActiveSync 管理。 Exchange Connector 将你与 Exchange 部署连接，使你能通过 Intune 控制台管理移动设备。

请按照[为本地或托管 Exchange 配置 Microsoft Intune 本地连接器](/intune/deploy-use/intune-on-premises-exchange-connector)中的步骤下载、安装和配置 Microsoft Intune Exchange Connector。

> [!IMPORTANT]
> 对于每个 Intune 帐户，你只能建立一个 Exchange 连接。 如果尝试配置其他连接，则它会将原始连接替换为新连接。

### <a name="step-2-create-compliance-policies-and-deploy-to-users"></a>步骤 2：创建合规性策略，并部署到用户。
合规性策略定义设备必须遵从的规则和设置，以便将设备视为符合条件访问策略。 请按照[在 Microsoft Intune 中创建合规性策略](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)中的步骤创建和部署合规性策略。

如果你希望在 iOS 设备不再属于公司之后，你能够从该设备中删除所有公司的电子邮件，那么你必须创建并部署电子邮件配置文件，然后设置合规性策略，该策略指定由 Intune 管理电子邮件配置文件。 你必须将电子邮件配置文件部署到此合规性策略针对的同一用户集。
![“Intune 创建策略”向导中“常规”选项卡上的“电子邮件配置文件”部分的屏幕截图，可以在该部分指定必须通过 Intune 管理电子邮件配置文件。](./media/ProtectEmail/intune-create-policy-email-profile.PNG)

如果你指定此合规性策略，则已设置电子邮件帐户的用户必须手动删除它，之后 Intune 会通过[条件访问的最终用户体验](end-user-experience-conditional-access.md)中描述的注册过程将其重新添加。

> [!IMPORTANT]
> 如果你尚未部署合规性策略，但是启用了 Exchange 条件访问策略，则将允许设定为目标的所有设备进行访问。

### <a name="step-3-identify-users-who-will-be-impacted-by-conditional-access-policy"></a>步骤 3：确定将会受到条件访问策略影响的用户。
成功配置 Exchange Server 连接器后，它将开始列出尚未注册到 Intune、但使用 Exchange Active Sync 连接到你的组织的 Exchange 资源的设备清单。  

请按照[评估条件访问策略的效果](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)中的说明确定会受到条件访问策略影响的用户。


### <a name="step-4-configure-user-groups-for-the-conditional-access-policy"></a>步骤 4：为条件访问策略配置用户组。
将条件访问策略的目标设定为不同的用户组，具体取决于策略类型。 这些组包含将作为目标的用户，或从策略中免除的用户。 如果将某个用户设定为策略的目标，则其使用的每个设备必须合规才能访问电子邮件。

有关详细信息，请参阅[为条件访问策略配置用户组](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)。

### <a name="step-5-configure-conditional-access-policy"></a>步骤 5：配置条件访问策略。
Exchange 内部部署的条件访问策略使用下面的流程来评估是允许还是阻止设备。

![显示本地 Exchange Server 的条件访问策略如何评估是允许还是阻止设备的流程图](./media/ProtectEmail/conditional-access-8-2.png)

请按照[配置条件访问策略](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)中提供的信息设置你的条件访问策略。

## <a name="reporting"></a>报表

### <a name="monitor-the-compliance-and-conditional-access-policies"></a>监视遵从性和条件性访问策略
查看被 Exchange 阻止的设备：

在 Intune 仪表板上，单击“被 Exchange 阻止的设备”磁贴，以显示被阻止的设备的数目以及指向相关详细信息的链接。
![在 Intune 仪表板上显示“被 Exchange 阻止的设备”磁贴的屏幕截图](./media/ProtectEmail/intune-sa-6blocked-devices.PNG)

## <a name="where-to-go-from-here"></a>后续步骤
当你在移动设备上部署保护企业电子邮件和电子邮件数据的解决方案后，你可以了解有关[条件访问的最终用户体验](end-user-experience-conditional-access.md)的详细信息。 这将帮助你为最终用户注册其特定设备时可能出现的问题做好准备。
