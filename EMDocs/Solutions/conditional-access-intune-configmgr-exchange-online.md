---
title: "条件访问 - Exchange Online、Intune、Configuration Manager"
description: "使用 Configuration Manager、Exchange Online 和 Intune 来管理电子邮件访问和保护移动设备上的电子邮件数据。"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 06921361-9475-46e6-9368-3cc44c84b22f
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: 47f4298d833bcc910f769046ec018f270e75d246
ms.contentlocale: zh-cn
ms.lasthandoff: 07/07/2017


---

# <a name="deploy-exchange-online-with-microsoft-intune-and-configuration-manager"></a>将 Microsoft Intune 和 Configuration Manager 与 Exchange Online 结合部署
你已通读了[有关保护公司电子邮件和文档的体系结构指南](architecture-guidance-for-protecting-company-email-and-documents.md)，现在可以继续部署解决方案。

如果你已使用 System Center Configuration Manager 和 Exchange Online，则你可以集成 Intune 来管理移动设备上的电子邮件访问和保护电子邮件数据。 用于实施此解决方案的高级别过程如下所示：

-   创建合规性策略，这些策略用于定义设备必须遵从的规则和设置，以便将设备视为符合条件访问策略。

-   开始实施条件访问。

-   或者，为 Exchange Online 配置 Exchange Server 连接器。此连接器仅供报表使用。 启用条件访问不需要此连接器。

## <a name="conditional-access-control-flow-for-exchange-online"></a>Exchange Online 的条件访问控制流
下图显示客户端试图在 Exchange Online 中访问电子邮件的控制流。 实施条件访问之前可能先执行 A 和 B。

![与 Intune 和 Exchange Online 结合使用的 Configuration Manager 中的条件访问流程图](./media/ProtectEmail/Hybrid-Exchange-Online-CA-architecture.png)

-   Microsoft Intune：管理设备的合规性和条件访问策略

-   Microsoft Azure Active Directory：对用户进行身份验证，并提供设备的合规性状态

-   Configuration Manager：管理设备注册和提供报表（如果已启用）

-   Exchange Online：根据设备状态执行对电子邮件的访问

## <a name="before-you-begin"></a>在开始之前
确保你的环境满足实施此解决方案的要求。

-   安装 Exchange 服务并分配到从受信任的公用证书颁发机构购买的[有效数字证书](https://technet.microsoft.com/library/dd351044.aspx)。

-   确认你运行的是具有累积更新包 1 或更高版本的 System Center 2012 R2 Configuration Manager SP1。

-   配置具有运行以下 Exchange Server cmdlet 的权限的帐户（本地或域管理员）：

    Clear-ActiveSyncDevice

    Get-ActiveSyncDevice

    Get-ActiveSyncDeviceAccessRule

    Get-ActiveSyncDeviceStatistics

    Get-ActiveSyncMailboxPolicy

    Get-ActiveSyncOrganizationSettings

    Get-ExchangeServer

    Get-Recipient

    Set-ADServerSettings

    Set-ActiveSyncDeviceAccessRule

    Set-ActiveSyncMailboxPolicy

    Set-CASMailbox

    New-ActiveSyncDeviceAccessRule

    New-ActiveSyncMailboxPolicy

    Remove-ActiveSyncDevice

## <a name="deployment-steps"></a>部署步骤
请按照以下步骤来部署 Exchange Online 解决方案：

### <a name="step-1-create-compliance-policies-and-deploy-to-users"></a>步骤 1：创建合规性策略，并部署到用户。
合规性策略定义设备必须遵从的规则和设置，以便将设备视为符合条件访问策略。 请按照 [Configuration Manager 中的合规性策略](https://technet.microsoft.com/library/mt131417.aspx)中的步骤创建合规性策略。

如果你希望在 iOS 设备不再属于公司之后，你能够从该设备中删除所有公司的电子邮件，那么你必须创建并部署电子邮件配置文件，然后设置合规性策略，该策略指定由 Intune 管理电子邮件配置文件。 你必须将电子邮件配置文件部署到此合规性策略针对的同一用户集。

![显示“创建符合性策略向导”的“规则”页面的屏幕截图，你可以在该页面指定电子邮件配置文件必须由 Intune 管理](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

如果你指定此合规性策略，则已设置电子邮件帐户的用户必须手动删除它，之后 Intune 会通过[条件访问的最终用户体验](end-user-experience-conditional-access.md)中描述的注册过程将其重新添加。

创建合规性策略后，在列表中选择合规性策略的名称，然后单击“部署” 。

### <a name="step-2-configure-conditional-access-policy"></a>步骤 2：配置条件访问策略。
首先，确定以何种方式、何时实施条件访问，以及将影响哪些员工。 然后，按照 [Configuration Manager 中的针对 Exchange 电子邮件的条件访问](https://technet.microsoft.com/library/mt131421.aspx)中的步骤为 Exchange Online 启用条件访问策略。

> [!NOTE]
> 必须在 Intune 控制台中配置条件访问策略。 以下步骤从通过 Configuration Manager 访问 Intune 控制台开始。 如果出现提示，请使用在 Configuration Manager 与 Intune 之间设置连接器时的相同凭据登录。

### <a name="step-3-optional-install-and-configure-an-exchange-server-connector"></a>步骤 3：（*可选*）安装和配置 Exchange Server 连接器。
Configuration Manager 仅支持一个 Exchange 组织包含一个连接器。

> [!IMPORTANT]
> 在安装 Exchange Server 连接器之前，请确认 Configuration Manager 支持你所使用的 Microsoft Exchange 的版本。 有关详细信息，请参阅 [Configuration Manager 支持的配置](https://technet.microsoft.com/library/gg682077.aspx)。

按照[如何使用 Configuration Manager 和 Exchange 管理移动设备](https://technet.microsoft.com/library/gg682001.aspx)中的步骤安装并配置 Exchange Server 连接器。

## <a name="verification-steps"></a>验证步骤
如果为此解决方案配置了可选的 Exchange Server 连接器，则可以使用 Configuration Manager 跟踪日志工具打开 EasDisc.log 文件（位于安装 Configuration Manager 的 Microsoft Configuration Manager/Logs 文件夹）。 在日志文件中搜索 "Exchange Connector" 以查找有关 Exchange Connector 是否正在运行以及连接的设备数量的信息。

![显示 EasDisc 日志文件在 Configuration Manager 跟踪日志工具中打开的屏幕截图](./media/ProtectEmail/Hybrid-Onprem-Eas-DiscLog-Sample.PNG)

Configuration Manager 跟踪日志工具包含在 [System Center 2012 R2 Configuration Manager 工具包](https://www.microsoft.com/download/details.aspx?id=50012)中。

## <a name="reporting"></a>报表
如果配置了可选的 Exchange Server 连接器，则可以使用 Configuration Manager 控制台查看有关 Exchange Connector 已发现的设备的特定信息。 对于已实施条件访问的设备，你可以查看每个设备的当前状态、最后一次使用 Exchange Server 连接设备的时间等等。

在 Configuration Manager 控制台中，单击“资产和合规性”  ，然后单击“设备” 。 在“Exchange 访问状态”列中可以查看每个设备的当前状态（隔离或允许）  。 如果该列尚未显示，可以右键单击列标题栏区域来添加该列。 通过添加“上次成功同步到 Exchange Server 的时间”  列，还可以查看如 Exchange 报告的每个设备的上次成功同步时间。

![显示 Configuration Manager 控制台中的设备列表的屏幕截图](./media/ProtectEmail/Hybrid-Onprem-Verify-Devices-State.png)

如果你正在运行 SQL Server Reporting Service (SSRS)，则可以查看条件访问报表，其中显示了设备的合规性状态、是否已安装并运行 Exchange Connector，以及 EAS 访问状态。 该报表还将提供有关 Active Directory 注册、EAS 激活，以及设备所有者的信息。

![显示 SQL Server Reporting Services 报表的一个示例的屏幕截图](./media/ProtectEmail/Hybrid-Reports-CA.png)

要查看 SSRS 报表，必须在主服务器上安装报表角色：

1.  在配置管理器中，单击“管理”&gt;“层次结构配置”&gt;“站点配置”&gt;“服务器和站点系统角色”。

2.  选择一个服务器，然后单击“添加站点系统角色”  以打开“添加站点系统角色”向导。

3.  在“系统角色选择”页面上，选择“报表服务点”  复选框。 报表服务点将显示与客户端管理相关的报表。

4.  单击“下一步” 。

下面显示了配置策略的部署状态：

![显示配置策略的部署状态的屏幕截图](./media/ProtectEmail/Hybrid-Reports-Deployment-Status.png)

### <a name="latency"></a>延迟
使用新式的身份验证方法的设备将立即应用条件访问。 对于通过 EAS 协议进行连接的设备，根据默认设置，在实施条件访问之前会有高达 6 小时的延迟时间。 设备在此期间可视为合规。

## <a name="where-to-go-from-here"></a>后续步骤
当你在移动设备上部署保护企业电子邮件和电子邮件数据的解决方案后，你可以了解有关[条件访问的最终用户体验](end-user-experience-conditional-access.md)的详细信息。 这将帮助你为最终用户注册其特定设备时可能出现的问题做好准备。

