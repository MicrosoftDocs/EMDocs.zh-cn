---
title: "身份验证和授权"
description: "本文介绍一系列移动设备管理方案中应考虑的有关身份验证和授权的设计注意事项。"
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 31b98333-5a3d-49ba-a25e-66447df68035
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: ff3b086f2ad076776e7cff918ef4bb26161427fd


---

# <a name="authentication-and-authorization"></a>身份验证和授权

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

在你可以正确地保护公司数据前，你必须标识你的用户的身份，然后才能验证是否已授权他们访问他们所请求的资源。 已有本地 Active Directory 服务的组织应将其用于对移动用户进行身份验证和授权。 所有 Microsoft 移动设备管理解决方案都可以使用现有 Active Directory 基础结构来执行此操作。

有关身份验证和授权的另一个决策点是目录服务所在的位置。 尽管大多数组织都有本地 Active Directory 服务，但某些组织可能正在考虑使用基于云的目录服务（例如 [Azure AD](http://azure.microsoft.com/documentation/articles/active-directory-whatis/)）扩展其本地目录服务。

ConfigMgr 允许集成 [Microsoft Passport for Work](https://technet.microsoft.com/library/mt488797.aspx)，它是在运行 Windows 10 的设备上使用 Active Directory 或 Azure Active Directory 帐户取代密码、智能卡或虚拟智能卡进行登录的一种替代方法。对于混合解决方案，将两个目录集成在一起是一个很好的选择，以便可以充分利用 Azure AD 功能，比如：

- **自助服务组管理**：允许用户创建组、请求对其他组的访问权限、委派组所有权，以便其他组可以批准请求和维护他们的组成员资格。
- **99.9% 的公司 SLA**：我们保证 Azure Active Directory 高级服务至少有 99.9% 的可用性。
- **密码重置回写**：可将自助服务密码重置回写到本地目录。

在 [Azure Active Directory](https://msdn.microsoft.com/library/azure/dn532272.aspx) 中阅读有关不同选项和功能的详细信息。
要求两种类型的身份验证（多因素身份验证或 MFA）是在规划移动设备管理解决方案时应考虑包含的另一个策略。 Intune 可[将目录服务与多因素身份验证 (MFA) 集成](https://technet.microsoft.com/library/dn889751.aspx)，这将为身份验证过程添加另一层安全性。

如果你的组织具有的本地 IT 基础结构包括具有 Active Directory 联合身份验证服务 (AD FS) 的 Active Directory 域，则可以在联合服务器上配置 MFA，然后启用 MFA 以便在 Intune 中注册。 如果你在联合身份验证服务器上配置 MFA，但你未启用 MFA 以在 Intune 中注册，则用户将需要在其每次从任何设备访问公司资源时使用 MFA。

你还可以使用 Azure AD MFA 在每次用户访问公司资源时要求 MFA，并且可以根据每个用户启用此要求。 Azure AD MFA 是不需要任何本地 IT 基础结构的云服务。

使用下表作为参考协助你选择最符合组织的身份验证和授权要求的 MDM 选项。

## <a name="intune-standalone"></a>Intune（独立版）

**优点**

- 可以使用本地目录服务（例如 Active Directory）进行身份验证
- 可以使用基于云的目录服务（例如 Azure AD）进行身份验证
- 可以与多因素身份验证集成

**缺点**

- 当你购买 Intune 订阅时，不包含 Azure AD 云服务

## <a name="mdm-for-office-365"></a>Office 365 的 MDM

**优点**

- 可以使用本地目录（例如 Active Directory）进行身份验证
- 可以使用基于云的目录（例如 Azure AD）进行身份验证
- 可以与多因素身份验证集成
- 可以利用合规性中心来使用基于角色的访问控制 (RBAC) 权限模型

**缺点**

- 当你购买 Office 365 订阅时，不包含 Azure AD 云服务

## <a name="hybrid-intune-with-configmgr"></a>混合版（带 ConfigMgr 的 Intune）

**优点**

- 可以使用本地目录（例如 Active Directory）进行身份验证
- 可以使用基于云的目录（例如 Azure AD）进行身份验证

**缺点**

- 当你购买 Intune 订阅时，不包含 Azure AD 云服务

## <a name="enterprise-mobility--security"></a>企业移动性 + 安全性

**优点**

- 利用 Azure AD Premium 提供访问控制
- Azure AD Premium 许可证已包含在 EMS 中
- 不需要本地目录服务
- 可以与本地 Active Directory 服务同步
- MFA 在本地适用于 EMS

**缺点**

- 不适用于不采用基于云的解决方案的客户



<!--HONumber=Nov16_HO4-->


