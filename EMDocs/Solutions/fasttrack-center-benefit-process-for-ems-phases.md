---
title: 载入和迁移阶段
description: FastTrack Center Benefit 的阶段
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 12/4/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: c9e909cbd37c217e99c7687354a9d3a132cb3867
ms.sourcegitcommit: b64e0087de6771f1f6ede4718025ea3a7e78f8c6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "53320021"
---
# <a name="onboarding-phases"></a>载入阶段

使用[符合 FastTrack 中心权益条件的服务和计划](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)以使 Microsoft Azure Active Directory Premium 和 Microsoft Intune 可供使用时，流程中涉及几个阶段。 以下各部分描述了载入流程的每个阶段。

载入包含四个主要阶段：

![FastTrack 载入流程的四个阶段](./media/ft-onboarding-benefit.png)


## <a name="initiate-phase"></a>启动阶段

购买适当数量的许可证后，请按照购买确认电子邮件中的指南将许可证与现有的租户或新租户相关联。 Microsoft 会验证你的 FastTrack 中心权益资格，并尝试与你联系来提供载入协助。

> [!NOTE]
> 如果已准备好在组织中部署这些服务，还可以从 [FastTrack 中心](http://fasttrack.microsoft.com/)请求协助。

### <a name="to-request-assistance"></a>请求协助

1. 登录到 [FastTrack 站点](https://go.microsoft.com/fwlink/?linkid=780698)。
2. 选择“FastTrack”。
3. 选择“服务”。
4. 完成“使用 Microsoft 365 表单请求帮助”。

启动载入支持之后，我们将为联机会议设置一个日程安排。

> [!NOTE]
> 如果在 Office 365 租户中列出了 Microsoft 合作伙伴，则不会看到此选项。 请咨询你的 Microsoft 合作伙伴以获取帮助。

Microsoft 合作伙伴也可以代表客户通过 [FastTrack 站点](https://go.microsoft.com/fwlink/?linkid=780698)获取帮助。 为此，请执行以下操作：

1. 登录到 [FastTrack 站点](https://go.microsoft.com/fwlink/?linkid=780698)。
2. 选择“FastTrack”。
3. 选择“我的客户”。
4. 搜索你的客户或从你的客户列表中选择。
5. 选择“服务”。
6. 完成“使用 Microsoft 365 表单请求帮助”。

载入支持启动后，FastTrack 会设置你的联机会议日程，讨论载入流程、验证数据，并设置启动会议。

![载入启动阶段](./media/ft-initiate-phase.png)

## <a name="assess-phase"></a>评估阶段

载入流程开始之后，FastTrack 中心将与你一同评估源环境和要求。 将运行相关工具来评估你的环境，并且 FastTrack 专家会指导你评估本地 Active Directory、Internet 浏览器、客户端设备的操作系统、域名系统 (DNS)、网络、基础结构和标识系统，以确定是否需要针对载入进行任何更改。

FastTrack 中心还会与你联系，提供有关如何推动成功采用符合条件的服务的指导。

根据当前设置，我们会提供一个修正计划，将你的源环境调整至满足成功载入到 EMS 或其单独的云服务的最低要求。 在修正阶段，我们还会设置相应的检查点调用。

![载入评估阶段](./media/ft-assess-phase.png)

## <a name="remediate-phase"></a>修正阶段
如果需要，你可以在源环境中执行修正计划中的相关任务，以便满足载入和采用每项服务的要求。

![载入修正阶段](./media/ft-remediate-phase.png)

开始启用阶段之前，我们会共同验证修正活动的结果来确保你可以执行后续操作。

## <a name="enable-phase"></a>启用阶段
完成所有修正活动后，项目会转而配置服务使用的核心基础结构并设置每个符合条件的 EMS 云服务。

**启用阶段 - 核心功能**

核心载入涉及服务设置以及租户和标识集成。 它还包括为载入联机服务（如 Azure AD Premium 和 Intune）提供基础的步骤。

![载入启用阶段 - 核心功能](./media/ft-enable-phase-core-01.png)

![载入启用阶段 - 核心功能](./media/ft-enable-phase-core-02.png)
> [!NOTE]
> Web 代表 Web 应用程序代理。 SSL 代表安全套接字层。 SDS 代表学校数据同步。有关 SDS 的详细信息，请参阅[欢迎使用 Microsoft School Data Sync](https://go.microsoft.com/fwlink/?linkid=871480)。

> [!NOTE]
> 托管身份验证方法包括但不限于密码哈希同步。 标识集成是一次性活动，不包括对现有身份验证方法（如托管或联合）的迁移或解除授权。

### <a name="enable-phase---azure-ad-premium"></a>启用阶段 - Azure AD Premium

根据需要，可以使用 Azure Active Directory Connect 目录同步工具和 Active Directory 联合身份验证服务 (AD FS) 设置 Azure AD Premium 环境。

对于包括将本地标识同步到云的 Azure AD Premium 方案，我们会帮助你向订阅添加 IT 管理员和用户，配置管理先决条件、设置 Azure AD Premium、使用 Azure AD Connect 工具通过托管身份验证和 AD FS 设置目录同步和 AD FS、配置测试用户以及验证服务的核心用例。

Azure AD Premium 设置包括启用以下功能：

-   Azure Active Directory 自助密码重置 (SSPR)。

-   Azure 多重身份验证 (Azure MFA)。

-   多达三 (3) 个及以上服务型软件 (SaaS) 应用程序与来自 [Azure Active Directory 市场](https://azure.microsoft.com/marketplace/active-directory/)的单一登录 (SSO) 集成。

-   [应用集成教程列表](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/tutorial-list)中列出的针对预集成的 SaaS 应用程序的自动用户预配仅限于出站预配。

-   自定义的登录屏幕（包括徽标、文本和图像）。

-   自助服务和动态组（组）。

-   Azure Active Directory 应用程序代理。

-   Azure Active Directory Connect Health。

-   Azure Active Directory 条件访问。

-   Azure Active Directory 使用条款。

-   Azure Active Directory Identity Protection。

-   Azure Active Directory Privileged Identity Management。

-   Azure Active Directory 访问评审。

![载入启用阶段 - Azure AD Premium](./media/ft-enable-phase_aad-premium_adconnect_adfed.png)

### <a name="enable-phase---intune"></a>启用阶段 - Intune

对于 Intune，我们会提供相关指导，确保你已可使用 Microsoft Intune 来管理设备。 具体步骤取决于你的源环境，并根据你的移动设备和移动应用管理需求而定。 步骤可能包括：

-   授权你的最终用户。 如果需要，我们还会提供有关如何为 Microsoft 云服务租户激活批量许可证的协助。

-   通过利用本地 Active Directory 或云标识，配置将由 Intune 使用的标识。

-   向 Intune 订阅添加用户时，定义 IT 管理员角色并创建用户组和设备组。

-   根据管理需要配置移动设备管理 (MDM) 机构，包括：

    -   当 Intune 是你唯一的 MDM 解决方案或其与 Office 365 的移动设备管理结合时，请将 Intune 设置为你的 MDM 机构。

-   提供相关 MDM 指导：

    -   配置用于验证 MDM 管理策略的测试组。

    -   配置 MDM 管理策略和服务，如：

        -   通过 Web 链接或深层链接为每个受支持平台进行的应用程序部署。

        -   条件性访问策略。

        -   电子邮件、无线网络和虚拟专用网络 (VPN) 配置文件的部署（如果组织中有现有的证书颁发机构、Wi-Fi 或 VPN 基础结构）。

        -   设置 Microsoft Intune Exchange Connector（如果适用）。

        -   连接到 Intune 数据仓库

        -   将 Intune 与以下产品集成：
            -   Team Viewer，获取远程协助（Team Viewer 订阅是必需的）。

            -   移动威胁防御 (MTD) 合作伙伴解决方案（移动威胁防御订阅是必需的）。

            -   电信费用管理解决方案（电信费用管理解决方案订阅是必需的）。

            -   Windows Defender 高级威胁防护（Windows E5 或 Microsoft 365 E5 许可证是必需的）。

    -   将[每个支持的平台](https://technet.microsoft.com/library/dn600287.aspx)的设备注册到 Intune。

-   提供有关以下内容的应用保护指导：

    -   为每个支持平台配置应用保护策略。

    -   为托管应用配置条件性访问策略。

    -   使用上述 MAM 策略定位适当的用户组。

    -   使用托管应用程序使用情况报告。

-   提供有关以下内容的电脑管理指导：

    -   安装 Intune 客户端软件（如果需要）。

    -   使用 Intune 中可用的软件和硬件报告。

    > [!IMPORTANT]
    > FastTrack 不支持使用 Intune 进行 Windows 10 经典电脑管理。 FastTrack 仅支持通过 Intune 移动设备管理 (MDM) 进行 Windows 10 设备管理。

#### <a name="windows-autopilot"></a>Windows Autopilot

FastTrack 可以帮助你简化在 Windows Autopilot 和 Intune 中的设备预配，方法是向你的最终用户提供新设备，无需生成、维护和向设备应用自定义操作系统映像。

FastTrack 支持以下 Autopilot 方案：

- **Azure AD 自助服务：** 设备联接 Azure AD 并注册到 Intune。 在使用 Windows 10 1703 和最新版本时支持使用此方案。

- **混合 AAD 自助服务：** 设备联接本地 Azure AD 和 Azure AD 并注册到 Intune。 在使用 Windows 10 1809 和最新版本时支持使用此方案。

- **自预配：** 设备自动联接 Azure AD。 在使用 Windows 1809 和最新版本时支持使用此方案。

    > [!IMPORTANT]
    > FastTrack 不支持从 Configuration Manager 启动的 Autopilot 方案。

设置 Windows Autopilot 的步骤取决于你的源环境，可能包括：

- 为 Windows Autopilot 配置和设置 Microsoft Intune。

- 配置 Azure AD 动态组

- 将公司品牌添加到 Azure AD。

- 创建设备并将其分配到 Windows Autopilot 配置文件（例如，限制本地管理员帐户创建的 Windows Autopilot 配置文件）。

- 自定义全新体验 (OOBE) 以符合组织的要求。

- 在 Azure AD 和 Intune 中配置 MDM 自动注册。

#### <a name="deploy-outlook-for-ios-and-android-securely"></a>安全部署 Outlook for iOS 和 Outlook for Android

FastTrack 可通过在组织中安全地部署 Outlook for iOS 和 Outlook for Android 帮助确保用户已安装所有所需的应用。

通过 Intune 安全地部署 Outlook Mobile for iOS 和 Outlook Mobile for Android 的步骤取决于源环境，这一环境可以包括：

- 通过 Apple 应用商店或 Google Play 商店下载 Outlook for iOS 和 Outlook for Android、Microsoft Authenticator 和 Intune 公司门户应用。
- 还提供设置以下应用的相关指导：
    - 通过 Intune 部署的 Outlook for iOS 和 Outlook for Android、Microsoft Authenticator 和 Intune 公司门户应用。
    - 应用保护策略
    - 条件性访问策略
    - 应用配置策略

    > [!IMPORTANT]
    > FastTrack 团队不支持使用 Exchange 移动设备邮箱策略保护 Outlook for iOS 和 Outlook for Android。

#### <a name="co-management"></a>共同管理

FastTrack 可指导你做好准备来使用 Configuration Manager 和 Intune 同时管理 Windows 10 设备。 具体步骤取决于你的源环境，可能包括：

- 介绍共同管理的好处。

- 授权许可你的最终用户。 根据需要，FastTrack 还会提供有关如何为 Microsoft 云服务租户激活批量许可证的协助。

- 通过利用本地 Active Directory 和/或云标识，配置将由 Intune 使用的标识。

- 向 Intune 订阅添加用户时，定义 IT 管理员角色并创建用户组和设备组。

- 提供有关如何从与 System Center Configuration Manager（混合）集成的 Intune 移动到 Intune Standalone 的指南。

- 提供有关如何设置 Azure Active Directory 进行 MDM 自动注册的指南。

- 提供有关如何设置混合 Azure Active Directory 加入的指南。

- 提供有关如何设置云管理网关的指南。

- 在 Configuration Manager 控制台中启用共同管理。

- 配置想要切换到 Intune 的受支持的工作负载。

- 将 Configuration Manager 客户端安装到在 Intune 中注册的设备。

- 提供有关如何监视环境中共同管理活动的指导。

此外，FastTrack 还提供有关如何推动成功采用符合条件的服务的指导。

![载入启用阶段 - Intune](./media/ft-enable-phase_intune_mam.png)

![载入启用阶段 - Intune](./media/ft-enable-phase_intune_mdm-mam_cloudonly.png)

![载入启用阶段 - 共同管理](./media/ft-9-enable-phase-comanagement.png)

> [!NOTE]
> **想要了解更多?** 请参阅[企业移动性 + 安全性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)。

## <a name="next-steps"></a>后续步骤

[EMS 的 FastTrack 权益 - Microsoft 职责](fasttrack-center-benefit-process-for-ems-fasttrack-responsibilities.md)
