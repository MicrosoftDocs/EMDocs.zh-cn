---
title: "Microsoft 365 企业版 | Microsoft Docs"
description: "概述并介绍了 Microsoft 365 企业版服务。"
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/15/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 14f22a558e2e437f1491033eb33858b377eeca9d
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2017
---
# <a name="microsoft-365-enterprise-overview"></a>Microsoft 365 企业版概述
Microsoft 365 企业版专为大型组织而设计，集成了 Office 365 企业版、Windows 10 企业版和企业移动性 + 安全性 (EMS)，让所有人都能够尽情挥洒创意，并安全地开展协作。 Microsoft 365 企业版包括 Windows 10 企业版，以及 Office 365 专业增强版包含的 Office 应用程序。

Windows 10 和 Office 365 专业增强版都在 3 月和 9 月通过半年频道发布了适用于企业的新功能。 通过半年频道发布的功能的支持期为 18 个月。 Microsoft Intune 和 System Center Configuration Manager 都提供可用于部署和更新 Windows 10 和 Office 365 专业增强版的功能。

本部分概述了 Microsoft 365 Enterprise 随附的 EMS 和 Office 365 服务，并介绍了一些必须掌握的核心概念，以便读者可以了解如何充分利用此解决方案来满足组织需求。 借助这些服务提供的功能，Microsoft 云企业管理员不仅可以保护公司员工的标识和设备，还可以控制对公司数据本身的访问（无论是在传输中，还是在静态状态下）。

|服务|描述|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD 提供一整套标识管理功能，包括多重身份验证、设备注册、自助式密码管理、自助式组管理、基于角色的访问控制、应用程序使用情况监视、各种审核以及安全监视和警报。|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|借助此服务，可以检测影响组织标识的潜在漏洞，并通过条件访问策略配置对低、中、高登录风险和用户风险的自动响应。|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|借助此服务，组织可以将永久有权执行特权操作的用户数降至最低；Azure AD Privileged Identity Management 引入了符合条件的管理员这一概念。符合条件的管理员应为偶尔（而不是每天）需要特权的用户。 在用户需要访问权限之前，此角色处于非活动状态。完成激活过程后，此管理员角色将在预先确定的一段时间内处于活动状态。|
|[Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure 信息保护是基于云的解决方案，属于 EMS E5 产品/服务，可有助于组织分类、标示和保护文档和电子邮件。 这可以由定义规则和条件的管理员自动进行、由用户手动进行或是组合进行（在这种情况下会向用户提供建议）。 可使用 Azure 信息保护标签对文档和电子邮件应用分类。 执行此操作时，分类在任何时候都是可识别的，无论数据的存储位置在哪或者与谁共享数据。 <br><br>Azure 信息保护策略设置受 [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms) 保护。 与标签的应用方式类似，使用 Rights Management 应用的保护会一直为文档和电子邮件提供保护，与位置无关（无论是在组织内外、网络内外、文件服务器内外，还是在应用程序内外）。|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune 是一种基于云的企业移动管理 (EMM) 服务，可帮助员工提高工作效率，同时保护企业数据。 Intune 与 Azure AD 紧密集成以提供标识和访问控制，Intune 可用于管理设备和应用程序。 [Intune 设备管理](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)功能用于配置和保护用户设备，包括 Windows 电脑。 <br><br>Intune 设备管理功能支持[自带设备办公 (BYOD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod) 注册，以便用户能够注册个人手机、平板电脑或电脑；此外，还支持[企业自有设备 (COD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) 注册，从而支持自动注册、共享设备或预授权的注册需求配置等管理方案。 为提高安全性，甚至可以要求必须通过 MFA 才能注册设备。 注册管理功能后，Intune 可以配置设备功能和设置，以实现对公司资源的安全访问。|


下面列出了 Windows 10、Office 365 专业增强版、Microsoft Intune 和 System Center Configuration Manager 的最新版本：

|     |**半年频道（定向）**|**半年频道**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update（即将推出）|版本 1703|
|**Office 365 专业增强版**|版本 1708|版本 1705|
|**Intune**|不适用|版本 1708|
|**System Center Configuration Manager**|Technical Preview 版本 1708|版本 1706<sup>*</sup>|

<sup>*</sup>System Center Configuration Manager 最新分支的更新 1706 作为控制台内更新提供，用于运行版本 1606、1610 或 1702 的之前安装的网站。

> [!NOTE]
> Microsoft Azure 服务也会定期更新，但没有按版本号划分的参考资料。 若要查看 Azure 服务的最新更新和即将发布的更新，请参阅[云平台路线图](https://www.microsoft.com/cloud-platform/roadmap)。

若要详细了解这些版本提供的功能，请参阅以下文章：
- [Windows 10 中的新增功能](https://docs.microsoft.com/windows/whats-new/)
- [Windows 10 发布信息](https://technet.microsoft.com/windows/release-info)
- [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Office 365 客户端更新频道版本](https://technet.microsoft.com/office/mt465751)
- [Microsoft Intune 新增功能](https://docs.microsoft.com/intune/whats-new)
- [System Center Configuration Manager 中的新增功能](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [System Center Configuration Manager Technical Preview 1708 中的功能](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="security-best-practices-and-recommendations"></a>安全最佳做法和建议
并不存在适用于所有客户环境的最佳建议，[推荐的安全策略和配置](microsoft-365-policies-configurations.md)一文介绍了应了解的重要安全最佳实践概念。 本文还介绍了一些通用的 Microsoft 建议，这些建议针对如何在 Microsoft 云中应用策略和配置，以确保员工在安全的环境中高效工作。


## <a name="deploy-windows-10-and-office-365-proplus"></a>部署 Windows 10 和 Office 365 专业增强版
了解如何部署 Windows 10 和 Office 365 专业增强版，以及如何集成到 Microsoft Azure Active Directory (Azure AD) 或本地 Active Directory 域服务 (AD DS) 中。 使用 Intune、System Center Configuration Manager 和组策略，将 Windows 10、Office 365 专业增强版和其他业务线应用程序部署到新设备，或将现有设备升级到 Windows 10，以便管理设备。

有关详细信息，请参阅以下文章：
- [Windows 10 部署注意事项](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Office 365 专业增强版的部署指南](https://support.office.com/article/f99f8cd0-e648-4834-8f45-f5637351899d)
- [在企业中部署 Office 365 专业增强版的最佳做法指南](https://support.office.com/article/31a384ca-650c-4265-b76c-a87b414fd8b8)
- [使用 Intune 将 Office 365 专业增强版应用程序分配到 Windows 10 设备](https://docs.microsoft.com/intune/apps-add-office365)

若要获取部署 Microsoft 365 方面的帮助，请[联系 FastTrack](https://fasttrack.microsoft.com/microsoft365)。

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>管理 Windows 10 和 Office 365 专业增强版的更新
单击以下链接，可以了解如何最大限度地控制 Windows 10 和 Office 365 专业增强版的质量和功能更新。 了解如何有效控制带宽使用，并应用最新功能和安全更新程序，不断更新 Windows 和 Office。

有关详细信息，请参阅以下文章：
- [Windows 即服务概述](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Office 365 专业增强版的更新频道概述](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
- [使用 Intune 管理软件更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [使用 System Center Configuration Manager 部署 Windows 10 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [使用 Configuration Manager 管理 Office 365 专业增强版](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup>Microsoft 建议当前使用 Configuration Manager 管理 Windows 更新的组织，继续对 Windows 10 客户端计算机这样做。

## <a name="next-steps"></a>后续步骤
[详细了解 Microsoft 365 企业版服务](services-overview.md)

[Microsoft 365 Enterprise 产品页](https://www.microsoft.com/microsoft-365/enterprise)

[云平台路线图](https://www.microsoft.com/cloud-platform/roadmap)

