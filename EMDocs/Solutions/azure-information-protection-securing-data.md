---
title: Azure 信息保护在保护数据方面的角色 | Microsoft Docs
description: 本文介绍 Azure 信息保护在保持组织数据安全中的角色。
author: yuridio
ms.author: mbaldwin
manager: barbkess
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: rights-management
ms.reviewer: v-craic
ms.suite: ems
ms.openlocfilehash: 7fd4ab09de4cf050b9300a9dd340b33338a4d8d2
ms.sourcegitcommit: c63d47c411504fb84651c43bb6851d9692450067
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "68937381"
---
# <a name="the-role-of-azure-information-protection-in-securing-data"></a>Azure 信息保护在保护数据方面的角色

[Azure 信息保护 (AIP)](/azure/information-protection/what-is-information-protection) 让客户能够对数据进行分类和标记，并能使用加密来保护数据。 Azure 信息保护使 IT 管理员能够：

- 基于预设规则对电子邮件和文档进行自动分类
- 向文档添加标记，如自定义标头、页脚和水印
- 使用权限管理保护公司的机密文件，这使得他们能够：
    - 将 RSA 2048 位密钥用于公钥加密，将 SHA 256 用于签名操作。
    - 针对组织内外某些特定接受者来加密文件
    - 应用一组特定的权限来限制文件的可用性    
    - 基于权限策略中用户的标识和授权来解密内容

这些功能使企业能够对其数据进行更好的端到端控制。 就此而论，Azure 信息保护在保护公司数据中扮演很重要的角色。

> [!IMPORTANT]
> 有关 Azure 信息保护工作方式的详细信息，请阅读[Azure RMS 如何工作？。](/azure/information-protection/how-does-it-work)

## <a name="the-state-of-enterprise-protection-today"></a>当今企业保护的状态

许多企业目前没有任何保护技术，其文档和电子邮件以明文形式共享，而数据管理员不明确哪些用户能够访问特别保密的内容。 SMIME 等保护技术非常复杂，而 ACL 不一定处理电子邮件和文档。

![无文档保护](./media/azure-information-protection-securing-data/aip-securing-data-fig1.png)

在很大程度上未受保护的环境中，Azure 信息保护提供以前没有的安全措施。 安全性是一个不断发展的主题，没有组织可声称任何时候都有 100% 保护，而 Azure 信息保护如果部署适当会增加组织的安全性。

## <a name="security-principles-for-sharing-content"></a>有关共享内容的安全原则

IT 管理员在组织内使用 Azure 信息保护时，对客户端设备和用户身份管理具有完全的控制，这为组织内部共享搭建适当平台。 组织外部发送信息本来可信度就较低。 考虑保护信息的方法时有一些原则 - 你必须执行风险评估。 执行此风险评估时请考虑以下几点：

- 接受者可以实际接触到非托管设备，因此可以控制该设备上发生的任何情况。
- 接受者通过身份验证，可能获得一定程度的与非模拟相关的信任。

如果 IT 管理员不控制设备或标识，IT 就不能控制受保护信息会发生什么情况。 一旦用户通过身份验证，并打开受保护的信息，你就不能再控制你的信息。 在这种情况下，将信任不执行内容策略的接受者。

如果恶意的外部接受者对受保护内容有权进行访问，则不可能完全停止他们。 Azure 信息保护帮助建立道德界限，并借助智慧的应用程序让人们在访问文档的方式上保持真诚。 当基于标识提供的访问权限的已定义边界内存在绝对信任时，Azure 信息保护可提供帮助。

但检测并缓解未来的访问更简单。 Azure 信息保护服务的文档跟踪功能可以跟踪访问，组织可撤消对特定文档的访问或撤消用户的访问权限。

如果内容非常敏感，组织无法信任接受者，额外的内容安全性变得极为重要。 建议打开有利于安全性的拨号，使文档具有访问控制。

## <a name="identity-based-security"></a>基于标识的安全性

接下来的部分将探讨攻击受保护内容的三种主要情况，以及可以如何使用环境控制和 Azure 信息保护的组合来缓解对内容的恶意访问。

### <a name="attacks-by-unauthorized-users"></a>未经授权用户的攻击

Azure 信息保护中保护的基础是 - 对受保护内容的访问基于已通过身份验证的标识和授权。 这意味着使用 Azure 信息保护，无身份验证或授权表示不能访问。 这是部署 Azure 信息保护的主要原因，它使企业能够从无限制访问状态转到根据用户身份验证和授权访问信息的状态。

通过使用此 Azure 信息保护功能，企业能够分隔信息。 例如，将人力资源 (HR) 部门的敏感信息分隔在部门内部；使财务部门的数据仅供财务部门访问。 Azure 信息保护提供了基于标识的访问，杜绝没有限制的随意访问。

下图提供向 Tom 发送文档的用户 (Bob) 的示例。 这里，Bob 来自财务部门，Tom 来自销售部门。 如果不授予任何权限，Tom 无法访问该文档。

![不能访问](./media/azure-information-protection-securing-data/aip-securing-data-fig2.png)

这种情况中的关键点是，Azure 信息保护可停止来自未经授权的用户的攻击。 有关 Azure 信息保护中加密控制的详细信息，请参阅 [Azure RMS 使用的加密控制：算法和密钥长度](/azure/information-protection/how-does-it-work)。

### <a name="access-by-malicious-programs-on-behalf-of-users"></a>通过恶意程序代表用户进行访问

代表用户的恶意程序访问通常在用户不知情的情况下发生。 特洛伊木马程序、病毒和其他恶意软件是可代表用户执行操作的典型恶意程序示例。 如果此类程序可模拟用户的标识或利用用户的权限来执行操作，那么它可使用 [Azure 信息保护 SDK](/azure/information-protection/develop/developers-guide) 代表不知情的用户来解密内容。 因为此操作发生在用户的上下文中，没有简单的方法来防止这种攻击。

![恶意程序](./media/azure-information-protection-securing-data/aip-securing-data-fig3.png)

此处我们的目的是提高用户标识的安全性，这将帮助降低恶意应用程序操纵用户标识的能力。 Azure Active Directory 提供几种解决方案，可帮助保护用户标识，例如使用双因素身份验证。 此外，Azure Activity Directory 标识保护还提供其他功能，应了解这些功能来保护用户标识的安全。

保护标识超出 Azure 信息保护的范围，属于管理员的职责。

> [!IMPORTANT]
> 还有很重要的一点是，关注“托管”环境以消除恶意程序的存在。 这将在下个情形中讨论。

### <a name="malicious-users-with-authorization"></a>具有授权的恶意用户

恶意用户的访问实质上是对信任的危害。 这种情况中需精心制作启用程序以提升用户的权限，因为与之前的情形不同，此用户自愿提供凭据来破坏信任。

![恶意用户](./media/azure-information-protection-securing-data/aip-securing-data-fig4.png)

Azure 信息保护旨在使应用程序位于负责强制执行与文档关联的权限的客户端设备上。 不论以哪种标准来衡量，当今受保护内容安全性的最薄弱环节是在客户端设备上，其内容对最终用户以纯文本形式可见。 Microsoft Office 等客户端应用程序正确地执行权限，因此恶意用户无法使用这些应用程序来提升权限。 但借助 Azure 的信息保护 SDK，有动机的攻击者可以创建不执行权限的应用程序，这就是恶意程序的本质。

这种情况的重点是保护客户端设备和应用程序，以便恶意应用程序不能被使用。 下面列出了 IT 管理员可以执行一些步骤：

- 使用 [Windows AppLocker](https://technet.microsoft.com/library/dd759117(v=ws.11).aspx) 帮助确保有害程序不能被执行
- 使用 [Intune](https://docs.microsoft.com/intune/) 和 [System Center Configuration Manager](https://docs.microsoft.com/sccm/) 帮助确保设备运行正常
- 确保设备上的防病毒软件处于最新状态
- 使用支持 [Microsoft 标识中转站](https://technet.microsoft.com/library/ms166045(v=sql.105).aspx)的应用程序进行身份验证和 [SSO](https://azure.microsoft.com/resources/videos/overview-of-single-sign-on/)

这种情况中的关键点是，保护客户端计算机和应用程序构成信任的重要部分，而信任对于 Azure 信息保护起巩固作用。

由于 Azure 信息保护的设计目的不包括防御已获得内容访问权限的用户的恶意滥用，因此不能将其用于保护内容免受上述用户的恶意修改。 虽然事实上对内容的任何类型修改需要用户首先已获得对受保护数据的访问权限，且与文档相关的政策和权限本身已恰当签名并防篡改，但是一旦用户被授予对所需加密/解密密钥的访问权限，则应将用户视为在技术上可以对数据进行解密、修改和重新加密。 有许多解决方案可以向 Office 文档提供文档签名、作者身份证明、防篡改和不可否认性，无论是在 Microsoft 产品（如 Office 文档签名支持、Outlook 中的 s/MIME 支持），还是通过第三方。 不应仅依赖 AIP 的保护功能来防御授权用户的恶意修改。 

## <a name="summary"></a>“摘要”

实现完全的安全性远不止采用一种技术。 通过各种各样的相互依赖的手段，IT 管理员可以减少现实世界中受保护内容的攻击面。

- **Azure 信息保护**：防止对内容进行未经授权的访问
- **Microsoft Intune、System Center Configuration Manager 和其他设备管理产品**：使托管的和受控的环境中不存在恶意应用
- **Windows AppLocker**：使托管的和受控的环境中不存在恶意应用
- **Azure AD 标识保护**：增强用户标识中的信任度
- **EMS 条件性访问**：增强设备和标识中的信任度
