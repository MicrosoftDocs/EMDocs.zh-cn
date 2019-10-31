---
title: 实现商业无国界
description: 本文介绍如何使用企业移动性 + 安全性提供跨云和本地资产的单一标识，并利用 Azure Active Directory 中的工具让用户保持最高效率。
keywords: ''
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: conceptual
ms.prod: ''
ms.service: active-directory
ms.assetid: 38e9802b-d8c0-4f5c-b89d-8ce1e04f7387
ROBOTS: ''
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: b1d2689c366872b9f9c559ae12e7cd4de032bb6d
ms.sourcegitcommit: 393421ada426fc958125e310b92e9a84b31a9c2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2019
ms.locfileid: "68937433"
---
# <a name="enable-business-without-borders"></a>实现商业无国界
标识并非可有可无 - 它是员工实现高效工作的核心。 组织需使其员工能通过任何设备随时随地访问所有数据和应用程序。 用户需要相互合作，与合作伙伴合作，并与客户沟通。 他们使用的工具不再驻留于受保护和受控制的环境中，而是可在任何公共云中找到。

这个新领域带来了传统工具无法应对的挑战和高级威胁。 由于新边界是用户，因此仅保护自己的网络是没有意义的。 在这种环境中提高工作效率和获得保护的关键是强大的标识解决方案。

## <a name="how-can-enterprise-mobility--security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？
企业移动性 + 安全性 (EMS) 是一个不仅从设备自身本机保护公司数据，还采用身份、设备、应用和数据这四个保护层提供更多保护的综合云解决方案。 EMS 可帮助解决移动优先、云优先世界中的一个重大难题 - 如何提供一个适用于跨云和本地资产的单一标识，并尽可能让用户保持高效。

### <a name="access-to-single-sign-on-applications"></a>访问单一登录应用程序
通过联合身份验证和单一登录，用户将拥有一组登录凭据和密码，并且 IT 能够更高效地管理用户标识。
### <a name="multi-factor-authentication"></a>多重身份验证
用户还能够将新设备引入企业，但 IT 部门可以验证这些连接到网络的设备由具有适当凭据的个人所有和控制。 多重身份验证 (MFA) 可帮助提供一层保护。
### <a name="self-service-group-management"></a>自助服务组管理
当用户确实忘记密码时，能够重置自己的密码，这减少了 IT 的负担并使用户通过快速解决问题提高效率。
### <a name="cross-organization-collaboration"></a>跨组织协作
企业到企业协作对于 97%的 Microsoft 客户是非常重要的，他们认为与合作伙伴合作是一个需实现的关键要求。 Azure Active Directory B2B（企业到企业）协作支持跨公司关系，途径是使合作伙伴能够使用自我管理的标识有选择地访问企业应用程序和数据。

## <a name="recommended-solution"></a>建议的解决方案
建议使用 [Azure Active Directory B2B（企业到企业）协作](https://azure.microsoft.com/documentation/articles/active-directory-b2b-what-is-azure-ad-b2b/) 解决方案，它可与传统工具上的现有投资协作，使组织能够以安全高效的方式随处访问所需的任何内容。
- IT 专业人员，向合作伙伴组织和协作方提供其组织数据和应用程序的访问权限。
- 合作伙伴用户，作为自己组织的代表或员工进行操作。
- 访问审查、电子邮件验证、允许列表、拒绝列表等，以及控制对主机应用程序和资源的访问。
- 合作伙伴用户是可发现的，并且可从其自己的组织看到其他用户（取决于策略）。

### <a name="how-azure-ad-b2b-collaboration-works"></a>Azure AD B2B 协作工作原理

Azure AD B2B 协作基于邀请和兑换模型，该模型使用你想与其合作的合作伙伴的电子邮件地址和你想使用的相应应用程序。

1. 管理员登陆 Azure 门户，并通过导入包含合作伙伴用户信息的 CSV 文件来邀请合作伙伴用户。
2. Azure 门户向合作伙伴发送电子邮件。
3. 合作伙伴单击从 Azure 门户收到的电子邮件中的链接。 如果合作伙伴用户已经存在于 Azure AD 中，系统将提示他们输入其工作凭据；如果没有，合作伙伴用户将需要以 Azure AD B2B 协作用户身份注册。
4. 合作伙伴用户将自动重定向到他们受邀在其中进行协作的应用程序。

![图示：合作伙伴用户受邀通过 Azure AD B2B. 进行协作的过程。](./media/enable-business-without-borders/enable-business-without-borders-fig1.png)

## <a name="how-to-implement-this-solution"></a>实现本解决方案的方式
以下步骤介绍之前讨论的实现每个 Azure AD B2B 协作的方法。 每个链接表示一组不同的文章，其中包含要在组织中实现的一组不同的说明/步骤：
- 了解[如何使用 Azure AD B2B 协作](https://azure.microsoft.com/documentation/articles/active-directory-b2b-detailed-walkthrough/)。
- 了解[如何使用 CSV 文件指定合作伙伴用户信息](https://azure.microsoft.com/documentation/articles/active-directory-b2b-references-csv-file-format/)。
