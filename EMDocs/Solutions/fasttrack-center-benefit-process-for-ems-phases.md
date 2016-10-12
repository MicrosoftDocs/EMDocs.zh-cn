---
title: "载入和迁移阶段"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 10/02/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4edfa04ab1ecf371e207497d74aa4c1e2366d7a9
ms.openlocfilehash: 9a41384fc4c7706c715b7c79d2dfd8e42f1d0a5d


---

# 载入和迁移阶段
当使用[符合 FastTrack 中心权益条件的服务和计划](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)以使 Azure Active Directory Premium 和/或 Microsoft Intune 可供使用时，该流程涉及几个阶段。 以下各部分描述了载入流程的每个阶段。

载入包含以下几个主要阶段：

![FastTrack 载入流程的四个阶段](./media/ft-onboarding-benefit.png)


## 启动阶段

购买适当数量的许可证后，请按照购买确认电子邮件中的指南将许可证与现有的租户或新租户相关联。 Microsoft 将验证你的 FastTrack 中心权益资格，并且将尝试与你联系来提供载入协助。 如果你已准备好在你的组织中部署这些服务，你还可以通过 [FastTrack 中心](http://fasttrack.microsoft.com/) 请求协助。

若要请求协助，请利用你的工作或学校帐户登录到 [FastTrack 中心](http://fasttrack.microsoft.com/) (http://fasttrack.microsoft.com)，单击公司（如有需要则添加它），单击“服务”选项卡，然后单击“请求 Microsoft Intune 或 Azure Active Directory Premium 协助”。 启动载入支持之后，我们将为联机会议设置一个日程安排。

在此阶段，我们将讨论载入流程，验证数据并设置启动会议。

![载入启动阶段](./media/ft-initiate-phase.png)

## 评估阶段

载入流程开始之后，Microsoft 将与您一同评估您的源环境和要求。 将运行相关工具以评估你的环境，并且 Microsoft 将指导你评估本地 Active Directory、Internet 浏览器、客户端设备的操作系统、DNS、网络、基础结构和标识系统，以确定是否需要针对载入进行任何更改。

Microsoft 还将与你联系，提供有关如何推动成功采用符合条件的服务的指导。

根据你的当前设置，我们将提供一个修正计划，将你的源环境调整至满足成功载入到 EMS 或其单独的云服务的最低要求。 在修正阶段，我们还会设置相应的检查点调用。

![载入评估阶段](./media/ft-assess-phase.png)

## 修正阶段
如果需要，你将针对源环境执行修正计划中的相关任务，以便满足载入和采用每项服务的要求。

![载入修正阶段](./media/ft-remediate-phase.png)

在开始启用阶段之前，我们将共同验证修正活动的结果以确保您可以继续后续操作。

## 启用阶段
完成所有修正活动后，项目会转而配置服务使用的核心基础结构并设置每个符合条件的 EMS 云服务。

**启用阶段 - 核心功能**

核心载入涉及服务设置以及租户和标识集成。 它还包括提供载入联机服务（如 Azure Active Directory Premium 和 Microsoft Intune）的基础的步骤。

![载入启用阶段 - 核心功能](./media/ft-enable-phase-core-01.png)

![载入启用阶段 - 核心功能](./media/ft-enable-phase-core-02.png)

### 启用阶段 – Azure Active Directory Premium

根据需要，可以使用 Azure Active Directory Connect 目录同步工具和 Active Directory 联合身份验证服务 (AD FS) 设置 Azure Active Directory Premium 环境。

对于包括将本地标识同步到云的 Azure Active Directory Premium 方案，我们将帮助你向订阅添加 IT 管理员和用户、配置管理先决条件、设置 Azure Active Directory Premium、使用 Azure Active Directory Connect 工具设置目录同步和 Active Directory 联合身份验证服务 (AD FS)、配置测试用户以及验证服务的核心用例。

Azure Active Directory Premium 设置包括启用以下功能：

-   自助服务密码重置 (SSPR)。

-   Azure 多重身份验证 (Azure MFA)。

-   一个服务型软件 (SaaS) 应用程序与来自 [Azure Active Directory 应用商店](https://azure.microsoft.com/marketplace/active-directory/)的单一登录 (SSO) 的集成。

-   自定义的登录屏幕（包括徽标、文本和图像）。

-   自助服务和动态组（组）。

-   Azure Active Directory 应用程序代理。

-   Azure Active Directory Connect Health。

-   标识保护。

-   特权标识管理。

-   发至管理员的使用情况和阿娜全报告。

-   管理性通知和警报。

![载入启用阶段 - AADP](./media/ft-enable-phase_aad-premium_adconnect_adfed.png)

### 启用阶段 – Microsoft Intune

对于 Microsoft Intune，根据你的移动设备和移动应用程序管理需求，我们将指导你准备好使用 Microsoft Intune 来管理设备。 具体步骤根据您的源环境而定，可能包括：

-   授权你的最终用户。 需要时，我们还将对有关如何为你的 Microsoft 云服务租户激活批量许可证提供协助。

-   通过利用本地 Active Directory 或云标识，配置将由 Microsoft Intune 使用的标识。

-   添加用户到你的 Microsoft Intune 订阅，定义 IT 管理员角色并创建用户组和设备组。

-   根据管理需要配置你的移动设备管理机构：

    -   当 Microsoft Intune 是你唯一的 MDM 解决方案或其与 Office 365 的移动设备管理结合时，将 Microsoft Intune 设置为你的 MDM 机构。

    -   如果拥有 System Center Configuration Manager 的现有实施，且想要使用 Microsoft Intune 扩展其管理功能，则将 Configuration Manager 设置为你的 MDM 机构。

        > [!NOTE]
        > 如果只希望对最终用户拥有的设备、共享设备或展台类型的设备使用移动应用程序管理，则不需要设置 MDM 机构。

-   如果移动设备管理在你的作用域中，我们将提供以下方面的指导：

    -   配置用于验证 MDM 管理策略的测试组。

    -   配置 MDM 管理策略和服务，如：

        -   通过 Web 链接或深层链接为每个受支持平台进行的应用程序部署。

        -   条件性访问策略。

        -   部署电子邮件、Wi-Fi 和 VPN 配置文件。

        -   设置 Microsoft Intune Exchange Connector（如果适用）。

    -   将每个[受支持平台](https://technet.microsoft.com/library/dn600287.aspx)的设备注册到你的 Microsoft Intune 或带 Microsoft Intune 服务的配置管理器。

-   如果移动应用管理 (MAM) 在你的作用域中，或者如果你希望为现有的 Microsoft 或第三方 MDM 解决方案补充 MAM 策略，我们将提供以下方面的指导：

    -   为每个支持平台配置 MAM 策略。

    -   为托管应用配置条件性访问策略。

    -   使用上述 MAM 策略定位适当的用户组。

    -   使用托管应用程序使用情况报告。

-   如果 PC 管理在你的作用域中，我们将提供以下方面的指导：

    -   在需要时安装 Intune 客户端软件。

    -   使用 Intune 中可用的软件和硬件报告。

Microsoft 还将与你联系，提供有关如何推动成功采用符合条件的服务的指导。

![载入启用阶段 - Intune](./media/ft-enable-phase_intune_mam.png)

![载入启用阶段 - Intune](./media/ft-enable-phase_intune_mdm-mam_cloudonly.png)

**了解更多信息？**

[企业移动性 + 安全性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)


<!--HONumber=Oct16_HO1-->


