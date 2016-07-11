---
title: "强化移动设备"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: ade57c73-a8a2-497f-ad8d-5dfc3cba9e70
ms.reviewer: 
ms.suite: ems
ms.sourcegitcommit: a16e90093c7571f3c098ce815a2b70ae03c080e3
ms.openlocfilehash: 1a8b4be857a8fede2df37db1eabd7b95cea1dba9


---

# 强化移动设备

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

在为移动设备创建配置基线以根据你的业务需求强化其功能时，请确保平衡可用性与安全性。 非常严格的强化模板可能会使你的员工遇到可用性和访问问题，这将破坏帮助用户通过使用其设备访问公司资源来提高效率的目的。 

此外，请记住并非所有策略都可用于所有移动设备平台。 你可能需要平衡允许组织中的移动设备平台与强化设备的安全合规性要求之间的优先级。
处理移动设备强化的一个方式是使用不同层的安全性。 可用于每个层的设置也可能因 MDM 解决方案而异。 下图显示了如何设置此分层方法的示例。

![安全层](./media/MDM_Figure_12.png)

## 移动设备强化的不同区域

每个层可用于对必须符合你的业务安全要求的区域进行分组。 例如，可以配置 Intune 以部署专门用于强化系统设置并启用加密的设备的[安全策略](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)。 这些策略还将通过创建访问允许列表来确保仅[兼容应用](https://technet.microsoft.com/library/dn818906.aspx)可在移动设备上进行安装。

在运行 Windows 8.1 企业版的 BYOD 设备上，AppLocker 使您可以基于应用的文件路径、哈希或在应用程序更新中保持原样的属性（如发布者名称、产品名、文件名和文件版本）允许或阻止应用。 在 Windows 10 中，添加新的 AppLocker 配置服务提供程序以允许您通过使用 MDM 服务器来启用 AppLocker 规则。 有关 Windows 10 中这一新功能的详细信息，请阅读 [AppLocker CSP](https://msdn.microsoft.com/library/windows/hardware/dn920019(v=vs.85).aspx)。

应该控制的另一个方面是用户的移动浏览体验。 托管浏览器策略包括允许或阻止列表，用于限制托管浏览器的用户可以访问的网站。 有关如何在 Intune 中配置这些策略的详细信息，请阅读[通过 Microsoft Intune 使用托管浏览器策略管理 Internet 访问](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)。

在具有本地 ConfigMgr 的混合环境中，你可以创建[配置基线](https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)以设置托管移动设备的基本强化状态。 自定义此基线以包括所有所需的设置，然后将其部署到移动设备。 合规性设置选项将因移动设备平台而异，因此有关可用于每个设备的选项的详细信息，请阅读 [Configuration Manager 中的移动设备的合规性设置](https://technet.microsoft.com/library/dn376523.aspx)。

[适用于 Office 365 的 MDM](https://technet.microsoft.com/library/ms.o365.cc.devicepolicy.aspx) 还有一组针对以下类别协助你强化移动设备的功能：

- 安全
- Encryption
- 已越狱
- 托管电子邮件配置文件

有关如何为强化这些选项设置安全策略的详细信息，请阅读文章[内置的适用于 Office 365 的移动设备管理的功能](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx)。

强化移动设备平台对于在保护公司数据的同时允许用户在不影响安全性的情况下使用他们的移动设备起到了重要的作用。 使用下表作为参考协助你选择最符合组织的数据强化要求的 MDM 选项。

## Intune（独立版）

**优点**

- 允许你为注册设备强制执行策略：加密、恶意软件、应用、电子邮件、电子邮件配置文件、越狱、系统和安全
- 支持主要移动设备平台的策略部署，包括（Android、iOS、Windows 10、Windows 8.x 和 Windows Phone）

**缺点**

- 缺乏与当前本地 MDM 平台的集成，将引入一个附加的管理接口供你在管理移动设备时使用
- 某些策略可能不适用于某些移动平台

## Office 365 的 MDM

**优点**

- 允许你为注册设备强制执行策略：加密、应用、越狱和安全
- 支持主要移动设备平台的策略部署，包括（Android、iOS、Windows 10、Windows 8.x 和 Windows Phone）

**缺点**

- 缺乏与当前本地 MDM 平台的集成，将引入一个附加的管理接口供你在管理移动设备时使用
- 某些策略可能不适用于某些移动平台
- 不允许与 Intune 相当的粒度

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 允许你为注册设备强制执行策略：加密、恶意软件、应用、电子邮件、系统、安全和越狱
- 支持主要移动设备平台的策略部署，包括（Android、iOS、Windows 10、Windows 8.x 和 Windows Phone）
- 从云和本地设备注册的移动设备的单个管理控制台

**缺点**

- 如果你的公司没有当前本地 ConfigMgr 基础结构，它将在集成前需要资源来规划、安装和配置 ConfigMgr

>[!TIP] 请在 [Microsoft Intune 的移动设备管理策略设置](https://technet.microsoft.com/library/dn913730.aspx)中阅读有关可在 Microsoft Intune 移动设备安全策略中配置的移动设备管理设置的详细信息。 



<!--HONumber=Jun16_HO4-->


