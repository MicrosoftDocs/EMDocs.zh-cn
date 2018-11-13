---
title: 第一道防线 | Microsoft Docs
description: 此方案描述如何使用企业移动性 + 安全性来保护标识，通过采用 Microsoft Azure Active Directory Identity Protection 和 Azure Active Directory Privileged Identity Management 功能安全访问公司资源。
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: solution
ms.prod: ''
ms.service: active-directory
ms.assetid: c9aeabcf-db9b-4a35-b1bc-61331c464165
ms.reviewer: v-craic
ms.suite: ems
ms.custom: microsoft-identity-manager
ms.openlocfilehash: f3092623cb8cd7fbfbb525a79ac91c6d93f80ecb
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196893"
---
# <a name="protect-at-the-front-door"></a>第一道防线

传统的安全解决方案在过去足以保护你的业务。 但随着移动性行业的发展，攻击风险日益增大，而向云端的过渡使得员工与其他用户、设备、应用和数据的交互变得更加复杂。 现在为了切实地保护公司，需要采用更加全面和创新的安全性策略，一种可以防止、检测和应对本地和云端的各种威胁的策略。

在超过 63% 的数据泄露中，攻击者通过安全性弱、采用默认设置或者被盗的用户凭据获取公司网络的访问权限。  Microsoft 标识驱动安全着眼于用户凭据，通过管理和保护标识（包括特权和非特权标识）杜绝凭据盗用。


## <a name="how-can-enterprise-mobility--security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？

企业移动性 + 安全性 (EMS) 安全策略首先采用一个受保护的常用标识，通过基于风险的[条件访问](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access/)安全访问本地和云端的所有公司资源。 通过此策略，IT 可使用新颖高级的基于风险的条件访问为公司资源建立第一道防线。 EMS 为访问数千的应用提供一个受保护的常用标识，有助于 IT 管理和保护特权标识。

## <a name="recommended-solution"></a>建议的解决方案

为了满足此方案的要求，EMS 使用 [Azure AD Identity Protection](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/) 和 [Azure AD Privileged Identity Management](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-configure/)。 通过实施这些技术，组织将能够：

- 从基于机器学习的威胁检测的合并视图中获得见解
- 修正建议
- 执行风险严重性计算
- 执行基于风险的条件访问可自动阻止可疑登录和被盗用的凭据
- 若有需要，强制执行按需实时管理访问
- 使用“警报”、“审核报告”和“访问评审”

下图总结了此方案涉及的功能以及如何使用这些功能保护资源：

![保护资源](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig1.png)

## <a name="how-to-implement-this-solution"></a>实现本解决方案的方式

请按照以下步骤实施 Azure AD Identity Protection 和 Azure AD Privileged Identity Management：

- 步骤 1：启用 Azure AD Identity Protection
- 步骤 2：配置 Azure AD Identity Protection
- 步骤 3：监视对资源的访问
- 步骤 4：启用 Azure AD Privileged Identity Management
- 步骤 5：配置 Azure AD Privileged Identity Management
- 步骤 6：Privileged Identity Management 操作


## <a name="how-to-protect-your-resources-at-the-front-door"></a>如何建立资源保护的第一道防线

不同组织对事件优先级有不同的理解。 对某个行业至关重要的事件可能对另一个行业并不重要。 因此，应该首先了解 Azure AD Identity Protection 如何划分[风险级别](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#detection-and-risk)，即风险事件的严重性指示（“高”、“中”或“低”）。 Azure AD Identity Protection 还可评估用户标识被盗用的可能性并分配其自己的风险级别，称为[用户的风险级别](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#what-is-a-user-risk-level)。 Azure AD Identity Protection 将识别[漏洞](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-vulnerabilities/)并为其分配风险级别。 风险有[不同类型](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/)，每一种风险根据其重要程度划分级别。 按照第 1 到 3 步执行操作，使用 Azure AD Identity Protection 启用、实施和监视资源。

此解决方案的第二阶段（第 4 到 6 步）将实施 Azure Active Directory (AD) Privileged Identity Management 以发现、限制和监视特权标识。 使用 Azure 的组织可[在 Azure AD 中分配角色](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/)，Azure AD Privileged Identity Management 可管理[其中一些角色](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-roles/)。

### <a name="step-1-enable-azure-ad-identity-protection"></a>步骤 1：启用 Azure AD Identity Protection

实施此解决方案前，请确保 [Azure AD Premium 许可证](https://azure.microsoft.com/documentation/articles/active-directory-get-started-premium/)已分配给最终用户。 如果使用联合域且要在云中强制执行密码更改以将密码写回本地，需要启用[密码写回](https://azure.microsoft.com/documentation/articles/active-directory-passwords-getting-started/)。 查看完这些要求后，从市场安装 Azure AD Identity Protection，以[启用 Azure AD Identity Protection](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-enable/)。 完成安装后，将拥有对 Azure AD Identity Protection 仪表板的访问权，此仪表板可能会显示为空，如下图所示。

![Azure AD Identity Protection](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig2.png)

### <a name="step-2-configure-azure-ad-identity-protection"></a>步骤 2：配置 Azure AD Identity Protection

计划实施 Azure AD Identity Protection 时，必须首先定义以下策略：

- [多重身份验证注册策略](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#multi-factor-authentication-registration-policy)：使 IT 能够对用户强制执行多重身份验证 (MFA)。
- [用户风险策略](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#user-risk-security-policy)：使 IT 能够设置用户风险安全策略以根据风险级别在登录时阻止用户。
- [登录风险策略](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#sign-in-risk-security-policy)：使 IT 能够评估特定登录的风险，并根据此结果使用预定义条件和规则缓解风险。

这些策略位于“配置”部分下的 Azure AD Identity Protection 仪表板中，如下面屏幕所示：

![策略](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig3.png)

除了配置安全策略外，还可自定义哪些用户将收到警报。 应使用 Azure AD Identity Protection 仪表板中的“设置”部分下的“警报”选项，如下图所示：

![警报](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig4.png)

请注意：在此配置中，仅当用户风险级别为“高”时，用户才会收到警报。

### <a name="step-3-monitor-and-remediation"></a>步骤 3：监视和修正

连续监视是任何安全操作的必要组成部分。 通过采用 Azure AD Identity Protection [调查](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#investigation)功能，IT 将通过通知和修正建议获得对基于机器学习的威胁检测的见解。 可使用 Azure AD Identity Protection 仪表板快速访问当前环境并根据重要程度轻松识别应处理的问题。 或者，可在 Azure AD Identity Protection 仪表板中的“调查”部分下的以下区域中缩小调查范围：

![调查](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig5.png)

开始调查每个区域时，管理员可对[风险用户](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#mitigating-user-risk-events)或[登录事件](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#mitigating-sign-in-risk-events)执行风险缓解操作。 例如，如果识别[不可能前往异常位置](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/#impossible-travel-to-atypical-locations)（下面屏幕中的第二个事件）等安全事件，可执行操作（例如通过强制重置密码）以[修正](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#remediating-user-risk-events)此威胁。

![风险事件](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig6.png)

也可利用[Azure AD Premium 访问和使用情况报告](https://azure.microsoft.com/documentation/articles/active-directory-view-access-usage-reports/)获取有关用户行为和潜在威胁的详细信息。

### <a name="step-4-enable-azure-ad-privileged-identity-management"></a>步骤 4：启用 Azure AD Privileged Identity Management

若要获得对 Azure AD Privileged Identity Management 的访问权限，必须首先[从市场安装它](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-getting-started/)。 Azure AD Privileged Identity Management 和 Azure 多重身份验证 (MFA) 配合使用有助于 IT 管理访问权限以保护应用程序和服务。 安装 Azure AD Privileged Identity Management 后，将执行测试以验证是否可使用 MFA。 单击此选项验证帐户时，将重定向到一个网页，你需要在此网页上键入凭据。 如果帐户未启用 MFA，将出现类似于以下屏幕的消息：

![登录屏幕](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig7.png)

单击“立即设置”，然后执行向导操作。 需要键入手机或电话号码用于验证。 完成此向导后，将看到验证完成消息：

![验证](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig8.png)

### <a name="step-5-configure-azure-ad-privileged-identity-management"></a>步骤 5：配置 Azure AD Privileged Identity Management

初始配置通过使用[安全向导](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-security-wizard/)执行，其具有三个阶段，如“保护组织”边栏选项卡所示：

![安全向导](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig9.png)

在第一个阶段中，将查看 Azure AD Privileged Identity Management 发现的[特权角色](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-roles/)。 第二个阶段的目的是减少组织中分配有永久特权角色的用户数量，可最大程度地直接减少安全漏洞。 在最后一个阶段，用户可查看特权角色中对用户进行的更改。

如果在此流程中，将管理角色授予其他用户，则此用户有资格执行此角色任务，也就是说，在需要执行此角色所需任务时，可[激活此角色](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-activate-role/)。

### <a name="step-6-privileged-identity-management-operations"></a>步骤 6：Privileged Identity Management 操作

安装和配置 Azure AD Privileged Identity Management 后，可执行初始评估以验证当前角色架构和警报。 在“特权标识管理”边栏选项卡中单击“管理特权角色”，将看到类似于下图所示的仪表板：

![特权角色](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig10.png)

在此仪表板中，可看到当前活动，例如[安全警报](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-configure-security-alerts/)和[访问评审](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-start-security-review/)。 还可使用此仪表板[添加](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-give-access-to-pim/)或[删除](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-give-access-to-pim/#remove-another-users-access-rights-for-managing-pim)一个或多个对 Azure AD Privileged Identity Management 的用户访问权限。
