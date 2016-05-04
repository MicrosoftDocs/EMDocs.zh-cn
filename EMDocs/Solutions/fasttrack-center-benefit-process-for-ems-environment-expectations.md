---
# required metadata

title: 企业移动性套件的 FastTrack 中心权益流程 – 源环境预期
description:
keywords:
author: 
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# 企业移动性套件的 FastTrack 中心权益流程 – 源环境预期
当你使用[企业移动性套件 (EMS) 的 FastTrack 中心权益](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)使 Azure Active Directory Premium、Microsoft Intune 和/或 Azure 权限管理可供使用时，你的环境需满足以下各节所述的期望。

若要阅读有关 FastTrack 载入流程的其他部分，请参阅[企业移动性套件 (EMS) 的 FastTrack 中心权益流程](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md)。

可能你的当前环境中已存在本地 Microsoft Active Directory，而你希望将其与 EMS 或其任何单独的服务集成，以便从单个控制台使用丰富的标识管理。 FastTrack 中心权益包括帮助你将 Microsoft Azure Active Directory Premium 与现有的本地实现进行集成。 如果需要集成，你的源环境必须处于此应用程序的最低级别。

下表介绍了用于载入的现有源环境的预期内容。

|活动|源环境预期|
|------------|----------------------------------|
|核心载入|功能林级别设置为 Windows Server 2008 或更高版本且进行了以下林配置的 Active Directory 林：<br /><br />-   单个 Active Directory 林<br />-   多个 Active Directory 林 </br></br>[!NOTE]：对于所有多林配置，AD FS 部署不在 FastTrack 中心权益的范围之内。|
|Microsoft Azure Active Directory Premium 载入|本地 Active Directory 及环境已准备就绪，可用于 Azure Active Directory Premium，包括修正了会阻止 Azure Active Directory 与 Azure Active Directory Premium 功能集成的标识问题。|
|Microsoft Intune、仅限云或与 System Center Configuration Manager 集成、载入|对于使用与 Microsoft Intune 进行连接的 System Center Configuration Manager 2012 R2 或更高版本进行设备管理，IT 管理员需要遵循 [管理员清单：配置 Configuration Manager 以使用 Microsoft Intune 来管理移动设备](https://technet.microsoft.com/library/jj943763.aspx).</br></br> [!NOTE]：服务权益不包括协助设置 System Center Configuration Manager 或将其升级到满足 Microsoft Intune 与 System Center Configuration Manager 集成所需的最低要求。|


>[!div class="step-by-step"]
[FastTrack 概述](fasttrack-center-benefit-process-for-ems-overview.md)
[FastTrack 阶段](fasttrack-center-benefit-process-for-ems-phases.md)

### 了解更多信息？
请参阅[企业移动性套件](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)。



<!--HONumber=Apr16_HO2-->


