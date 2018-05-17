---
title: FastTrack 职责
description: FastTrack 在客户使用适用于 EMS 的 FastTrack 中心权益时肩负的职责
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 04/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: b9fb99c2c5bd640a033684096bd8f189a09b1698
ms.sourcegitcommit: 0863dce817862f00068614f2c62698784eb76d84
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="fasttrack-responsibilities"></a>FastTrack 职责

FastTrack 在加入期间的职责如下。

## <a name="general"></a>常规

-   对于所需的配置活动，为你提供远程支持协助（请参阅具体阶段中所列内容）。

-   提供可用的文档、软件工具和管理控制台，帮助你减少或消除配置任务。

## <a name="initiate-phase"></a>启动阶段

-   和你一起合作，开始载入服务。

-   定义您要载入的符合条件的服务。

## <a name="assess-phase"></a>评估阶段

-   提供管理概述。

-   提供以下方面的指导：

    -   DNS、网络和基础结构需求。

    -   客户端需求（Internet 浏览器、客户端操作系统和服务需求）。

    -   用户标识和设置。

    -   启用已购买且定义为载入部分的符合条件的服务。

-   为修正活动设置时间表。

-   为 Intune 和 Azure AD Premium 提供修正清单。

## <a name="remediate-phase"></a>修正阶段

-   根据商定的日程与你进行电话会议，审阅修正活动的进度，例如在载入 Microsoft 云服务之前指导你满足安装先决条件。

## <a name="enable-phase"></a>启用阶段
提供以下方面的指导：

-   激活你的 Microsoft 联机服务租户或订阅。

-   配置 TCP/IP 协议和防火墙端口。

-   为符合条件的服务配置 DNS。

-   验证 Microsoft Online Services 的连接。

-   对于单林环境：

    -   在 Active Directory 域服务 (AD DS) 和符合条件的 Microsoft 联机服务之间安装目录同步服务器（仅指导，如果需要的话）。

    -   使用 Azure Actice Directory Connect 工具配置托管身份验证（密码哈希同步或直通身份验证）。 （仅指导，如果需要的话）。

        > [!NOTE]
        > 自定义规则扩展的开发和实现不在讨论范围内。

-   对于目标为联合标识的单林：根据需要安装并配置 Active Directory 联合身份验证服务 (AD FS)，在单个站点、容错配置中使用 Intune 对本地域进行身份验证。

    > [!NOTE]
    > 对于多林配置，AD FS 部署不在讨论范围内。

-   如果已部署单一登录 (SSO)，请测试其功能。

### <a name="enable-phase---microsoft-azure-active-directory-premium"></a>启用阶段 - Microsoft Azure Active Directory Premium

提供以下方面的指导：

- 激活 Azure AD Premium 帐户。

- 配置防火墙端口。

- 为符合条件的服务配置 DNS。

- 验证到 Azure AD Premium 服务的连接。

- 对于单林环境：

  -   根据需要，在你的 Active Directory 域服务 (AD DS) 和 Azure AD Connect 之间安装目录同步。

  -   使用 Azure AD Connect 工具配置身份验证方法（密码哈希同步或传递身份验证）。

- 对于多林环境：

  -   安装 Azure AD Connect 同步，为多林方案进行设置。
- 对于单林和多林环境：
  - 如果需要，请配置 Azure Active Directory 传递身份验证。
  - 如果需要，请配置 Azure Active Directory 无缝单一登录 (SSO)。
    > [!NOTE]
    > 如果你的 Active Directory 林之间存在林信任，并且名称后缀路由得到正确配置，则支持多林环境的 Azure Active Directory 传递身份验证。 可在多个本地服务器上安装其他代理，为登录请求提供高可用性。

  - 有关详细信息，请参阅 [Azure Active Directory 直通身份验证：快速入门](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication-quick-start#step-1-check-prerequisites)和 [Azure Active Directory 无缝单一登录：快速入门](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start#step-1-check-prerequisites)。
  - 若要详细了解直通身份验证限制，请参阅 [Azure Active Directory 直通身份验证：当前限制](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication-current-limitations)。
  - 若要详细了解无缝 SSO 问题，请参阅[排查 Azure Active Directory 无缝单一登录问题](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-troubleshoot-sso)。

      > [!NOTE]
      > 密码哈希同步和密码写回支持多林。 但是，不支持其他写回方案。

  - 配置本地 Active Directory 林和 Microsoft Azure Active Directory Premium 目录 (Azure Active Directory) 之间的同步。

    > [!NOTE]
    > 自定义规则扩展的开发和实现不在讨论范围内。

- 对于目标为联合标识的单林：

  -   根据需要安装并配置 AD FS，以便在单个站点、容错配置中使用 Azure AD Premium 进行本地域身份验证。

  > [!NOTE]
  > 对于多林配置，AD FS 部署不在讨论范围内。

- 测试 SSO 功能（如果已部署）。

### <a name="enable-phase---azure-ad-premium--with-azure-ad-connect-and-ad-fs"></a>启用阶段 - Azure AD Premium-- 使用 Azure AD Connect 和 AD FS

提供设置以下内容的相关指导：

- 用户设置（包括许可）。

- Azure AD Connect 目录同步（使用密码写回和密码哈希同步）。

  - 自助服务密码重置 (SSPR)。

  - Azure 多重身份验证。

  - 多达三 (3) 个及以上服务型软件 (SaaS) 应用程序与来自 [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/) 的 SSO 集成。

  - 自定义的登录屏幕（包括徽标、文本和图像）。

  - 自助服务和动态组（组）。

  - Azure Active Directory 应用程序代理。

  - Azure AD Connect 运行状况。

  - 标识保护。

  - 特权标识管理。

  - Azure Active Directory 条件访问。

### <a name="enable-phase---intune"></a>启用阶段 - Intune

> [!IMPORTANT]
> FastTrack 不支持使用 Intune 进行 Windows 10 经典电脑管理。 FastTrack 仅支持通过 Intune 移动设备管理 (MDM) 进行 Windows 10 管理。

提供以下方面的指导：

-   通过利用本地 Active Directory 或利用云标识，配置将由 Intune 使用的标识 (Azure Active Directory)。

-   授权你的最终用户。

-   向 Intune 订阅添加用户时，定义 IT 管理员角色并创建用户组和设备组。

-   根据管理需要配置移动设备管理 (MDM) 机构，包括：

    -   Intune 是你唯一的 MDM 解决方案时将 Intune 设为 MDM 机构。

    -   如果已具有 Configuration Manager 的现有实施，并想使用 Intune 扩展其管理功能，请将 System Center Configuration Manager 设置为 MDM 机构。

    -   配置用于验证 MDM 管理策略的测试组。

    -   浏览 Intune 管理门户来查找有关用户和设备的信息。

    -   设置 Intune 角色（支持人员、管理员等）

    -   配置 MDM 管理策略和服务，如：

        -   通过 Web 链接、MSI 和/或深层链接为每个受支持平台进行的应用部署。

        -   将 Office 专业增强版部署到 Windows 10 设备。

        -   用于应用部署的批量购买计划，包括 Apple VPP、Windows Store for Business 和 Google Play for Work Store。

        -   电子邮件、无线网络和 VPN 配置文件的部署（如果组织中有现有的证书颁发机构、Wi-Fi 或 VPN 基础结构）。

        -   设置 Microsoft Intune Exchange Connector（如果适用）。

        -   受支持设备平台的设备配置文件。

    -   设置条件访问策略。

    -   为每个支持平台配置和部署 Intune 应用保护策略。

    -   通过可用选项的相关指南，为 Intune 应用保护策略准备业务线 (LOB) 应用。

    -   将每个受支持平台的设备注册到 Intune 或具有 Microsoft Intune 服务的 Configuration Manager。

    -   连接到 Intune 数据仓库。

    -   将 Intune 与以下产品集成：
        -   Team Viewer，获取远程协助（Team Viewer 订阅是必需的）。

        -   移动威胁防御合作伙伴解决方案（移动威胁防御合作伙伴解决方案订阅是必需的）。

        -   电信费用管理解决方案（电信费用管理解决方案订阅是必需的）。

        -   Windows Defender 高级威胁防护（Windows E5 或 Microsoft 365 E5 许可证是必需的）。

    -   为适用的受支持平台配置软件更新。

    -   用户采用规划的相关资源。

> [!NOTE]
> **想要了解更多?** 请参阅[企业移动性 + 安全性](https://www.microsoft.com/cloud-platform/enterprise-mobility)。

## <a name="next-steps"></a>后续步骤

[EMS 的 FastTrack 权益 - 你的职责](fasttrack-center-benefit-process-for-ems-your-responsibilities.md)
