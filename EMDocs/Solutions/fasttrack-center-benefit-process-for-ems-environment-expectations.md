---
title: 源环境预期
description: 使用 EMS 的 FastTrack 中心权益所需的源环境要求
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: 65b7b77bb0afafc019c44c2fb980c18ee782471a
ms.sourcegitcommit: 06c39d619052a609c250b8b3978d9061841a6ff2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2018
ms.locfileid: "51859220"
---
# <a name="source-environment-expectations"></a>源环境预期

使用[企业移动性 + 安全性 (EMS) 的 FastTrack 中心权益](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)让 Microsoft Azure Active Directory Premium 和 Microsoft Intune 可供使用时，你的环境需满足以下各节所述的期望。

可能你的组织中已存在本地 Active Directory，而你希望将其与企业移动性 + 安全性 (EMS) 或从单个控制台使用丰富的标识管理的其任何单独的服务集成。 企业移动性 + 安全性 (EMS) 的 FastTrack 中心权益包括帮助你将 Azure Active Directory 与现有的本地 Active Directory 环境进行集成。

下表显示了用于载入的现有源环境的预期内容。

|活动|源环境预期|
|------------|----------------------------------|
|核心载入|功能林级别设置为 Windows Server 2008 或更高版本且进行了以下林配置的 Active Directory 林：<br /><br />-   单个 Active Directory 林<br />-   多个 Active Directory 林 </br></br>**注意**：对于所有多林配置，Active Directory Federation Services (AD FS) 部署不在 FastTrack 中心权益的范围之内。|
|Azure AD Premium 载入|本地 Active Directory 及环境已准备就绪，可用于 Azure AD Premium，包括修正了会阻止 Azure AD 与 Azure AD Premium 功能集成的标识问题。|
|Intune 载入| 规划使用 Intune 部署 WiFi 和 VPN 配置文件时，IT 管理员需确保其生产环境中已存在现成可用且处于运行状态的证书颁发机构、WiFi 和 VPN 基础结构。<br /><br /> 注意：服务权益不包括有关设置或配置证书颁发机构、WiFi、VPN 基础结构或 Apple MDM 推送证书方面的帮助。  |
|共同管理|通过共同管理，IT 管理员负责准备本地环境，其中可能包括修正当前阻止使用 Configuration Manager 和 Intune 同时管理 Windows 10 设备的问题。<br /><br />注意：FastTrack 服务权益不包括协助设置或升级 Configuration Manager 网站服务器和/或 Configuration Manager 客户端以满足支持使用 Windows 10 设备进行共同管理所需的最低要求。 |
|Intune 与 Windows Defender 高级威胁防护 (Windows Defender ATP) 集成|你的 Windows Defender ATP 订阅已根据贵公司的安全要求进行激活和配置。<br /><br />**注意**：FastTrack 服务权益可帮助将 Intune 与 Windows Defender ATP 集成，并根据其 Windows 10 风险级别评估创建设备符合性策略。 FastTrack 服务权益不提供有关购买、授权、激活或使用 Windows Defender ATP 及其安全中心控制台的帮助。 |
|Windows Autopilot|IT 管理员负责将其设备注册到其组织，方法是让硬件供应商代表其自己上载其硬件 ID 或让他们亲自将其上载到 Windows Autopilot 服务。 |
|通过 Intune 安全地部署 Outlook for iOS 和 Outlook for Android|<br /><br />-   在 Azure AD for Office 365 中启用了用户标识。<br />-   使用分配的用户许可证配置了 Exchange Online 或混合 Exchange。<br />|

> [!NOTE]
> **想要了解更多？**
> [企业移动性 + 安全性](https://www.microsoft.com/cloud-platform/enterprise-mobility)

## <a name="next-steps"></a>后续步骤

[EMS 载入和迁移阶段的 FastTrack 中心权益](fasttrack-center-benefit-process-for-ems-phases.md)
