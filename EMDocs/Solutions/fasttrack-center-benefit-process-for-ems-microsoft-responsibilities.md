---
title: "Microsoft 职责"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 10/02/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 323bdb56b3d81eb6a63e266899427672abf79da4
ms.openlocfilehash: 777236784c06eeea2e62bcb77b2ceabc5d31b14a


---

# Microsoft 职责

在载入期间 Microsof 具有下列职责。

## 常规

-   对于所需的配置活动，为你提供远程支持协助（请参阅具体阶段中所列内容）。

-   提供可用的文档和软件工具、管理控制台和脚本，帮助您减少或消除配置任务。

## 启动阶段

-   对于新租户，在购买符合条件的许可证的 30 天内与您联系。

-   和你一起开始载入。

-   定义您要载入的符合条件的服务。

## 评估阶段

-   提供管理概述。

-   提供以下方面的指导：

    -   DNS、网络和基础结构需求。

    -   客户端需求（Internet 浏览器、客户端操作系统和服务需求）。

    -   用户标识和设置。

    -   启用已购买且定义为载入部分的符合条件的服务。

-   为修正活动设置时间表。

-   提供修正清单。

## 修正阶段

-   根据商定的日程安排与你开始电话会议，以审核修正活动的进度。

-   运行工具以识别并解决问题，并对结果进行说明，从而提供协助。

## 启用阶段
提供以下方面的指导：

-   激活您的 Microsoft Online Service 租户。

-   配置 TCP/IP 协议和防火墙端口。

-   为符合条件的服务配置 DNS。

-   验证 Microsoft Online Services 的连接。

-   对于单林环境：

    -   根据需要，在您的 Active Directory 域服务 (AD DS) 和符合条件的 Microsoft Online Service 之间安装目录同步服务器。

    -   使用 Azure Active Directory Connect 工具配置密码同步（密码哈希）到 Microsoft Intune (Azure Active Directory)。

        > [!NOTE]
        > 自定义规则扩展的开发和实现不在讨论范围内。

-   对于目标为联合标识的单林：根据需要安装并配置 Active Directory 联合身份验证服务 (AD FS)，在单个站点、容错配置中使用 Microsoft Intune 对本地域进行身份验证。

    > [!NOTE]
    > 对于多林配置，AD FS 部署不在讨论范围内。

-   如果已部署单一登录 (SSO)，则测试其功能。

### 启用阶段 – Azure Active Directory Premium

提供以下方面的指导：

-   激活 Microsoft Azure Active Directory Premium 租户。

-   配置防火墙端口。

-   为符合条件的服务配置 DNS。

-   验证与 Microsoft Azure Active Directory Premium 服务的连接。

-   对于单林环境：

    -   根据需要，在你的 Active Directory 域服务 (AD DS) 和 Azure Active Directory Connect 之间安装目录同步。

    -   使用 Azure Active Directory Connect 工具配置密码同步。

-   对于多林环境：

    -   安装 Azure Active Directory Connect 同步，为多林方案进行设置。 请注意，密码哈希同步和密码写回支持多林。  但是，不支持其他写回方案。

    -   配置本地 Active Directory 林和 Microsoft Azure Active Directory Premium 目录 (Azure Active Directory) 之间的同步。

        > [!NOTE]
        > 自定义规则扩展的开发和实现不在讨论范围内。

-   对于目标为联合标识的单林：根据需要安装并配置 Active Directory 联合身份验证服务 (AD FS)，以在单个站点、容错配置中使用 Microsoft Azure Active Directory Premium 对本地域进行身份验证。

    > [!NOTE]
    > 对于多林配置，AD FS 部署不在讨论范围内。

-   如果已部署单一登录 (SSO)，请测试其功能。

### 启用阶段 – Azure Active Directory Premium，使用 Azure Active Directory Connect 和 Active Directory 联合身份验证服务 (AD FS)

提供设置以下内容的相关指导：

-   用户设置（包括许可）。

-   Azure Active Directory Connect 目录同步（使用密码写回和密码哈希同步）。

  - 自助服务密码重置 (SSPR)。

  - Azure 多重身份验证(MFA)。

  - 一个服务型软件 (SaaS) 应用程序与来自 [Azure Active Directory 应用商店](https://azure.microsoft.com/marketplace/active-directory/)的单一登录 (SSO) 的集成。

  - 自定义的登录屏幕（包括徽标、文本和图像）。

  - 自助服务和动态组（组）。

  - Azure Active Directory 应用程序代理。

  - Azure Active Directory Connect Health。

  - 标识保护。

  - 特权标识管理。

  - 发至管理员的使用情况和阿娜全报告。

  - 管理性通知和警报。

### 启用阶段 – Microsoft Intune
提供以下方面的指导：

-   授权你的最终用户。 需要时，我们还将对有关如何为你的 Microsoft 云服务租户激活批量许可证提供协助。

-   通过利用本地 Active Directory 或利用云标识，配置将由 Microsoft Intune 使用的标识。

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

        -   电子邮件配置文件部署。

        -   设置 Microsoft Intune Exchange Connector（如果适用）。

    -   将每个受支持平台的设备注册到你的 Microsoft Intune 或带 Microsoft Intune 服务的 Configuration Manager。

    -   使用硬件和软件清单报告。

-   如果移动应用管理 (MAM) 在你的作用域中，或者如果你希望为现有的第三方 MDM 解决方案补充 MAM 策略，我们将提供以下方面的指导：

    -   为每个支持平台配置 MAM 策略。

    -   为托管应用配置条件性访问策略。

    -   使用上述 MAM 策略定位适当的用户组。

    -   使用托管应用程序使用情况报告。

-   如果 PC 管理在你的作用域中，我们将提供以下方面的指导：

    -   在需要时安装 Intune 客户端软件。

    -   使用 Intune 中可用的软件和硬件报告。

**了解更多信息？**

[企业移动性 + 安全性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)


<!--HONumber=Oct16_HO1-->


