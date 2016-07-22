---
title: "电子邮件管理选项"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 9b89da63-039f-4831-b204-28c0681478fe
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ef523f44cd9d51e59fc8d94bbb8d7aa388120945
ms.openlocfilehash: 13749f7100df8a157ae8204641442aadfa3c7f16


---

# 电子邮件管理选项

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

通常，实现移动设备管理解决方案的主要是为了提供从移动设备访问企业电子邮件的托管权限。 例如，在 Office 365 的 MDM中，你可以创建提供托管在 Exchange Online 中的电子邮件邮箱的基本托管访问权限或（在 iOS 和 Android 上）通过 Office 应用提供访问权限的[安全策略](https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx)。 在设备允许连接到用户邮箱前，该策略强制执行基本移动设备合规性设置，例如要求设备密码和设备加密。

在 Intune、混合 Intune 和 ConfigMgr部署中配置电子邮件管理选项时应遵循类似的过程。 主要区别在于你可以比在 Office 365 的 MDM 中实现更高级的电子邮件管理选项。 例如，使用 Intune 独立版可以配置条件电子邮件访问以允许访问托管在 Exchange Online 和本地 Exchange 上的邮箱，还可以配置自定义的电子邮件配置文件。 Intune 通过使用配置和合规性策略启用这些功能。  混合 Intune 和 ConfigMgr 部署也支持条件电子邮件访问，但仅限于托管在 Exchange Online 上的邮箱

在下图 6 所示的方案中，用户已在 Intune 中注册设备，现在正尝试使用 Office 365 或本地 Exchange 访问其企业电子邮件。 根据公司 IT 管理员定义的设置，Intune 运行策略验证过程。 在此方案中，如果设备已加密、密码已设置并且设备没有越狱或没有获取根权限，将授予用户访问权限。 如果用户尝试访问企业电子邮件但其设备尚未注册，或与 IT 管理员定义的设置不兼容，他将收到一封电子邮件，说明访问受阻的原因以及如何解决该问题的步骤。 

![条件性访问](./media/MDM_Figure_06.png)

**条件性访问**

对步骤 1 中的问题的回答可以帮助你确定想要如何使用移动设备管理解决方案管理设备。 下表列出了每个 MDM 解决方案的电子邮件管理的优缺点。

## Intune（独立版）

**优点**

- 支持所有主要的移动设备操作系统（Android、iOS、Windows 10、Windows 8.x 以及 Windows Phone）的电子邮件管理
- 可以通过与 Exchange ActiveSync 集成来利用本机移动设备电子邮件应用程序
- 通过服务间连接器与 Exchange Online 集成允许在 Intune 和 Office 365 之间进行跨平台监视和报告
- 支持配置用于管理移动设备上基于 Exchange ActiveSync 的设置的电子邮件配置文件
- 资源的有条件电子邮件访问权限

**缺点**

- 基于 Android 的移动设备不支持电子邮件配置文件

## Office 365 的 MDM

**优点**

- 允许 Exchange ActiveSync 支持密码、加密和 root 设备合规性
- 在授予 Office 和 OneDrive for Business 应用（iOS 和 Android）的访问权限前，允许执行设备管理策略和所需设备注册
- 资源的有条件电子邮件访问权限

**缺点**

- 不支持某些高级电子邮件管理选项 
- 不支持部署电子邮件配置文件（iOS 除外）

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 适用于混合连接 Exchange Online 的 Intune 本地连接器
- 与 Exchange ActiveSync 集成（已强制执行最严格的策略设置）
- 电子邮件配置文件
- 将电子邮件访问权限限制到 Exchange Online 的有条件访问权限
- 定义设备为允许访问服务而必须遵守的规则和设置的合规性策略
- 每项服务的条件访问策略，定义安全组、Intune 组或如何管理未注册设备的规则

**缺点**

- 电子邮件的托管访问仅适用于托管在 Exchange Online 上的邮箱，而非托管在本地 Exchange 上的邮箱
- 如果你为 Exchange Online 和本地 Exchange 启用了条件访问，则不应配置服务间的连接器

查看以下内容，了解有关移动设备电子邮件配置管理选项的详细信息：

- Intune：如何[启用电子邮件配置文件](/Intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)和[有条件的电子邮件访问](/Intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
- ConfigMgr：启用[电子邮件配置文件](https://technet.microsoft.com/library/dn554227.aspx)和[有条件电子邮件访问](https://technet.microsoft.com/library/dn919655.aspx)
- Office 365 的 MDM：[移动设备管理功能](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx)


<!--HONumber=Jul16_HO3-->


