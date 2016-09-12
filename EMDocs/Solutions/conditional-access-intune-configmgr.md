---
title: "通过 Intune 和 Configuration Manager 使用条件访问"
description: "使用 Configuration Manager 解决方案部署 Intune。"
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e65a0662-33ff-4e8c-9305-a21e80ea0f69
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: faa30f461ff9a1a14d150bd85d86d37cd298570c
ms.openlocfilehash: 4d7d429b4c6ede6197501f4035903f23cbe2ade3


---

# 通过 Intune 和 Configuration Manager 使用条件访问
本主题假设你已在公司中使用 System Center Configuration Manager 和本地 Microsoft Exchange Server、Exchange Online 或两者的混合部署来管理电子邮件访问。 该解决方案将现有的 Configuration Manager 环境与 Intune 相结合，以便安全地管理所有类型设备上的电子邮件访问，而无需考虑设备的位置。

> [!TIP]
> 可在 [TechNet 库](https://gallery.technet.microsoft.com/Deploying-Enterprise-16499404)中获取本完整主题的可下载副本。

## 在开始之前
在你开始使用条件性访问之前，请确保已经满足正确的要求：

## 对于 Exchange Online
条件访问 Exchange Online 支持运行以下操作系统的设备：

-   Windows 8.1 及更高版本（注册到 Intune 时）

-   Windows 7.0 或更高版本（若已加入域）

-   Windows Phone 8.1 及更高版本

-   iOS 7.1 及更高版本

-   Android 4.0 及更高版本、Samsung Knox 标准版 4.0 及更高版本

此外，设备必须通过 Azure Active Directory 设备注册服务 (AAD DRS) 进行注册。

AAD DRS 将对 Intune 和 Office 365 客户自动激活。 已经部署了 ADFS 设备注册服务的用户将不会在他们本地的 Active Directory 上看到已注册的设备。

-   你必须使用包含 Exchange Online（例如 E3）的 Office 365 订阅，并且用户必须获得 Exchange Online 许可。

-   可选的 **Microsoft Intune 服务间连接器**将 Intune 连接到 Microsoft Exchange Online，并帮助你通过 Intune 控制台管理设备信息（请参阅[使用 Exchange ActiveSync 和 Microsoft Intune 管理移动设备](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)）。 你不需要使用连接器来使用合规性策略或条件性访问策略，但要求你运行帮助评估条件性访问影响的报告。

    如果你配置了连接器，那么 Intune 中的某些 Exchange ActiveSync 策略可能在 Office 控制台中可见，但没有设置为默认策略，因此不会影响设备。

    > [!IMPORTANT]
    > 如果你要同时对 Exchange Online 和 Exchange 内部部署使用条件访问，则不要配置服务间连接器。

    现在，你就可以了解如何[使用 Intune 部署 Exchange Online](conditional-access-intune-exchange-online.md)。

## 对于本地 Exchange Server
Exchange 内部部署支持的条件访问：

-   Windows 8 及更高版本（注册到 Intune 时）

-   Windows Phone 8 及更高版本

-   使用 Exchange ActiveSync (EAS) 电子邮件客户端的任何 iOS 设备

-   Android 4 及更高版本

此外：

-   你的 Exchange 版本必须是 Exchange 2010 或更高版本。 支持 Exchange Server 客户端访问服务器 (CAS) 配置。

    > [!TIP]
    > 如果你的 Exchange 环境在 CAS 服务器配置中，则必须将本地 Exchange 连接器配置为指向任一 CAS 服务器。

-   可以基于身份验证或用户凭据条目使用证书来配置 Exchange ActiveSync。

-   必须使用**本地 Exchange 连接器**，它将 Intune 连接到本地 Microsoft Exchange Server。 这样就可以通过 Intune 控制台管理设备（请参阅[使用 Exchange ActiveSync 和 Microsoft Intune 管理移动设备](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)）。

  > [!IMPORTANT]
> 请确保使用最新版本的本地 Exchange 连接器。 Intune 控制台中可供你使用的内部部署 Exchange 连接器特定于你的 Intune 租户，不能用于其他任何租户。 此外，还应确保仅在一台计算机（而不是多台计算机）上安装适用于你的租户的 Exchange 连接器。

  现在，你就可以了解如何[使用 Intune 部署本地 Exchange Server](conditional-access-intune-exchange.md)。

如果你的环境包括 Exchange Online 和 Exchange 内部部署，你可以阅读[使用 Microsoft Intune 和 Configuration Manager 部署 Exchange Online 和 Exchange 内部部署](conditional-access-intune-configmgr-coexist.md)的相关信息。



<!--HONumber=Sep16_HO1-->


