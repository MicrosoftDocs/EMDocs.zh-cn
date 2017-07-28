---
title: "Microsoft 职责"
description: "客户使用 FastTrack Center Benefit 时 Microsoft 的职责"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 77e668d5f638ee2e4b9a9e81a1f9181252fde8b9
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2017
---
# <a name="microsoft-responsibilities"></a>Microsoft 职责

在载入期间 Microsof 具有下列职责。

## <a name="general"></a>常规

-   对于所需的配置活动，为你提供远程支持协助（请参阅具体阶段中所列内容）。

-   提供可用的文档和软件工具、管理控制台和脚本，帮助您减少或消除配置任务。

## <a name="initiate-phase"></a>启动阶段

-   对于新租户，在购买符合条件的许可证的 30 天内与您联系。

-   和你一起开始载入。

-   定义您要载入的符合条件的服务。

## <a name="assess-phase"></a>评估阶段

-   提供管理概述。

-   提供以下方面的指导：

    -   DNS、网络和基础结构需求。

    -   客户端需求（Internet 浏览器、客户端操作系统和服务需求）。

    -   用户标识和设置。

    -   启用已购买且定义为载入部分的符合条件的服务。

-   为修正活动设置时间表。

-   提供修正清单。

## <a name="remediate-phase"></a>修正阶段

-   根据商定的日程安排与你开始电话会议，以审核修正活动的进度。

-   运行工具以识别并解决问题，并对结果进行说明，从而提供协助。

## <a name="enable-phase"></a>启用阶段
提供以下方面的指导：

-   激活您的 Microsoft Online Service 租户。

-   配置 TCP/IP 协议和防火墙端口。

-   为符合条件的服务配置 DNS。

-   验证 Microsoft Online Services 的连接。

-   对于单林环境：

    -   根据需要，在 Active Directory 域服务 (AD DS) 和符合条件的 Microsoft Online Service 之间安装目录同步服务器。

    -   使用 Azure Active Directory Connect 工具配置密码同步（密码哈希）到 Microsoft Intune (Azure Active Directory)。

        > [!NOTE]
        > 自定义规则扩展的开发和实现不在讨论范围内。

-   对于目标为联合标识的单林：根据需要安装并配置 Active Directory 联合身份验证服务 (AD FS)，在单个站点、容错配置中使用 Intune 对本地域进行身份验证。

    > [!NOTE]
    > 对于多林配置，AD FS 部署不在讨论范围内。

-   如果已部署单一登录 (SSO)，请测试其功能。

### <a name="enable-phase---microsoft-azure-active-directory-premium"></a>启用阶段 - Microsoft Azure Active Directory Premium

提供以下方面的指导：

-   激活 Azure AD Premium 帐户。

-   配置防火墙端口。

-   为符合条件的服务配置 DNS。

-   验证到 Azure AD Premium 服务的连接。

-   对于单林环境：

    -   根据需要，在你的 Active Directory 域服务 (AD DS) 和 Azure AD Connect 之间安装目录同步。

    -   使用 Azure AD Connect 工具配置密码同步。

-   对于多林环境：

    -   安装 Azure AD Connect 同步，为多林方案进行设置。

        > [!NOTE]
        > 密码哈希同步和密码写回支持多林。 但是，不支持其他写回方案。

    -   配置本地 Active Directory 林和 Microsoft Azure Active Directory Premium 目录 (Azure Active Directory) 之间的同步。

        > [!NOTE]
        > 自定义规则扩展的开发和实现不在讨论范围内。

-   对于目标为联合标识的单林：

    -   根据需要安装并配置 AD FS，以便在单个站点、容错配置中使用 Azure AD Premium 进行本地域身份验证。

    > [!NOTE]
    > 对于多林配置，AD FS 部署不在讨论范围内。

-   测试 SSO 功能（如果已部署）。

### <a name="enable-phase---azure-ad-premium--with-azure-ad-connect-and-ad-fs"></a>启用阶段 - Azure AD Premium-- 使用 Azure AD Connect 和 AD FS

提供设置以下内容的相关指导：

-   用户设置（包括许可）。

-   Azure AD Connect 目录同步（使用密码写回和密码哈希同步）。

  - 自助服务密码重置 (SSPR)。

  - Azure 多重身份验证。

  - 一个服务型软件 (SaaS) 应用程序与来自 [Azure Active Directory 应用商店](https://azure.microsoft.com/marketplace/active-directory/)的 SSO 的集成。

  - 自定义的登录屏幕（包括徽标、文本和图像）。

  - 自助服务和动态组（组）。

  - Azure Active Directory 应用程序代理。

  - Azure AD Connect 运行状况。

  - 标识保护。

  - 特权标识管理。

  - 发至管理员的使用情况和安全报告。

  - 管理性通知和警报。

### <a name="enable-phase---intune"></a>启用阶段 - Intune
提供以下方面的指导：

-   授权你的最终用户。

-   通过利用本地 Active Directory 或利用云标识，配置将由 Intune 使用的标识。

-   向 Intune 订阅添加用户时，定义 IT 管理员角色并创建用户组和设备组。

-   根据管理需要配置移动设备管理 (MDM) 机构，包括：

    -   当 Intune 是你唯一的 MDM 解决方案或其与 Office 365 的移动设备管理结合时，请将 Intune 设置为你的 MDM 机构。

    -   如果已具有 Configuration Manager 的现有实施，并想使用 Intune 扩展其管理功能，请将 System Center Configuration Manager 设置为 MDM 机构。

        > [!NOTE]
        > 如果只希望对最终用户拥有的设备、共享设备或展台类型的设备使用 MDM，则不需要设置 MDM 机构。

    -   配置用于验证 MDM 管理策略的测试组。

    -   配置 MDM 管理策略和服务，如：

        -   通过 Web 链接或深层链接为每个受支持平台进行的应用程序部署。

        -   条件性访问策略。

        -   电子邮件、无线网络和 VPN 配置文件的部署（如果组织中有现有的证书颁发机构、Wi-Fi 或 VPN 基础结构）。

        -   设置 Microsoft Intune Exchange Connector（如果适用）。

    -   将每个受支持平台的设备注册到 Intune 或具有 Microsoft Intune 服务的 Configuration Manager。

    -   使用硬件和软件清单报告。

    -   为每个支持平台配置 MAM 策略。

    -   为托管应用配置条件性访问策略。

    -   使用上述 MAM 策略定位适当的用户组。

    -   使用托管应用程序使用情况报告。

    -   安装 Intune 客户端软件（如果需要）。

    -   使用 Intune 中可用的软件和硬件报告。

**想要了解更多信息？**

[企业移动性 + 安全性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
