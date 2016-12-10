---
title: "在内部和外部共享敏感数据 | Azure 信息保护"
description: "此方案介绍如何使用企业移动性 + 安全性，通过利用 Microsoft Azure 信息保护功能在内部和外部共享敏感数据。"
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a996fbf8-ece4-40bc-b866-d4606c230027
ms.reviewer: v-craic
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 02b0e611805ad2214b1b108b8c466590aad7999a
ms.openlocfilehash: d76fa5c4857b12e2eb91de9fb3217ba78ea6a11f


---

# <a name="share-sensitive-data-internally-and-externally"></a>在内部和外部共享敏感数据

虽然许多数据泄露是由网络攻击造成的，但专家认为更多的原因在于人为错误，或者说是因为员工无意间或不慎泄漏敏感商业数据所致。 通过设置适当的安全信息和数据丢失防护协议，几乎能够避免所有这类泄露。

对于企业和用户而言，共享数据不可避免，尽管这很有必要，但同时也带来行业中的最大挑战之一，即：在跨设备共享数据的同时如何减少与他人共享数据时的数据泄露情况？ 在需要与外部源（如合作伙伴、客户和其他方）共享敏感数据时，这种威胁波及的范围甚至更广。 

![图示](./media/share-sensitive-data/share-sensitive-data-fig1.png)

在这种情况下，通常企业会进行这类项目：员工需能够跨数据接收器进行内部协作并与第三方供应商进行外部协作，在业务中采用一致的安全协议的同时，在数据分类和保护过程中影响最终用户行为。 

## <a name="how-can-enterprise-mobility-security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？

企业移动性 + 安全性 (EMS) 是一个不仅从设备自身本机保护公司数据，还采用身份、设备、应用和数据这四个保护层提供更多保护的综合云解决方案。 EMS 可帮助解决移动优先、云优先世界中的一个重大难题，即如何向出行在外的员工传送安全的电子邮件。 使用 EMS，可以让员工在组织内外安全地进行协作。 EMS 允许 IT 管理员对电子邮件使用应用 [Azure 权限管理](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)策略模板。 使用权限附加在邮件上，以便在联机和脱机、组织防火墙内部和外部提供保护。

## <a name="recommended-solution"></a>建议的解决方案

通过集成 Azure 权限管理和 Exchange Online 权限管理，EMS 使组织能够保护经由电子邮件离开组织的数据。 可以对位于本地的 Exchange Server 和 Exchange online (Office 365) 实施这一解决方案。 信息权限管理和 [Office 365 邮件加密](https://technet.microsoft.com/library/dn569285.aspx)均基于策略，旨在与 Exchange 传输规则引擎配合使用。 这意味着 Microsoft Azure 权限管理支持通过单步操作轻松设置复杂的策略限制。

下面介绍一些通过此解决方案可实现的功能：

- 通过向电子邮件应用不同的 IRM 选项帮助防止电子邮件受到未经授权的访问。
- 在联机和脱机的情况下保证信息安全，因为无论使用 Office Online 查看文件或将文件下载到本地计算机，文件都受到保护。
- 与所有 Office 文档无缝集成，可帮助保护组织的知识产权。
- 除使用默认权限管理服务模板外，还可根据业务需要应用自定义模板。


## <a name="how-to-implement-this-solution"></a>实现本解决方案的方式

若要配置 Exchange Online 以支持 Azure RMS，你必须为 Exchange Online 配置信息权限管理 (IRM) 服务。 执行以下步骤以实施本解决方案：

1. 与 Exchange 集成： 
    - Exchange Online：使 Exchange Online 能够使用 Azure RMS
    - Exchange 内部部署：部署 Azure 权限管理连接器
2. 使用 Exchange 发送受保护的 Office 文档

## <a name="how-to-share-sensitive-data-internally-and-externally"></a>如何在内部和外部共享敏感数据

企业需要让员工能够跨数据接收器进行内部协作并与第三方供应商进行外部协作，在业务中采用一致的安全协议的同时，在数据分类和保护过程中影响最终用户行为。 数据共享成为整个过程中关键的一环，企业在实现数据共享的同时也要减少数据隐私性和完整性受损的情况。

### <a name="step-1-integration-with-exchange"></a>步骤 1：与 Exchange 集成

通过将 Azure 权限管理策略模板应用于电子邮件，向电子邮件应用权限管理保护。 启用集成的第一步将因 Exchange 的位置而异，取决于其是在云中 (Exchange online) 还是在本地。 

#### <a name="enable-rights-management-integration-with-exchange-online"></a>实现权限管理与 Exchange Online 的集成

若要配置 Exchange Online 以支持 Azure RMS，你必须为 Exchange Online 配置信息权限管理 (IRM) 服务。 按照 [Office 365：客户端和联机服务的配置](https://docs.microsoft.com/rights-management/deploy-use/configure-office365)一文中 [Exchange Online：IRM 配置](https://docs.microsoft.com/rights-management/deploy-use/configure-office365#exchange-online-irm-configuration)部分中的步骤配置 Exchange Online 以实现 IRM。

最后一步应是用于检验配置的最后测试，所得结果应类似于以下屏幕中的某一结果：

![PowerShell](./media/share-sensitive-data/share-sensitive-data-fig2.png)

#### <a name="enable-rights-management-integration-with-exchange-on-premises"></a>实现权限管理与 Exchange本地部署的集成

若要配置权限管理与 Exchange 本地部署的集成，需要配置 Microsoft 权限管理 (RMS) 连接器。 该连接器将启用现有本地 Exchange 服务器以将其信息权限管理 (IRM) 功能与基于云的 Microsoft 权限管理服务 (Azure RMS) 配合使用。 你可以在混合方案中使用此连接器，即使你的一些用户连接到了在线服务。

查看[安装 RMS 连接器的先决条件](https://docs.microsoft.com/rights-management/deploy-use/deploy-rms-connector#prerequisites-for-the-rms-connector)，并按照[安装和配置 Azure 权限管理连接器](https://docs.microsoft.com/rights-management/deploy-use/install-configure-rms-connector)一文中提供的五个步骤进行操作。

### <a name="step-2-send-a-protected-document-using-exchange"></a>步骤 2：使用 Exchange 发送受保护的文档

请按照[使用分类和标记保护数据](infoprotect-secure-classify-scenario.md)方案中的步骤 3 来安装 RMS 共享应用程序。 如需支持不同类型的客户端，请查看[权限管理共享应用程序：安装和配置客户端](https://docs.microsoft.com/rights-management/deploy-use/configure-sharing-app)一文，了解如何安装 RMS 共享应用程序的更多详细信息。

如果希望共享 Office 文档，例如直接从 Word 共享，只需使用功能区中的“共享保护项”图标即可，如下图所示：

![ShareProtect](./media/share-sensitive-data/share-sensitive-data-fig3.png)

单击此选项后，应会显示“共享保护项”对话框，其中包括希望如何共享此文档的更多详细信息，如下图所示：

![共享](./media/share-sensitive-data/share-sensitive-data-fig4.png)

必须在此窗口的顶端键入目标用户的电子邮件，并选择想要为此用户提供的访问类型。 在此窗口的底部，可以控制文档的过期日期，还可以启用选项：每次有人尝试打开此文档时你都将收到一封电子邮件。 正确进行选择后，单击“发送”，Outlook 将会打开一封新邮件，如以下屏幕所示：

![电子邮件](./media/share-sensitive-data/share-sensitive-data-fig5.png)

> [!IMPORTANT] 
> 从 Microsoft Ignite 观看演示文稿[使用 Azure 信息保护安全地进行协作](https://myignite.microsoft.com/videos/49947)，了解有关此方案的详细信息。



<!--HONumber=Dec16_HO2-->


