---
title: "制定事件响应要求"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 1072858e-dc0a-44ad-a512-d938f20310b6
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d43860e838a40de05bdec73b00b6721ee634d7e5
ms.openlocfilehash: bfeb1fd4cceacf225093d3a5c2d808ebeb21c825


---

# 数据加密

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

现在你已回答了任务 1 中有关处于静态时和传输过程中的数据加密要求的问题，接下来你将评估可用于处理每个要求的选项。 即使数据处于静态，仍然可以采用不同的方法对其进行加密，如下图所示。

![移动设备磁盘](./media/MDM_Figure_09.png)

## 不同的加密级别

你可以使用完整磁盘加密或基于应用所处理的数据的加密。 [ConfigMgr](https://technet.microsoft.com/library/dn919655.aspx) 允许你强制执行将在移动设备上执行文件加密的策略。 尽管某些移动设备（如 Windows Phone 8）将自动加密，但某些其他移动设备仅在启用某些其他选项时加密数据。 例如，对于 iOS 设备，加密仅在你将设置配置为需要在设备上使用密码后自动发生。 

Windows 10 移动版使用基于 BitLocker 技术的设备加密来加密所有内部存储，包括操作系统和数据存储分区。 通过 MDM 工具，用户可以激活设备加密，或者 IT 部门可以激活并强制对公司管理的设备执行加密。 启用设备加密后，存储在手机上的所有数据都会自动进行加密。 启用了加密的 Windows 10 移动版设备有助于在设备丢失或被盗的情况下保护存储数据的保密性。 阅读 Windows 10 移动版安全指南，了解更多信息。

>[!TIP] 有关可以使用 ConfigMgr 启用加密的移动设备的详细信息，请阅读 [Configuration Manager 中的移动设备的合规性设置](https://technet.microsoft.com/library/dn376523.aspx)。

对于与 Intune 移动应用程序管理策略关联的应用，加密由 Microsoft 提供。 根据移动应用程序管理策略的设置，数据在文件 I/O 运行过程中同步加密。 在 Android 设备上，托管应用利用平台加密库（非 FIPS 140-2 认证）在加密块链接 (CBC) 模式下使用 AES-128 加密。 

此选项允许你指定将加密与特定应用相关联的所有数据，包括存储在外部媒体（例如 SD 卡）上的数据。 相同的功能也可用于[适用于 Office 365 的 MDM](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx)。 

公有云存储服务（例如 OneDrive for Business）还可以与 Intune Standalone 集成，也可以与 [System Center 2012 R2 Configuration Manager SP1](https://technet.microsoft.com/library/mt131422.aspx) 集成。 你可以将 OneDrive for Business 应用部署到用户的设备，然后用户的 OneDrive for Business 帐户中的所有文档都将加密。 

大多数 MDM 解决方案使用 SSL 来保护传输过程中的数据，因此你只需确定你是否将使用现有 PKI 来颁发证书，或者你是否将使用第三方供应商证书颁发机构 (CA)。 使用第三方 CA 的好处是使用自己的设备来访问公司资源的用户将自动信任公认的公用 CA。 

## Intune（独立版）

**优点** 

- 加密与受 Intune 管理策略控制的应用相关联的数据

**缺点** 

- 不包括移动设备存储的本机加密
- 没有与当前本地 MDM 平台的集成意味着将增加一个管理接口供你使用

## Office 365 的 MDM

**优点**

- 基于移动设备平台功能加密数据

**缺点**

- 如果组织没有当前本地 ConfigMgr 基础结构，则需在集成前规划、安装和配置此平台

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 加密与受 Intune 管理策略控制的应用相关联的数据
- 加密移动设备存储
- 对于可以在移动设备上加密哪些内容和如何完成加密提供更细化的控制，包括加密算法的选择

**缺点**

- 如果组织没有当前本地 ConfigMgr 基础结构，则需在集成前规划、安装和配置此平台

有关如何将 Intune 和 ConfigMgr 功能结合以增加数据保护并配置加密的详细信息，请阅读[使用配置管理器和 Intune 在移动设备上管理加密](http://blogs.technet.com/b/pauljones/archive/2014/08/04/managing-encryption-on-mobile-devices-with-configuration-manager-and-intune.aspx)。



<!--HONumber=Jun16_HO4-->


