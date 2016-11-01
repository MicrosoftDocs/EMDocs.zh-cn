---
title: "大规模管理访问权限"
description: "大规模管理访问权限"
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 0292919a-af10-4a25-8916-c704aed643f6
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c20f69b821a2acfbf2fa399b960b60fc31dbf502
ms.openlocfilehash: 28b83995ab2689cffa048cbf2ccdd53a3d9b1421


---

# 大规模管理访问权限
Microsoft 自成立以来一直在为各大组织提供支持。 Microsoft 不仅提供标识以便随时随地进行访问，还提供一组工具以便在组织内对 IT 资源进行自动化、保护和管理。 即使在云计算问世后，仍需要管理和控制 IT 操作，如呼叫支持人员以重置用户密码、管理用户组和请求应用程序。

## 企业移动性 + 安全性可提供哪些帮助？
企业移动性 + 安全性 (EMS) 是一个不仅从设备自身本机保护公司数据，还采用身份、设备、应用和数据这四个保护层提供更多保护的综合云解决方案。 EMS 帮助你解决移动优先、云优先世界中的其中一个主要挑战，即如何在 Azure Active directory (Azure AD) 中提供一组全面型工具，帮助你实现以下目的：
- 高级用户生命周期管理
- 低 IT 开销和成本
- 监视标识桥


### 建议的解决方案
建议采用 Azure AD Premium 解决方案为组织实现标识访问管理。
#### 高级用户生命周期管理
Azure AD 利用动态组成员身份规则和应用程序管理功能，提供自动化的高级用户生命周期管理。

- 对于拥有本地 HR 的组织，Microsoft Identity Manager 在 Windows Server Active Directory 中建立用户标识。
- 对于拥有服务型软件 (SaaS) 交付 HR 的组织，Azure AD 当前与 Workday 集成，将来还将集成更多应用。
- Azure AD Connect 在 Windows Server Active Directory 与 Azure AD 之间同步用户和组。
- Azure AD 为 Office 365 和其他 Microsoft 联机服务提供基于组的自动授权。

![显示 Azure AD Connect 如何同步 Windows Server Active Directory 与 Azure Active Directory 之间的用户和组的图形](./media/ManageAccessAtScale/fig1.png)
#### 应用程序管理
有多少用户愿意记住日用的每个应用程序的密码？ [单一登录](https://azure.microsoft.com/en-us/documentation/articles/active-directory-appssoaccess-whatis/)解决了这一常见问题：可针对组织中所有应用程序配置单个用户帐户和密码，并使用它登录到多个 SaaS 应用程序。 此功能可用于 Office 365 等 Microsoft 云应用程序和 Salesforce、ServiceNow 和 Workday 等第三方应用程序。

 此外，也可通过 [Azure AD 应用程序代理](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/)使用本地应用程序，它以服务解决方案的形式向所有本地应用程序提供简单、安全且经济高效的远程访问。 远程员工可不受限于工公司网络而访问本地资源，并且无需 IT 实现 VPN、DMZ 环境或反向代理。

 - 云中操作，可以节省时间和资金。 本地解决方案要求设置和维护 DMZ、边缘服务器或其他复杂基础结构。
 - 相比本地解决方案，它更加易于设置和保护，因为不必允许任何入站连接通过防火墙。
 - 提供更高安全性。 使用 Azure AD 应用程序代理发布应用时，可利用 Azure 中丰富的授权控件和安全分析功能。 这意味着无需更改任何应用，即可获得适用于所有现有应用的高级安全功能。
 - 为用户提供始终如一的身份验证体验。 提供单一登录，最终用户使用一个密码即可轻易访问高效完成工作所需的所有应用。

#### 低 IT 开销和成本
Azure AD Premium 还提供密码重置、组管理和应用管理功能的自助服务，可提高组织中 IT 人员和最终用户的工作效率。 用户无需呼叫支持人员并浪费时间讲电话，提供大量信息，通过电子邮件或电话不安全地获取临时密码。
- 它适用于联合身份验证、密码同步或仅限云的用户帐户。 此外，还实施所有本地密码策略。
- 所有通信均采用特定于租户的密钥并通过 HTTPS 进行加密。
- 用户可以实时更新其 AD 密码或解锁其 AD 帐户。
- 向用户和管理员发送实时通知。

![显示 Azure Active Directory 如何在本地和云中安全地向最终用户提供自助服务密码重置功能的图形。  ](./media/ManageAccessAtScale/fig2.png)

#### 监视标识桥
Azure AD Connect Health 可帮助组织监视和深入了解其本地标识基础结构和同步服务，并通过向密钥标识组件（如 AD FS 服务器、Azure AD Connect 服务器和 Active Directory 域控制器）提供监视功能以保持 Office 365 和 Microsoft Online Services 的可靠连接。

- 通过 Azure 门户单击“审核和合规性”。
- 取证和调查：帮助 IT 管理员了解活动及其执行者、发生位置和时间。
- 活动报告：提供审核、登录、SSPR、组活动、应用活动、应用设置等。
- 安全报告：通过标识保护提供丰富的安全异常缓解措施和解决办法。

![显示 Azure AD Connect Health 如何帮助组织监视密钥标识组件（如 AD FS 服务器、Azure AD Connect 服务器和 Active Directory 域控制器）的图形。 ](./media/ManageAccessAtScale/fig3.png)

## 如何实现高级用户生命周期管理
下面介绍几个示例以及可用于实现此解决方案的步骤：
1. 在实际方案中，组织雇用专业人员，并将其用户作为市场营销团队的成员添加到 HR 系统。
2.  假设已通过目录同步集成了本地 Active Directory 和 Azure AD，则本地 Azure AD Connect 会将用户帐户与 Azure AD 进行同步。
3.  用户帐户显示在 Azure AD 上后，便可以创建自动向其分配市场营销用户的动态组成员身份规则。
4.  市场营销组自动填充用户后，便可以利用基于组的选择性授权，以便用户添加到特定许可证组，如 Azure AD Premium 或 Office 365 企业版 E5。
  - 在此示例中，它向用户提供了执行工作所需的所有 Office 365 应用的访问权限，以及执行其他自动化任务的 Azure AD Premium 访问权限。

如果员工因某种原因需要离开公司，可从 HR 系统将其删除，这将自动删除之前向其预配的所有应用程序和资源的访问权限。 如果员工仅需调动到另一部门，则从市场营销团队中删除用户并将其添加到新部门的动态组时，动态组成员身份规则将自动删除其对市场营销应用程序的访问权限，并添加对另一部门应用程序的访问权限。

### 如何管理云和本地应用程序
使用 Azure AD 添加、部署和管理 Microsoft 及第三方 SaaS 应用程序时，可执行以下步骤。
- 了解有关[将应用程序与 Azure AD 集成](https://azure.microsoft.com/documentation/articles/active-directory-integrating-applications-getting-started/)的详细信息。
- 了解有关[为 SaaS 应用启用单一登录](https://azure.microsoft.com/documentation/articles/active-directory-sso-integrate-saas-apps/)的详细信息。
- 了解有关 [Managing access to apps](https://azure.microsoft.com/documentation/articles/active-directory-managing-access-to-apps/)（管理应用访问权限）的详细信息。

## 如何实现密码重置自助服务门户
默认情况下，Azure AD 附带一免费功能，每位管理员都可用它自助重置自身密码。

使用 Azure AD Premium 时，可以通过为用户提供密码重置自助服务门户功能超越 IT 管理员职责。 可以快速启用用户密码重置策略，以便将相同的丰富管理功能扩展到每位用户。

详细了解在 Azure AD 租户上[使用密码自助服务门户的先决条件、启用及配置方式](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)。

## 如何实现 Azure AD Connect Health
可以查看 [Azure AD Connect Health 文档](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health/)以收集有关该工具、其功能及可执行以开始在组织中使用它的步骤的详细信息。

[Azure 门户](https://ms.portal.azure.com)提供 Azure AD Connect Health，该功能要求在要监视的本地域控制器上安装运行状况代理。 了解有关[如何安装运行状况代理](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health-agent-install/)的详细信息。

域控制器 (DC) 仪表板提供有关环境运行状况和操作状态的单一见解，管理员可在其中轻松找到属于 FSMO 角色所有者、具有活动警报、属于全局编录的 DC 以及其他列，如“可访问的 PDC”、“可访问的 GC”、“SYSVOL 状态”等：

![显示含所选域控制器相关信息的域控制器仪表板的屏幕截图。 ](./media/ManageAccessAtScale/fig4.png)

此外，管理员可按 DC 的对应域或站点对其进行分组：

![显示按站点分组的域控制器的屏幕截图。 ](./media/ManageAccessAtScale/fig5.png)

“复制状态”仪表板显示复制拓扑在环境中的外观，以及每个命名环境上次复制尝试的相关信息：

![显示含上次复制尝试相关信息的“复制状态”仪表板的屏幕截图。 ](./media/ManageAccessAtScale/fig6.png)

警报详细信息包含有关引起警报的问题、所需修复和其他疑难解答资源链接的详细信息：

![显示特定警报相关详细信息的屏幕截图。 ](./media/ManageAccessAtScale/fig7.png)

通过 AD Connect Health 性能监视，可简单地比较受监视 DC 之间的性能及各方面不同指标：

![显示所选域控制器的性能监视的屏幕截图。 ](./media/ManageAccessAtScale/fig8.png)



<!--HONumber=Oct16_HO3-->


