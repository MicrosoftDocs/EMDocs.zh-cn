---
title: 源环境预期
description: 使用 EMS 的 FastTrack 中心权益所需的源环境要求
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: beee0fe5a4b0907b6584f22d9c2a9967f83e5161
ms.sourcegitcommit: ffa46a69834de317e99a58146492e06c6aa4901a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="source-environment-expectations"></a>源环境预期

使用[企业移动性 + 安全性 (EMS) 的 FastTrack 中心权益](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)让 Microsoft Azure Active Directory Premium 和 Microsoft Intune 可供使用时，你的环境需满足以下各节所述的期望。

可能你的组织中已存在本地 Active Directory，而你希望将其与 EMS 或其任何单独的服务集成，以便从单个控制台使用丰富的标识管理。 EMS 的 FastTrack 中心权益包括帮助你将 Azure Active Directory 与现有的本地 Active Directory 环境进行集成。

下表介绍了用于载入的现有源环境的预期内容。

|活动|源环境预期|
|------------|----------------------------------|
|核心载入|功能林级别设置为 Windows Server 2008 或更高版本且进行了以下林配置的 Active Directory 林：<br /><br />-   单个 Active Directory 林<br />-   多个 Active Directory 林 </br></br>**注意**：对于所有多林配置，Active Directory Federation Services (AD FS) 部署不在 FastTrack 中心权益的范围之内。|
|Azure AD Premium 载入|本地 Active Directory 及环境已准备就绪，可用于 Azure AD Premium，包括修正了会阻止 Azure AD 与 Azure AD Premium 功能集成的标识问题。|
|Intune, 仅限云或与 System Center Configuration Manager 集成, 载入|对于使用与 Intune 相连接的 Configuration Manager 2012 R2 或更高版本进行的设备管理，IT 管理员需要遵循[管理员清单：配置 Configuration Manager 以使用 Microsoft Intune 来管理移动设备](https://technet.microsoft.com/library/jj943763.aspx)。</br></br> **注意**：服务权益不包括协助设置 Configuration Manager 或将其升级到满足 Microsoft Intune 与 Configuration Manager 集成所需的最低要求。</br></br>对于 WiFi 和 VPN 配置文件部署，IT 管理员需确保其生产环境中已存在现成可用且处于运行状态的证书颁发机构、WiFi 和 VPN 基础结构。</br></br> **注意**：服务权益不包括有关设置或配置证书颁发机构、WiFi 或 VPN 基础结构方面的帮助。 |

> [!NOTE]
> **想要了解更多？**
> [企业移动性 + 安全性](https://www.microsoft.com/cloud-platform/enterprise-mobility)

## <a name="next-steps"></a>后续步骤

[EMS 载入和迁移阶段的 FastTrack 中心权益](fasttrack-center-benefit-process-for-ems-phases.md)
