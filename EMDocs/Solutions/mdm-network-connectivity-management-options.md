---
# required metadata

title: 网络连接管理选项
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: bc7cdb8f-3485-45ae-9493-f840ad9ed3ea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 网络连接管理选项

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

根据基础结构，移动设备可以从各种 Internet 连接服务连接到企业资源，这些资源通常由 VPN 保护的终结点进行保护。

使用 [Intune](/Intune/deployuse/wi-fi-connections-in-microsoft-intune) 或与 ConfigMgr 的[混合部署](https://technet.microsoft.com/library/dn261221.aspx)，你可以部署 Wi-Fi 配置文件来预配 Wi-Fi 网络，使设备在位于网络范围内时可自动连接到网络。 例如，移动设备可配置为连接分段到会议室的 Wi-Fi 网络，但在漫游到不同位置时又随即切换为连接某个 Wi-Fi 网络段。 用户无需输入密码或选择网络，因为连接自动进行。

[Intune](/Intune/deployuse/vpn-connections-in-microsoft-intune) 和 [ConfigMgr](https://technet.microsoft.com/library/dn261217.aspx) 也可以将 VPN 配置文件直接部署到移动设备，从而让用户无需额外配置或手动操作即可访问内部企业资源。 此外，Intune 还可以将移动设备配置为自动启动基于资源类型或访问方法的 VPN 连接。 但请注意，不同类型的移动设备操作系统执行此操作会有不同的配置要求。

对任务 3 中的问题的回答可以帮助你确定设备要如何连接企业资源。 请注意，<token> Office 365 的 MDM</token> 当前不支持管理移动设备的无线和 VPN 网络资源。

下表列出了使用 Intune 独立版和带 ConfigMgr 的 Intune 混合版来管理无线网络和 VPN 网络的优缺点。

## Intune（独立版）

**优点**

- 支持所有主要的移动设备操作系统（Android、iOS、Windows 10、Windows 8.x 以及 Windows Phone）上的无线和 VPN 配置文件 
- 支持业界领先的 VPN 连接类型，包括 Cisco、Juniper、Dell SonicWall 和 Checkpoint 等
- 无线和 VPN 配置文件可与 SCEP 证书配置文件集成，以提升安全性
- 支持为不同类型的用户、设备、设备操作系统或用户组和角色配置自定义的无线和 VPN 配置文件
- Windows 10、Windows 8.1、Windows Phone 8.1 和 iOS 支持基于 DNS 名称启动
- 基于应用程序 ID 的初始化支持 Windows 10 和 Windows 8.1
- 选择通过 VPN 配置文件中的 VPN 自动连接到你的企业网络的应用。

**缺点**

- 若要支持 VPN 配置文件，你将需要部署和维护本地 VPN 基础结构

## Office 365 的 MDM

Office 365 的 MDM 不支持 Wi-Fi 和 VPN 策略。

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 除了 Intune 独立版的所有优点外，还包括以下优点：
    - 现有的本地企业 VPN 基础结构支持 VPN 配置文件

**缺点**

- 若要支持 VPN 配置文件，你将需要部署和维护本地 VPN 基础结构 
- 必须授予特定安全权限，以在 ConfigMgr 中管理 [Wi-Fi 配置文件](https://technet.microsoft.com/library/dn408646.aspx)和 [VPN 配置文件](https://technet.microsoft.com/library/dn408643.aspx)

查看以下内容，了解有关移动设备电子邮件配置管理选项的详细信息：

- Intune：启用[无线](/Intune/deployuse/wi-fi-connections-in-microsoft-intune)和 [VPN](/Intune/deployuse/vpn-connections-in-microsoft-intune) 配置文件
- ConfigMgr：启用[无线](https://technet.microsoft.com/library/dn261221.aspx)和 [VPN](https://technet.microsoft.com/library/dn261217.aspx) 配置文件

<!--HONumber=Jun16_HO1-->


