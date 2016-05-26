---
# required metadata

title: 设计注意事项
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 639dfd46-33ea-4cfd-918d-f3d8e57645ed

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 设计注意事项

了解本文档中“构想 BYOD 基础结构解决方案”中详细介绍的要求之后，你可以选择适当的产品和技术来实现 BYOD 基础结构设计的要求。 下表列出了可用于实现 BYOD 基础架构解决方案的 Microsoft 产品、技术和服务。

本指南中所述的用于 BYOD 基础架构解决方案的 Microsoft 产品、技术和服务分别为：

## 用户和设备

- Windows Server 2012 R2
- Windows 10
- 工作区加入
- 设备注册服务
- 设备注册
- Wi-Fi 配置文件
- Company Portal
- HTTPS 协议

## 数据访问和保护

- Windows Server 2012 R2
- Active Directory 域服务 (AD DS)
- Azure Active Directory (Azure AD)
- Azure Multi-Factor Authentication (Azure MFA)
- Active Directory 联合身份验证服务 (AD FS)
- 动态访问控制
- Microsoft 权限管理服务
- Azure Rights Management 
- SMB 加密
- 单一登录(SSO)
- 工作文件夹
- Web 应用程序代理 (WAP)

## Management

- Microsoft Intune
- 设备管理策略
- 统一的管理基础结构
- 选择性擦除
- 软件分发
- 分发点使用报告和管理
- System Center 2012 R2 Configuration Manager

## 应用

- Web 应用程序代理
- 自动触发器 VPN
- RemoteApp
- 会话阴影
- 快速重新连接
- 重复数据删除存储
- 安全开发生命周期 (SDL)
- Active Directory 联合身份验证服务 (AD FS)
- HTTPS 协议

以下各节概述了设计过程，但正如本文档的“构想 BYOD 基础结构解决方案”中提到的，设计和要求定义过程在完成之前都将进行迭代。
文档的其余部分涉及到设计注意事项以及上表中列出的产品、技术和服务。 在使用多种 Microsoft 产品、技术和服务来处理不同的设计注意事项时，将讨论它们之间的权衡。

用于支持 BYOD 的基础结构设计将总结已在本文出现的问题的解答，以及可供你使用的技术功能和选项。 本文档讨论的设计使用基于 Microsoft 的技术。 但是，设计选项和注意事项可应用于任何用来实现 BYOD 模型的基础结构。




<!--HONumber=Apr16_HO4-->


