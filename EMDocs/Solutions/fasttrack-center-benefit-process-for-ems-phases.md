---
title: 载入和迁移阶段
description: FastTrack Center Benefit 的阶段
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 04/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: e63644b2e8db81f6293dbad4ca4de14dbe40ecac
ms.sourcegitcommit: 0863dce817862f00068614f2c62698784eb76d84
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
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

1. 转到 [FastTrack 中心](http://fasttrack.microsoft.com/)，使用你的工作或学校帐户登录。

2. 在客户仪表板中，选择页面右下侧的“转到 FastTrack”。

3. 在 FastTrack 仪表板上，在页面右下侧展开“需要帮助?”，然后按照提示完成请求。

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

-   自助服务密码重置 (SSPR)。

-   Azure 多重身份验证 (Azure MFA)。

-   多达三 (3) 个及以上服务型软件 (SaaS) 应用程序与来自 [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/) 的单一登录 (SSO) 集成。

-   自定义的登录屏幕（包括徽标、文本和图像）。

-   自助服务和动态组（组）。

-   Azure Active Directory 应用程序代理。

-   Azure Active Directory Connect Health。

-   标识保护。

-   特权标识管理。

-   Azure Active Directory 条件访问。

![载入启用阶段 - Azure AD Premium](./media/ft-enable-phase_aad-premium_adconnect_adfed.png)

### <a name="enable-phase---intune"></a>启用阶段 - Intune

对于 Intune，我们会提供相关指导，确保你已可使用 Microsoft Intune 来管理设备。 具体步骤取决于你的源环境，并根据你的移动设备和移动应用管理需求而定。 步骤可能包括：

-   授权你的最终用户。 如果需要，我们还会提供有关如何为 Microsoft 云服务租户激活批量许可证的协助。

-   通过利用本地 Active Directory 或云标识，配置将由 Intune 使用的标识。

-   向 Intune 订阅添加用户时，定义 IT 管理员角色并创建用户组和设备组。

-   根据管理需要配置移动设备管理 (MDM) 机构，包括：

    -   当 Intune 是你唯一的 MDM 解决方案或其与 Office 365 的移动设备管理结合时，请将 Intune 设置为你的 MDM 机构。

    -   如果已具有 Configuration Manager 的现有实施，并想使用 Intune 扩展其管理功能，请将 System Center Configuration Manager 设置为 MDM 机构。

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

    -   将每个[受支持平台](https://technet.microsoft.com/library/dn600287.aspx)的设备注册到你的 Intune 或具有 Intune 服务的 Configuration Manager。

-   提供有关以下内容的 Intune 应用保护（应用管理）指导：

    -   为每个支持平台配置应用保护策略。

    -   为托管应用配置条件性访问策略。

    -   使用上述 MAM 策略定位适当的用户组。

    -   使用托管应用程序使用情况报告。

-   提供相关电脑管理指导：

    -   安装 Intune 客户端软件（如果需要）。

    -   使用 Intune 中可用的软件和硬件报告。

    > [!IMPORTANT]
    > FastTrack 不支持使用 Intune 进行 Windows 10 经典电脑管理。 FastTrack 仅支持通过 Intune 移动设备管理 (MDM) 进行 Windows 10 设备管理。

Microsoft 还会与你联系，提供有关如何推动成功采用符合条件的服务的指导。

![载入启用阶段 - Intune](./media/ft-enable-phase_intune_mam.png)

![载入启用阶段 - Intune](./media/ft-enable-phase_intune_mdm-mam_cloudonly.png)

![载入启用阶段 - Intune](./media/ft-enable-phase-intune-mdm-mam-sccm.png)

> [!NOTE]
> **想要了解更多？**请参阅[企业移动性 + 安全性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)。

## <a name="next-steps"></a>后续步骤

[EMS 的 FastTrack 权益 - Microsoft 职责](fasttrack-center-benefit-process-for-ems-fasttrack-responsibilities.md)
