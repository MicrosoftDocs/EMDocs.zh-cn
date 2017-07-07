---
title: "开始使用企业移动性 + 安全性 | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 11/10/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 9938ab0e-19b8-49a2-91b5-61d69eb3dc01
ms.reviewer: mhamerof
ms.suite: ems
ms.custom: advanced-threat-analytics,cloud-app-security,information-protection,microsoft-identity-manager,microsoft-intune,rights-management
ms.translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: 7f82e8b0644765fc8cc14024cd65ef99733f1ecb
ms.contentlocale: zh-cn
ms.lasthandoff: 07/07/2017


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
一切内容均始于云标识，因此开始使用时需要做的第一件事就是建立组织的 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/)。 使用 Microsoft 的平台和安全关系图来保护你的标识、云应用和本地环境免受高级威胁的攻击。

可以完全通过云来执行此操作，或[通过 Azure Active Directory 同步当前的 Windows Server Active Directory 对象](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)，利用当前在本地标识管理中的投资。


### <a name="protect-your-organization-at-the-front-door"></a>在第一道防线保护组织
传统的安全解决方案在过去足以保护你的业务。 但随着移动性行业的发展，攻击风险日益增大，而向云端的过渡使得员工与其他用户、设备、应用和数据的交互变得更加复杂。 现在为了切实地保护公司，需要[采用更加全面和创新的安全性策略](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-front-door)，一种可以防止、检测和应对各种本地以及云端的威胁的策略。

### <a name="start-managing-devices"></a>开始管理设备
现在的大多数信息工作者都是移动办公，这使得移动设备上的工作效率成为提高竞争力的必要途径。 这些员工需要随时随地无缝访问所有公司应用和数据。 你需要确保公司数据是安全的并且管理成本较低。 IT 需要管理企业设备复杂性：从公司拥有的“选择自己的设备”(CYOD) 到个人拥有的用于工作的“自带设备”（BYOD）。

**分发企业拥有的设备**。 Intune 提供大量预配和管理解决方案，帮助在组织中[分发公司拥有的设备](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices)，这些解决方案与当今市场上的主要公司设备管理平台集成，包括 Apple 设备注册程序和 Samsung KNOX 移动安全平台。 通过使用 Intune 集中创作设备配置，可实现公司设备预配的高度自动化。

想象一下：将一个未开封的 iPhone 手机盒发放给员工。 员工打开手机后，完成公司自创的设置流程，在此过程中他必须进行身份验证。 这部 iPhone 手机无缝配置了安全策略（加密硬盘驱动器、设备 pin 等等）、电子邮件/Wi-Fi/VPN/证书配置文件和一系列基础应用。 然后，员工启动 Intune 公司门户应用来访问提供给他们的可选公司应用。

**启用使用受限的共享设备解决方案**。 任务工作者开始越来越多地使用移动技术。 例如，共享平板电脑现在对于零售店员工已经是司空见惯了。 无论是用于处理销售还是即时检查库存，平板电脑都有助于创造良好的顾客交互体验。 在这种情况下，用户体验的简单性至关重要。 出于此原因，发放给员工的平板电脑通常采用使用受限模式，使员工只能与单个业务线应用交互。 Intune 允许你批量预配、保护和集中管理这些可配置为在此使用受限模式下运行的共享 iOS 和 Android 平板电脑。

**在组织中启用 BYOD**。 BYOD 可以降低硬件开销或增加员工的移动工作效率选择，因此受到越来越多组织的青睐。 随着企业开始摆脱传统的企业拥有设备模式，他们必须[决定如何实施 BYOD 计划](https://docs.microsoft.com/enterprise-mobility-security/solutions/byod-design-considerations-guide)，允许员工使用个人设备完成某些工作任务。

现如今几乎人手一部手机，因此为什么还要往他们的口袋里再添一个？ 公司一直以来的主要难题就是说服员工将其个人设备注册到管理系统中，因为他们担心 IT 部门能看到其设备中的信息并对其设备进行处理。 在设备注册不可行的情况下，Intune 提供替代的 BYOD 方法，可简单地[管理包含公司数据的应用](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)。 与 Office 移动应用一样，即使是有问题的应用访问公司和个人数据，Intune 也能保护公司数据。

**使 Windows 10 部署和管理策略与业务、最终用户和IT需求保持一致**。 Windows 10 通过 Windows 7 和 Windows 8.1 中引入的技术为基础，提供新的部署功能、方案和工具，同时以一种服务概念引入新的 Windows，使操作系统保持最新。 这些变化需要用户[重新思考传统的部署过程](https://technet.microsoft.com/itpro/windows/plan/windows-10-deployment-considerations)。

部署 Windows 10 后，还需要[确定如何通过 Intune 最好地管理 Windows 10 电脑](https://docs.microsoft.com/intune/get-started/choose-how-to-manage-devices)，以满足最终用户的工作效率和业务需求。 有两种选择：将 Windows 10 电脑注册为一台移动设备，或安装 Intune 软件客户端，作为一台计算机来管理设备。

### <a name="manage-and-protect-company-data"></a>管理和保护公司数据
现在的大多数信息工作者都是移动办公，移动设备上的工作效率成为提高竞争力的必要途径。 这些员工需要在任何时候、任何位置都能够无缝访问所有公司应用和数据，而 EMS 可轻松进行此操作（不管是在本地还是云中）。

**保护本地公司数据**。 大多数企业移动性策略都以一个计划开始，让员工可以使用移动设备通过 Internet 安全访问电子邮件，但还需要能够安全地访问由移动设备访问的[本地公司数据](https://docs.microsoft.com/enterprise-mobility-security/solutions/conditional-access-intune-exchange)。 例如，许多组织仍然在公司网络上托管了本地数据和应用程序服务器（如 Microsoft Exchange）。 Intune 和 Microsoft 企业移动性 + 安全性 (EMS) 为 Exchange Server 提供了独一无二的集成式条件访问解决方案，确保在向 Intune 注册设备之前，任何移动应用都无法访问电子邮件，并且完全无需在公司网络边缘再部署一台网关计算机！

除了电子邮件，Intune 还支持对需要安全访问本地数据的移动应用（例如业务线应用服务器）启用访问权限。 为此，通常需要将用于访问控制的 Intune 托管证书与外围中的标准 VPN 网关或代理（如 Microsoft Azure AD 应用程序代理）结合使用。 在这些情况下，访问公司数据的唯一方法是将设备注册到管理系统中。 注册后，Intune 可确保访问公司数据的设备符合你的策略。

**保护 Office 365 公司数据**。 [在 Office 365 中保护公司数据（电子邮件、文档、即时消息等等）](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-office365-data-with-intune)既方便了你，又给用户带来了更加顺畅的体验。 Intune 和 Microsoft 企业移动性 + 安全性提供了独一无二的集成式条件性访问解决方案，确保用户、应用或设备在符合公司的合规性要求（已执行多重身份验证，已向 Intune 注册，使用托管应用、受支持的 OS 版本、设备 pin 和低用户风险配置文件等等）之前无法访问 Office 365 数据。 位于其各自应用存储中的 Office 移动应用可以与数据包含策略（可通过 Intune 配置）结合使用，使你能够避免与不受 IT 管理的应用（例如本机电子邮件应用）和存储位置（例如 Dropbox）共享数据。 此功能完全内置于 Office 365 和 EMS 中。 你无需部署其他基础结构便可获得此功能。

**安全地访问 Office 365并保护非托管设备上的数据**。 常见的 Office 365 部署做法是要求将设备注册到管理系统中，但并不是始终都有必要。 如果用户只需访问公司电子邮件和文档（通常是个人拥有的设备），那么可以使用 Office 移动应用（已向其[采用应用限制策略](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)）并完全跳过设备注册。

## <a name="leverage-cloud-security-and-protection"></a>利用云安全性和保护
EMS 提供标识驱动的安全解决方案，它是一种用来应对移动优先、云优先时代安全挑战的全面性方法。 通过 EMS，不仅可以保护共享的组织数据，还可以在安全漏洞可能造成损害之前识别它们。

### <a name="securely-share-data"></a>安全地共享数据
现今，已实现从多台设备跨组织边界进行信息共享。 公司面临的挑战是确定哪些数据需要保护，哪些数据不需要保护。 若要解决这一难题，可以通过 [Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)来对[敏感数据分类、加标签和保护](https://docs.microsoft.com/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario)以确保重要的公司数据不会遭到破坏，同时使用户可以安全地共享他们认为重要的数据来完成工作。

通过 Azure 信息保护，组织可以在创建或修改数据时分类、标记和保护数据。 使用 Azure 信息保护，用户可以：
- 根据机密性手动或自动地分类数据和添加标签
- 通过加密、身份验证和使用权限保护数据
- 为最终用户启用直观、非侵入式体验

### <a name="identify-and-protect-against-threats"></a>识别和防御威胁
<!-- Detect advanced threats on-premises and in the cloud (ATA, Azure AD, Cloud App Security) -->
随着更多的组织采取承担违约的态度，EMS 可通过创新行为分析和异常检测技术，帮助识别组织内的攻击者 - 本地则采用 [Microsoft 高级威胁分析](http://www.microsoft.com/ata)，云中则采用[Azure Active Directory](http://www.microsoft.com/identity) 和 [云应用安全性](http://www.microsoft.com/cloudappsecurity)。 借助云中海量数据集和机器学习驱动的 Microsoft 智能安全图，我们的威胁智能得到了增强。

高级威胁分析持续从用户、设备和资源的行为中学习，并进行调整以反映快速发展中的企业的变化。 随着策略越来越复杂，高级威胁分析使用行为分析来帮助用户调整和响应。

## <a name="full-service-it-from-the-cloud"></a>基于云的全面服务 IT
随着组织完成数字转换，基于云的全面服务 IT 将成为一项常规业务。 具有成熟云实施的公司将期望利用 EMS 提供的功能，实现长期的端到端标识和数据保护方案。

### <a name="identity-management-from-hire-to-retire"></a>从采用到停用的标识管理
Microsoft 保护基于云的标识已超过十年，借助 Azure Active directory，Microsoft 向企业客户提供相同的保护系统，以确保用户和管理员能通过更高的安全性和更好的管理履行各自的职责。

**数千个应用，一个标识**。 通过 Azure Active Directory Premium 获取对数千个云应用的单一登录和访问在本地运行的 Web 应用。 Azure Active Directory 管理工具使用非常方便，可实现协作并提供全面标识保护和自适应访问控制。

Azure AD 是一种云标识和访问管理解决方案，可为组织提供能从任何位置访问所需一切内容的权限。 通过为可访问云和本地资源的[服务型软件 (SaaS) 应用程序的用户提供通用标识](https://docs.microsoft.com/enterprise-mobility-security/solutions/thousands-apps-one-identity)，Azure Active Directory (Azure AD) 使用户的工作效率更高。

**实现业务无边界**。 组织需[使其员工能通过任何设备随时随地访问所有数据和应用程序](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-business-without-borders)。 用户需要相互合作，与合作伙伴合作，并与客户沟通。

这个新领域带来了传统工具无法应对的挑战和高级威胁。 由于新边界是用户，因此仅保护自己的网络是没有意义的。 在这种环境中提高工作效率和获得保护的关键是强大的标识解决方案。

**大规模管理访问权限**。 Azure AD 利用动态组成员身份规则和应用程序管理功能，提供一套工具来自动化[高级用户生命周期管理](https://docs.microsoft.com/enterprise-mobility-security/solutions/manage-access-at-scale)。

Azure AD Premium 不仅提供标识以便随时随地进行访问，还提供一组工具以便在组织内对 IT 资源进行自动化、保护和管理。 即使在云计算问世后，仍需要管理和控制 IT 操作，如呼叫支持人员以重置用户密码、管理用户组和请求应用程序。

**由云支持的保护**。 Azure AD Identity Protection 是一种安全服务，可让用户对影响组织标识的[风险事件和潜在漏洞有一个综合全面的了解](https://docs.microsoft.com/enterprise-mobility-security/solutions/cloud-powered-protection)。

Azure Active Directory Identity Protection 是独一无二的。 它使用计算机学习每天分析超过 10 TB 的行为和上下文数据，使用户能够发现可疑活动，并在必要时立即采取行动。

此外，Azure AD 条件性访问规则允许客户基于属性（如设备合规性或网络位置）控制对联机服务的访问。 可能会有以下区分：
- Azure AD 基于 MFA 的条件性访问
- Azure AD 基于位置的条件性访问
- Azure AD 基于设备的条件性访问

### <a name="protect-shared-files-and-saas-apps-with-policies-and-tracking"></a>使用策略和跟踪保护共享的文件和 SaaS 应用
EMS 将高级公司数据保护无缝地集成到业务节奏中，使保护公司信息免于有意和意外数据丢失变得简单。

**在内部和外部共享敏感数据**。 虽然许多数据泄露是由网络攻击造成的，但专家认为更多的原因在于人为错误，或者说是因为员工无意间或不慎泄漏敏感商业数据所致。 [通过设置适当的安全信息和数据丢失防护协议](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data)，几乎能够避免所有这类泄露。

EMS 允许 IT 管理员对电子邮件使用设置采用 Azure 权限管理策略模板。 使用权限附加在邮件上，以便在联机和脱机、组织防火墙内部和外部提供保护。

**跟踪共享数据使用情况并对数据滥用做出响应**。 [Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)是基于云的解决方案，可帮助组织对其文档和电子邮件进行分类、添加标签和保护。 这可以由定义规则和条件的管理员自动进行、由用户手动进行或是组合进行（在这种情况下会向用户提供建议）。

可使用 Azure 信息保护标签对文档和电子邮件应用分类。 执行此操作时，分类在任何时候都是可识别的，无论数据的存储位置在哪或者与谁共享数据。 永久性标签包括可视化标记，如页眉、页脚或水印。 元数据以明文形式添加到文件和电子邮件的标头，以便其他服务（如数据丢失防护解决方案）可以识别分类并执行相应的操作。

**通过灵活的部署和密钥管理选项，以自己的方式管理数据**。 为了遵守适用于组织的特别规定，你可能想要[自行管理 Azure 信息保护的租户密钥](https://docs.microsoft.com/en-us/information-protection/plan-design/plan-implement-tenant-key)，而不是由 Microsoft 管理你的租户密钥（默认设置）。 自行管理租户密钥也称为自带密钥 (BYOK)。

**批准和管理员工的 SaaS 应用程序**。 使用 [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 以批准或取消批准应用程序、强制执行数据丢失防护 (DLP)、控制权限和共享，并生成自定义报表和警报。

 Cloud App Security 是一个全面的解决方案，可帮助组织充分利用云应用程序的承诺，同时维持可控性并提高活动可见性。 它还会使跨云应用程序的关键数据更加安全。 借助有助于揭示影子 IT、评估风险、强制实施策略、调查活动和停止威胁的工具，组织可以安全地移到云中并保持对关键数据的控制力度。

**保护数据不受用户错误影响**。 过渡到移动方式和云后，员工的工作效率显著提高，但是用户、设备、应用与本地及云中的数据之间的复杂交互也为 IT 团队制造了新的盲区。 尽管组织可能不接受这种转移，但员工已经接受了。 由于这些元素之间的交互和攻击媒介的复杂性在增加，安全性仍然是企业的最大挑战。 IT 人员致力于维持企业数据可见性和对企业数据的控制和保护。

Cloud App Security 可实现对用户和数据活动的高度可见性，因此，当用户处理重要的公司数据[做出错误选择时它可以对公司进行保护](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake)。 此外，还可以获得云应用程序（包括 Office 365）的可见性和控制权。 通过 Azure 信息保护，我们将分类和标签与持久数据保护结合在一起，实现了内部和外部的安全文件共享。

### <a name="learn-more"></a>了解详细信息

[请访问 Microsoft 企业移动性 + 安全性页面](http://go.microsoft.com/fwlink/?LinkId=816837)

[了解企业移动性 + 安全性](learn-about-ems.md)

[免费试用 EMS](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-security-trial)

