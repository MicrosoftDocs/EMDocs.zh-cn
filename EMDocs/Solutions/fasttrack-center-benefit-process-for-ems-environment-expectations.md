---
title: "源环境预期"
description: "使用 FastTrack 中心权益所需的源环境要求"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 608f2a8de302f2d36b4a70fe631cc231963e41f8
ms.openlocfilehash: 18be543bd0b3442d6f623cba4c5260e93b42d2b8


---


# <a name="source-environment-expectations"></a>源环境预期
使用[企业移动性 + 安全性 (EMS) 的 FastTrack 中心权益](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)让 Microsoft Azure Active Directory Premium 和 Microsoft Intune 可供使用时，你的环境需满足以下各节所述的期望。

可能你的当前环境中已存在本地 Microsoft Active Directory，而你希望将其与 EMS 或其任何单独的服务集成，以便从单个控制台使用丰富的标识管理。 FastTrack 中心权益包括将 Azure AD 与现有的本地实现进行集成方面的帮助。 如果需要集成，源环境必须满足此应用程序的最低级别。

下表介绍了用于载入的现有源环境的预期内容。

|活动|源环境预期|
|------------|----------------------------------|
|核心载入|功能林级别设置为 Windows Server 2008 或更高版本且进行了以下林配置的 Active Directory 林：<br /><br />-   单个 Active Directory 林<br />-   多个 Active Directory 林 </br></br>**注意**：对于所有多林配置，Active Directory Federation Services (AD FS) 部署不在 FastTrack 中心权益的范围之内。|
|Azure AD Premium 载入|本地 Active Directory 及环境已准备就绪，可用于 Azure AD Premium，包括修正了会阻止 Azure AD 与 Azure AD Premium 功能集成的标识问题。|
|Intune, 仅限云或与 System Center Configuration Manager 集成, 载入|对于使用与 Intune 相连接的 Configuration Manager 2012 R2 或更高版本进行的设备管理，IT 管理员需要遵循[管理员清单：配置 Configuration Manager 以使用 Microsoft Intune 来管理移动设备](https://technet.microsoft.com/library/jj943763.aspx)。</br></br> **注意**：服务权益不包括协助设置 Configuration Manager 或将其升级到满足 Microsoft Intune 与 Configuration Manager 集成所需的最低要求。</br></br>对于 WiFi 和 VPN 配置文件部署，IT 管理员需确保其生产环境中已存在现成可用且处于运行状态的证书颁发机构、WiFi 和 VPN 基础结构。</br></br> **注意**：服务权益不包括有关设置或配置证书颁发机构、WiFi 或 VPN 基础结构方面的帮助。 |
|Azure 中的 Intune 管理体验 | 2016 年 12 月，Microsoft Intune [公布](https://blogs.technet.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/)了其在 Azure 门户 (portal.azure.com) 中的新 Intune 管理体验的公共预览版，通常称为 Intune on Azure。<br><br>公共预览期间，我们只会尽力为 Intune on Azure 提供载入支持。 将继续为现有管理控制台 (manage.microsoft.com) 提供完整载入支持。<br><br>在今年晚些时候正式推出后，FastTrack 将完全支持 Intune on Azure 体验。


**想要了解更多信息？**

[企业移动性 + 安全性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Jan17_HO3-->


