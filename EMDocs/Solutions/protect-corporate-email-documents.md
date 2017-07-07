---
title: "保护公司电子邮件和文档"
description: "只允许合规设备访问你公司的电子邮件和保护电子邮件和附件中的内容。"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 78d8368e-1bfe-4ac4-991d-467321a76ed7
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: f209973d304e1a54393dc994e7c3785e4f751a88
ms.contentlocale: zh-cn
ms.lasthandoff: 07/07/2017


---

# <a name="protecting-corporate-email-and-documents"></a>保护企业电子邮件和文档
保护企业电子邮件涉及两个主要目标：

-   只允许合规设备访问企业的电子邮件

-   保护电子邮件和附件中的内容

## <a name="allow-only-compliant-devices-to-access-your-companys-email"></a>只允许合规设备访问企业的电子邮件
保护企业数据的一个重要步骤是限制对未使用强密码、未破解或未加密的设备的访问。 Microsoft Intune 可让你设定条件，用户必须满足这些条件，才能访问公司资源。 这称为条件性访问。

条件性访问由可在 Intune 中设置的两种类型的策略决定：

**合规性策略** 确定设备的合规性。 它们评估以下设置和条件：

-   **PIN 和密码**：IT 部门可以创建以下规则：必须提供密码才可解锁设备，设定密码的复杂性、密码过期和其他密码设置。

-   **加密**：IT 部门可以限制对加密设备的访问。

-   **设备未越狱或取得 root 权限**：Intune 可以检测注册的设备是否已越狱，而 IT 部门可以设置策略来阻止此类设备上的访问。

**条件性访问策略** 专为 Exchange Online 或 SharePoint Online 等特定服务配置。 对于每个服务，你可以定义这些策略应该应用到哪些用户组。 例如，你可以确保财务部门的每个人只能从注册的合规设备访问公司电子邮件。

## <a name="high-level-end-user-experience"></a>高级最终用户体验
实现解决方案之后，最终用户将只能在托管且合规的设备上访问公司电子邮件。 一旦他们能够在设备上访问电子邮件，公司数据便受到保护并且包含在应用生态系统内，只能由预期用户使用。 如果设备不合规，则可以随时撤消访问权限。

具体而言，在 Intune 中设置的条件访问策略可确保仅当设备符合所设置的合规性策略时，它们才能访问电子邮件。 可以使用移动应用程序管理策略来限制诸如复制和粘贴或保存到个人云存储服务这类操作。 Azure 信息保护可用于确保只有预期收件人才能读取敏感电子邮件数据和转发的附件。 有关最终用户体验更详细的描述，请参阅[条件访问的最终用户体验](end-user-experience-conditional-access.md)。


观看 [这段](https://www.youtube.com/watch?feature=player_embedded&v=lYx3YIezccg) 四分钟的视频，了解条件性访问会如何影响最终用户。

## <a name="why-architecture-matters"></a>为什么体系结构很重要
EMS 和 Office 365 的不同组件构建用于在云中运行。 这带来了云的所有好处：可扩展性、灵活性和易管理性。

由于不同的业务有不同的要求，EMS 专门针对与 Active Directory、Exchange Server 或 System Center Configuration Manager 等现有本地体系结构集成而设计。 这样，你就可以将已在网络建立的凭据用于本地和云资源。

以下各节主要介绍设计在云中运行的体系结构，并简要谈及本地选项。

### <a name="email-access-flow"></a>电子邮件访问流程
根据用于访问 Exchange Online 的电子邮件应用程序的类型，建立安全访问电子邮件的路径可能略有不同。 但是，关键组件 Azure Active Directory (Azure AD)、Office 365/Exchange Online 和 Microsoft Intune 是相同的。 IT 体验和最终用户体验也很相似。 EMS 目前支持本机电子邮件应用以及适用于 iOS 和 Android 的 Microsoft Outlook 应用。

### <a name="access-control-flow-for-native-email-applications"></a>本机电子邮件应用程序的访问控制流程
尝试访问 Exchange Online 中的电子邮件的 Exchange ActiveSync (EAS) 需针对以下属性接受评估：

-   这是 Intune 管理的设备吗？

-   设备注册了 Azure Active Directory 吗？

-   设备合规吗？

-   客户端 EAS ID 映射到了已注册的设备吗？

为达到合规性状态，运行 EAS 客户端的设备需要：

-   注册 Intune

-   注册 [Azure Active Directory](https://msdn.microsoft.com/6a14cb1f-a058-4453-8ede-d9f4a66a7073.aspx)，并且

-   符合 IT 管理员设置的设备策略。

在大多数平台上，注册期间 Azure Active Directory 设备会自动注册。 设备状态由 Intune 写入 Azure Active Directory，然后由 Exchange Online 在下次 EAS 客户端尝试获取电子邮件时进行读取。 如果设备未注册，则用户收件箱中会收到一封邮件，其中会提供注册（也称登记）步骤的说明。 如果设备不符合要求，则用户会收到一封不同的电子邮件，将他们重定向到 Intune Web 门户，用户可在此了解有关合规性问题以及修正方式的详细信息。

**Azure AD**对用户和设备进行身份验证，Microsoft Intune 管理合规性和条件性访问策略， **Exchange Online** 基于设备状态管理对电子邮件的访问。

![iOS 和 Android 设备上的本机电子邮件应用程序的访问控制流程图](./media/ProtectEmail/Access-Control-Flow-For-Native-Email-Apps.png)

### <a name="access-control-flow-for-outlook-applications"></a>Outlook 应用程序的访问控制流程
与 EAS 客户端类似，尝试访问 Exchange Online 中的电子邮件的 Outlook 电子邮件应用需针对以下属性接受评估：

-   这是 Intune 管理的设备吗？

-   设备注册了 Azure Active Directory 吗？

-   设备合规吗？

设备合规性的建立与 EAS 客户端访问控制流程中所述大致相同。 但是对于 Outlook 应用而言，组件之间的流程略有不同。 Outlook 应用尝试获取电子邮件时会被重定向到 Azure AD。 如果设备成功评定为已注册且合规，则 Azure AD 会发布安全令牌。 随后，安全令牌将用于从 Exchange Online 获取企业电子邮件。 电子邮件同步实际是通过 Outlook 云服务进行的，云服务代表用户获取 EAS 服务访问令牌以完成身份验证并传送电子邮件。

![Outlook 应用程序的访问控制流程图](./media/ProtectEmail/Access-Control-Flow-For-Outlook-App.png)

## <a name="the-it-admin-experience"></a>IT 管理员体验：
Azure AD 或 Exchange 无需复杂的体系结构设置即可实现此目标。 你的 IT 管理员：

-   配置和部署用于评估设备合规性状态的合规性策略。

-   配置 Exchange Online 的条件性访问策略，并指定将受/不受这些策略影响的 Azure AD 安全组。

-   选择允许或阻止无法注册 Intune 的设备。 稍后将列出移动设备支持的操作系统的完整列表。

还有一个可能需要的可选设置阶段。 用于管理和监视设备访问和状态的报告需要设置 Microsoft Intune 服务间连接器。

## <a name="the-end-user-experience"></a>最终用户体验：
当用户首次尝试访问设备上的电子邮件或随后同步时，将检查设备注册和合规性状态。 注册或修复合规性问题的过程是一种指导式体验。 将向最终用户显示注册设备并让其合规的必要步骤，用户无需联系 IT 支持人员：

-   **如果设备未注册**，登录页面将显示访问被拒绝并提示你进行注册。 注册时，设备会自动注册 Azure Active Directory。 Intune 检查设备是否合规，并提供修正措施以解决任何非合规性问题。 设备合规后，Intune 将使用 Azure Active Directory 设定设备的合规性状态。

-   **如果设备已注册但不合规**，则将向设备发送包含问题修正措施的链接。 最终用户纠正此问题后（例如设置密码、加密），管理合规性策略的 Intune 将在 Azure AD 中更新设备的合规性状态。

设备被评定为已注册且合规后，几分钟内即会进行电子邮件同步。

## <a name="where-to-go-from-here"></a>后续步骤
你已了解了保护企业电子邮件和文档的相关内容，现在可以阅读有关如何[保护电子邮件附件](protect-email-attachments.md)的详细信息。 或者，如果你已准备好了，则可详细了解如何[实现保护你的企业电子邮件的解决方案](implement-solution.md)。

