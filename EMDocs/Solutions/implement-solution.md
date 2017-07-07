---
title: "实现用于保护公司电子邮件和附件的解决方案"
description: "准备并实现用于保护公司电子邮件内容和附件的解决方案。"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: edc744d8-97d9-42e0-8906-6f0dedd8d629
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: 4a7537775ce2c6c19850720f789ea5882d062aec
ms.contentlocale: zh-cn
ms.lasthandoff: 07/07/2017


---

# <a name="implementing-your-solution-for-protecting-email-and-attachments"></a>实现用于保护电子邮件和附件的解决方案
本文将帮助你做好准备，然后实现用于保护公司电子邮件内容和附件的解决方案。

## <a name="what-you-should-consider-when-planning-your-implementation"></a>规划实现时应该考虑以下因素：

-   **设备平台支持**：你还必须考虑是否允许在 Intune 不支持的平台上访问电子邮件。 Intune 移动设备管理支持下列操作系统：

    -   Apple iOS 7.1 及更高版本 （以前注册的 iOS 6.0 和 7.0 设备保持已注册状态，但新设备无法注册）

    -   Google Android 2.3.4 及更高版本（包括 Samsung KNOX）

    -   Windows Phone 8.0 及更高版本

    -   Windows RT 及更高版本

    -   Windows 8.1 计算机及更高版本

-   **电子邮件应用的类型**：EMS 解决方案当前支持使用 EAS 协议的客户端和 Outlook 应用（之前 iOS 和 Android 上的 Accompli）。

-   **策略**：EMS 解决方案及其组件具有多个管理安全和访问权限的策略。 确定你的 IT 管理员需要配置何种策略。 保障电子邮件和电子邮件数据的访问安全时，用于研究和计划的三个主要策略是：

    -   **设备合规性策略**：确定合规对你公司的意义。 Intune 包含你可以设定的多条规则，但所有这些规则可能适用也可能不适用于你的公司。 你可以随时更改策略，但最好的做法是为你的公司确定一组基本的策略。 合规性策略主要针对 Intune 用户组和设备组。

    -   **条件访问策略**：条件访问策略主要针对 Azure AD 安全组。 确定策略针对哪些用户以及是否有需要免除的用户。 基于云的解决方案和混合实现均支持条件性访问。

    -   **移动应用程序管理**：确定应管理的应用和需要应用于这些应用的 MAM 策略。

-   **设备管理注意事项**：在实现解决方案之前，选择最适合组织需求的设备管理选项。 共有两个选项：

    -   结合使用 System Center Configuration Manager 和 Microsoft Intune，通过单一控制台管理所有设备。 这称为 *混合实现*。 这种方法的优点：

        -   单一管理控制台含有丰富的权限管理控件，可同时管理本地 PC 和移动设备

        -   丰富的目标定位和部署功能

        -   高扩展性，适合极大型企业

    -   使用 System Center Configuration Manager 单独从本地设备通过 Microsoft Intune 管理移动设备。 这称为 *Intune 独立实现*。 这种方法的优点：

        -   基于 Web 的简易控制台，专门定制用于管理移动设备

        -   快速访问最新的功能

    尽管迁移始终可行，我们仍强烈建议在实现之前做此决定，因为这会影响你在转出过程中做出的很多决策。

-   **你的 Exchange 环境**：

    -   部署 Exchange 连接器以及其在实现网络负载均衡器时的连接方式。

    -   Exchange Online – 是多租户还是专用租户？ 如果是专用租户，则查明租户所在的体系结构。 这将确定是否可以使用基于 Azure AD 的条件性访问，或者是否需要本地连接器。

-   **Azure AD 同步和 Active Directory 联合身份验证服务 (ADFS) 或其他第三方联合身份验证服务**：

    -   条件性访问设计用于已将标识服务联合至 ADFS 的客户。 通常客户端访问规则仍将应用，但建议进行全面测试。 对目录同步和 ADFS 的要求与对 Office 365 的要求相同。

    -   Ping 等第三方联合服务也应发挥作用。 建议在实现之前进行测试。

## <a name="on-premises-implementation"></a>本地实现
如果已具备现有的 System Center Configuration Manager、Active Directory 和/或 Exchange Server 实现，则可以通过与 Intune、Azure AD 和 Office 365 集成来扩展现有的体系结构。 你可以使用此混合实现在所有本地和云设备上提供一致的管理体验。 Intune 和 Configuration Manager 提供一组类似的功能，允许根据设备状态限制对电子邮件的访问。

对于 Exchange Online Dedicated 实现，是否可以利用前述的基于云的解决方案，或使用混合实现，这都取决于你当前的实现。 请咨询帐户团队以确定将采用哪种实现。

## <a name="operations-and-incidence-response"></a>操作和事件响应
实现解决方案后，你需要管理环境并确定潜在的安全风险。 Intune 和 Azure AD 都具有监视和报告功能，这些功能可帮助监视和快速响应安全事件。

下面是部分报告功能：

-   Intune 报告和警报可帮助你监视 Intune 所管理设备的状态和运行状况。

-   Azure AD 具有审核和活动日志记录功能。 你可以监视密码更改和用户管理等事务。 Azure Active Directory Premium 包含高级异常安全报告和警报。 这些警报基于详细的机器学习报告，报告中显示登录活动、不一致的访问模式和潜在的威胁领域。

## <a name="where-to-go-from-here"></a>后续步骤
有关如何部署用于保护公司电子邮件内容和附件的解决方案的分步说明，请参阅下面的一个主题，具体视你的特定环境而定：

- [结合使用条件访问和 Microsoft Intune](conditional-access-intune.md)
- [结合使用条件访问、Microsoft Intune 和 Configuration Manager](conditional-access-intune-configmgr.md)

