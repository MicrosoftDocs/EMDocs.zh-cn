---
title: "开始使用企业移动性 + 安全性 | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 1df56825-c0d1-48ac-a294-5ebd1667bc38
ms.reviewer: mhamerof
ms.suite: ems
ms.custom: advanced-threat-analytics,cloud-app-security,information-protection,microsoft-identity-manager,microsoft-intune,rights-management
experimental: true
experiment_id: jeffgilb-length-20161110
ms.translationtype: Human Translation
ms.sourcegitcommit: ed952bd866758978ed4348c70da826eb519b4733
ms.openlocfilehash: 78b0119b52ca1459fd644d093bf7f364b80e8ce1
ms.contentlocale: zh-cn
ms.lasthandoff: 12/08/2016


---
# <a name="start-using-enterprise-mobility--security"></a>开始使用企业移动性 + 安全性

进行数字转换的组织需要保护自己免受新的威胁和挑战，同时还要求 IT 不断追求更高的效率和性价比。 此外，在当今云优先、移动优先的世界中，用户希望在任何地方通过任何设备都可以高效工作。 使用 EMS，可以获得全面的解决方案来帮助你：

- **在云中控制标识 + 访问**。 跨设备、数据中心和云，集中管理标识并保护单一登录的安全。
- **获取标识驱动的安全性**。 全面、智能地防御当前的高级攻击。
- **管理移动设备 + 应用**。 从一个位置安全地管理 iOS、Android 和 Windows 上的应用和数据。
- **保护信息**。 智能地保护公司数据并实现安全协作。

阅读下文，了解 EMS 如何让 IT 能够自信地提供人们欢迎的安全和不受限制的工作效率。 从本地过渡到云、利用云安全性和保护以及最终通过云提供完整的服务 IT 时，这些示例方案将有助于入门 EMS。

## <a name="transition-from-on-premises-to-the-cloud"></a>从本地过渡到云
EMS 包含许多服务和功能，可以根据业务需求和熟练程度选择使用。

### <a name="establish-azure-ad-identity"></a>建立 Azure AD 标识
一切内容均始于云标识，因此开始使用时需要做的第一件事就是建立组织的 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/)。 可以完全通过云来执行此操作，或[通过 Azure Active Directory 同步当前的 Windows Server Active Directory 对象](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)，利用当前在本地标识管理中的投资。

### <a name="protect-your-organization-at-the-front-door"></a>在第一道防线保护组织
传统的安全解决方案在过去足以保护你的业务。 但随着移动性行业的发展，攻击风险日益增大，而向云端的过渡使得员工与其他用户、设备、应用和数据的交互变得更加复杂。 现在为了切实地保护公司，需要[采用更加全面和创新的安全性策略](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-front-door)，一种可以防止、检测和应对各种本地以及云端的威胁的策略。

### <a name="start-managing-devices"></a>开始管理设备
要确保公司数据安全且管理成本低，同时还要管理企业中的设备复杂性，传统 IT 可能难以完成这些工作。 EMS 使你可以轻松支持多种设备管理方案：从公司拥有的“自择设备办公”(CYOD) 到个人拥有的用于工作的“自带设备办公”(BYOD)。

- **分发企业拥有的设备**。 Intune 提供大量预配和管理解决方案，帮助在组织中[分发公司拥有的设备](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices)，这些解决方案与当今市场上的主要公司设备管理平台集成，包括 Apple 设备注册程序和 Samsung KNOX 移动安全平台。
- **启用使用受限的共享设备解决方案**。 任务工作者开始越来越多地使用移动技术。 无论是用于处理销售还是快速检查清单，可能只运行单一业务线应用的平板电脑通常会以使用受限的模式分发给员工。 Intune 允许你批量预配、保护和集中管理这些可配置为在此使用受限模式下运行的共享 iOS 和 Android 平板电脑。
- **在组织中启用 BYOD**。 BYOD 可以降低硬件开销或增加员工的移动工作效率选择，因此受到越来越多组织的青睐。 随着企业开始摆脱传统的企业拥有设备模式，他们必须[决定如何实施 BYOD 计划](https://docs.microsoft.com/enterprise-mobility-security/solutions/byod-design-considerations-guide)，允许员工使用个人设备完成某些工作任务。
- **使 Windows 10 部署和管理策略与业务、最终用户和IT需求保持一致**。 Windows 10 通过 Windows 7 和 Windows 8.1 中引入的技术为基础，提供新的部署功能、方案和工具，同时以一种服务概念引入新的 Windows，使操作系统保持最新。 这些变化需要用户[重新思考传统的部署过程](https://technet.microsoft.com/itpro/windows/plan/windows-10-deployment-considerations)。 部署 Windows 10 后，还需要[确定如何通过 Intune 最好地管理 Windows 10 电脑](https://docs.microsoft.com/intune/get-started/choose-how-to-manage-devices)，以满足最终用户的工作效率和业务需求。 有两种选择：将 Windows 10 电脑注册为一台移动设备，或安装 Intune 软件客户端，作为一台计算机来管理设备。

### <a name="manage-and-protect-company-data"></a>管理和保护公司数据
现在的大多数信息工作者都是移动办公，移动设备上的工作效率成为提高竞争力的必要途径。 这些员工需要在任何时候、任何位置都能够无缝访问所有公司应用和数据，而 EMS 可轻松进行此操作（不管是在本地还是云中）。
- **保护本地公司数据**。 大多数企业移动性策略都以一个计划开始，让员工可以使用移动设备通过 Internet 安全访问电子邮件，但还需要能够安全地访问由移动设备访问的[本地公司数据](https://docs.microsoft.com/enterprise-mobility-security/solutions/conditional-access-intune-exchange)。 例如，许多组织仍然在公司网络上托管了本地数据和应用程序服务器（如 Microsoft Exchange）。
- **保护 Office 365 公司数据**。 [在 Office 365 中保护公司数据（电子邮件、文档、即时消息等等）](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-office365-data-with-intune)既方便了你，又给用户带来了更加顺畅的体验。 Office 365 和 EMS 提供了独一无二的集成式条件性访问解决方案，确保用户、应用或设备在符合公司的合规性要求（已执行多重身份验证，已向 Intune 注册，使用托管应用、受支持的 OS 版本、设备 pin 和低用户风险配置文件等等）之前无法访问 Office 365 数据。
- **安全地访问 Office 365并保护非托管设备上的数据**。 常见的 Office 365 部署做法是要求将设备注册到管理系统中，但并不是始终都有必要。 如果用户只需访问公司电子邮件和文档（通常是个人拥有的设备），那么可以使用 Office 移动应用（已向其[采用应用限制策略](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)）并完全跳过设备注册。

## <a name="leverage-cloud-security-and-protection"></a>利用云安全性和保护
EMS 提供标识驱动的安全解决方案，它是一种用来应对移动优先、云优先时代安全挑战的全面性方法。 通过 EMS，不仅可以保护共享的组织数据，还可以在安全漏洞可能造成损害之前识别它们。

### <a name="securely-share-data"></a>安全地共享数据
现今，已实现从多台设备跨组织边界进行信息共享。 公司面临的挑战是确定哪些数据需要保护，哪些数据不需要保护。 若要解决这一难题，可以通过 [Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)来对[敏感数据分类、加标签和保护](https://docs.microsoft.com/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario)以确保重要的公司数据不会遭到破坏，同时使用户可以安全地共享他们认为重要的数据来完成工作。

### <a name="identify-and-protect-against-threats"></a>识别和防御威胁
<!-- Detect advanced threats on-premises and in the cloud (ATA, Azure AD, Cloud App Security) -->
随着更多的组织采取承担违约的态度，EMS 可通过创新行为分析和异常检测技术，帮助识别组织内的攻击者 - 本地则采用 [Microsoft 高级威胁分析](http://www.microsoft.com/ata)，云中则采用[Azure Active Directory](http://www.microsoft.com/identity) 和 [云应用安全性](http://www.microsoft.com/cloudappsecurity)。 借助云中海量数据集和机器学习驱动的 Microsoft 智能安全图，我们的威胁智能得到了增强。

## <a name="full-service-it-from-the-cloud"></a>基于云的全面服务 IT
随着组织完成数字转换，基于云的全面服务 IT 将成为一项常规业务。 具有成熟云实施的公司将期望利用 EMS 提供的功能，实现长期的端到端标识和数据保护方案。

### <a name="identity-management-from-hire-to-retire"></a>从采用到停用的标识管理
Microsoft 保护基于云的标识已超过十年，借助 Azure Active directory，Microsoft 向企业客户提供相同的保护系统，以确保用户和管理员能通过更高的安全性和更好的管理履行各自的职责。
- **数千个应用，一个标识**。 Azure AD 是一种云标识和访问管理解决方案，可为组织提供能从任何位置访问所需一切内容的权限。 通过为可访问云和本地资源的[服务型软件 (SaaS) 应用程序的用户提供通用标识](https://docs.microsoft.com/enterprise-mobility-security/solutions/thousands-apps-one-identity)，Azure Active Directory (Azure AD) 使用户的工作效率更高。
- **实现业务无边界**。 组织需[使其员工能通过任何设备随时随地访问所有数据和应用程序](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-business-without-borders)。 用户需要相互合作，与合作伙伴合作，并与客户沟通。
- **大规模管理访问权限**。 Azure AD 利用动态组成员身份规则和应用程序管理功能，提供一套工具来自动化[高级用户生命周期管理](https://docs.microsoft.com/enterprise-mobility-security/solutions/manage-access-at-scale)。
- **由云支持的保护**。 Azure AD Identity Protection 是一种安全服务，可让用户对影响组织标识的[风险事件和潜在漏洞有一个综合全面的了解](https://docs.microsoft.com/enterprise-mobility-security/solutions/cloud-powered-protection)。

### <a name="protect-shared-files-and-saas-apps-with-policies-and-tracking"></a>使用策略和跟踪保护共享的文件和 SaaS 应用
EMS 将高级公司数据保护无缝地集成到业务节奏中，使保护公司信息免于有意和意外数据丢失变得简单。
- **在内部和外部共享敏感数据**。 虽然许多数据泄露是由网络攻击造成的，但专家认为更多的原因在于人为错误，或者说是因为员工无意间或不慎泄漏敏感商业数据所致。 [通过设置适当的安全信息和数据丢失防护协议](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data)，几乎能够避免所有这类泄露。
- **跟踪共享数据使用情况并对数据滥用做出响应**。 [Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)是基于云的解决方案，可帮助组织对其文档和电子邮件进行分类、添加标签和保护。 这可以由定义规则和条件的管理员自动进行、由用户手动进行或是组合进行（在这种情况下会向用户提供建议）。
- **通过灵活的部署和密钥管理选项，以自己的方式管理数据**。 为了遵守适用于组织的特别规定，你可能想要[自行管理 Azure 信息保护的租户密钥](https://docs.microsoft.com/en-us/information-protection/plan-design/plan-implement-tenant-key)，而不是由 Microsoft 管理你的租户密钥（默认设置）。 自行管理租户密钥也称为自带密钥 (BYOK)。
- **批准和管理员工的 SaaS 应用程序**。 使用 [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 以批准或取消批准应用程序、强制执行数据丢失防护 (DLP)、控制权限和共享，并生成自定义报表和警报。
- **保护数据不受用户错误影响**。 我们提供对用户和数据活动的高度可见性，因此，当用户处理重要的公司数据时[做出错误选择](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake)，你可以对公司进行保护。 Microsoft Cloud App Security 对云应用（包括 ffice 365）提供可见性和控制。 通过 Azure 信息保护，我们将分类和标签与持久数据保护结合在一起，实现了内部和外部的安全文件共享。


### <a name="learn-more"></a>了解详细信息

[请访问 Microsoft 企业移动性 + 安全性页面](http://go.microsoft.com/fwlink/?LinkId=816837)

[了解企业移动性 + 安全性](learn-about-ems.md)

[免费试用 EMS](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-security-trial)

