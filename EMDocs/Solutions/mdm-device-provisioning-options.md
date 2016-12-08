---
title: "设备设置选项"
description: "本文提供有关使用企业移动性 + 安全性规划和设计 Microsoft 移动设备管理解决方案时的设备设置选项的指导。"
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 991cd722-089c-4e8c-80b9-b82e405cc891
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 3df9be3ef643303f4205aa1b6daf18fdf53762d8


---

# <a name="device-provisioning-options"></a>设备设置选项

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

如果用户可以使用和注册自己的设备，这不仅会增加对用户和 IT 的要求，也会对多个方面造成影响。 例如，下图显示使用 Intune 和 ConfigMgr 的组织的注册过程概述。 本示例概述了在计划解决方案时需要考虑的证书、Web 应用程序和同步注意事项：

![使用混合 Intune 和 ConfigMgr 的移动设备的注册过程概述](./media/MDM_Figure_04.png)

**使用混合 Intune 和 ConfigMgr 的移动设备的注册过程概述**

1. 通过 <token>Windows Server 2012 R2，引入了名为设备注册的新概念。  用户可以使用工作区加入注册其设备以用于单一登录和访问企业数据。  作为此注册过程的一部分，将在设备上安装证书。 在用户已注册其设备并了解设备管理解决方案后，用户可以获得对原先仅在加入域的电脑上使用的企业资源的访问权限。
2. 用户可[使用公司门户](/Intune/deploy-use/enroll-devices-in-microsoft-intune)通过 Intune 对要配置以供管理的设备进行注册，之后利用 Microsoft Intune 公司门户不仅可以轻松访问企业应用程序、数据，还能管理他们自己的设备，并在设备丢失、被盗或更换时执行诸如远程擦除等任务。
3. 根据设备感知（即设备是否已注册）和用户标识，你可以通过 Windows Server 2012 R2 中名为 [Web 应用程序代理](https://technet.microsoft.com/library/dn584107.aspx)的内置功能发布企业资源的访问权限。 如果你正使用企业移动性 + 安全性，还可使用 Azure AD 应用程序代理发布应用程序。 多重身份验证可通过 [Azure Active 身份验证](https://azure.microsoft.com/documentation/articles/multi-factor-authentication-get-started-cloud/)进行使用。
4. 为了向管理员提供整个环境的统一视图，Intune 中的数据将与在本地和云中提供统一管理的 ConfigMgr 同步。
5. 作为注册过程的一部分，将在 Active Directory 中创建一个新的设备对象。  此设备对象用于在用户与其设备之间建立链接、将此链接告知设备管理解决方案，并允许对设备进行身份验证，从而有效形成无缝双重身份验证。

根据你对步骤 1 中的问题的回答，你应该能够确定想要在移动设备管理解决方案中如何管理设备。 下面的列表显示了每个预配选项的优缺点。

## <a name="intune-standalone"></a>Intune（独立版）

**优点**

- 支持注册和预配所有主要的移动设备操作系统（Android、iOS、Windows 10、Windows 8.x 以及 Windows Phone）
- 基于云的服务，可在任何可以访问 Internet 的位置注册移动设备
- 可通过集中且可自定义的公司门户注册设备
- 移动设备的高级设备预配选项

**缺点**

- （仅）在将本地管理平台用于非移动设备时，预配移动设备还有其他管理界面
- 适用于基于云的服务和本地管理平台的单独设备合规性和安全策略 

## <a name="mdm-for-office-365"></a>Office 365 的 MDM

**优点**

- 与 Office 365 租户集成，从而为移动设备和 Office 365 租户服务（Exchange Online、SharePoint Online 和 Skype for Business ）提供单个管理控制台
- 支持注册和预配所有主要的移动设备操作系统（Android、iOS、Windows 10、Windows 8.1 以及 Windows Phone）
- 移动设备的基本设备预配选项

**缺点**

- （仅）在将本地管理平台用于非移动设备时，预配移动设备还有其他管理界面
- 适用于基于云的服务和本地管理平台的单独设备合规性和安全策略
- 普通设备预配选项

## <a name="hybrid-intune-with-configmgr"></a>混合版（带 ConfigMgr 的 Intune）

**优点**

- Intune（基于云的设备管理服务）与 System Center 2012 Configuration Manager 和 System Center 2012 R2 Configuration Manager（本地设备管理平台）之间进行本机集成
- 支持注册和预配所有主要的移动设备操作系统（Android、iOS 和 Windows Phone），并包括预配所有主要的非移动设备操作系统
- 通过 Intune 连接性支持移动设备的高级设备预配选项

**缺点**

- 对于尚未配置当前 ConfigMgr 基础结构的组织，将需要在与 Intune 集成前进行规划、安装和配置
- 需要其他配置，以将 Intune 与本地 ConfigMgr 基础结构相连接

有关移动设备注册和预配选项的详细信息，请务必查看在 Intune 中如何[启用移动设备注册](/Intune/deploy-use/enroll-devices-in-microsoft-intune)，并将这些要求和步骤与在 ConfigMgr 和 MDM for Office 365 中[启用移动设备注册](https://technet.microsoft.com/library/jj884158.aspx)的要求和步骤进行比较。



<!--HONumber=Nov16_HO4-->


