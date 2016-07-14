---
title: "证书管理选项"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c3d350b5-4437-4f3d-907f-57ce6a819a74
ms.reviewer: 
ms.suite: ems
ms.sourcegitcommit: a16e90093c7571f3c098ce815a2b70ae03c080e3
ms.openlocfilehash: fed75819dbc13755b5ef28cbe3abe008d46c8473


---

# 证书管理选项

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

[Intune](/Intune/deploy-use/secure-resource-access-with-certificate-profiles) 独立版以及[混合 Intune 和 ConfigMgr](https://technet.microsoft.com/library/dn261202.aspx) 部署方案均支持使用数字证书管理和证书配置文件。 这些功能允许你将受信任的根证书部署到移动设备以及基于简单证书注册协议 (SCEP) 的配置文件，这将指示移动设备从组织中的 NDES 服务器获取其他证书。

因为 iOS、Windows 10 和 8.1 以及 Windows Phone 10 和 8.1 本机支持 SCEP，并且通过适用于 Android 的 Microsoft Intune 公司门户应用也可以支持 SCEP，所以使用此注册协议具有直接在移动设备上生成私钥的优势。 ConfigMgr 或 Intune 永远无法生成、缓存或存储私钥，这有助于保护移动设备的安全。

下图显示 Intune 和 ConfigMgr 如何使用 NDES 向使用 SCEP 的移动设备提供安全证书预配：

![保护证书预配的安全](./media/MDM_Figure_07.png)

**保护证书预配的安全**

1. 在 Intune 服务上创建了包括 SCEP 注册证书属性的策略。
2. Intune 将该策略转换为平台移动设备管理协议（比如 Windows 10 和 Windows 8.1 的 OMA-DM）并将其发送至设备
3. 移动设备接收该策略并从 NDES 启动注册请求
4. NDES 将该请求转发至 ConfigMgr
5. ConfigMgr 比较 SCEP 请求的请求属性以进行身份验证匹配，并将确认发送回 NDES。
6. NDES 将证书颁发请求发送至 CA，然后后者将相应证书发送给 NDES 角色。
7. NDES 角色将该证书发送到设备。

根据你对任务 3 中的问题的回答，你应该能够确定想要在移动设备管理解决方案中如何管理证书。 Office 365 的 MDM 当前不支持管理移动设备的证书配置文件。 

以下列表将帮助你了解 Intune 和混合 Intune 与 ConfigMgr 部署方案的证书配置文件管理的优缺点：

## Intune（独立版）

**优点**

- 支持所有主要的移动设备操作系统（Android、iOS、Windows 10、Windows 8.x 以及 Windows Phone）上的证书配置文件
- 平台支持简单证书注册协议 (SCEP)
- 证书配置文件可自动配置移动设备，以便可以在无需手动安装证书或使用未经批准的安全过程的情况下访问公司资源。
- 在设备退出管理、被选择性擦除或被阻止进入管理层次结构时，证书会自动撤销

**缺点**

- 若要使用证书配置文件，一些现有的本地基础结构必须存在。 你必须通过 Intune 集成以下本地基础结构：
 - 运行网络设备注册服务的服务器
 - 企业证书颁发机构
 - 安装在运行 NDES 的服务器上的 Intune NDES 连接器

## Office 365 的 MDM

- Office 365 的 MDM 中不提供对证书配置文件的支持。

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 除了 Intune 独立版的所有优点外，还包括以下优点：
 - 还支持管理非移动设备的证书

**缺点**

- 若要使用证书配置文件，一些现有的本地基础结构必须存在。 
- 你必须通过 Intune 集成以下本地基础结构：
 - 运行网络设备注册服务的服务器
 - 企业证书颁发机构
 - 安装在运行 NDES 的服务器上的 Intune NDES 连接器

有关移动设备证书管理选项的详细信息，请参阅 Intune 中的[启用证书配置文件](/Intune/deploy-use/secure-resource-access-with-certificate-profiles)，并将这些要求和过程与 System Center 2012 R2 Configuration Manager 中的[启用证书配置文件](https://technet.microsoft.com/library/dn261202.aspx)的要求和过程进行比较。


<!--HONumber=Jul16_HO2-->


