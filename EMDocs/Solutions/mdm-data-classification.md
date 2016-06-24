---
# required metadata

title: 数据分类
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: f3486381-66d5-469a-93a3-013eaaa17c07

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 数据分类

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

大多数公司已经采用了[数据分类策略](http://blogs.microsoft.com/cybertrust/2014/01/28/the-importance-of-data-classification/)，你将需要了解部署移动设备管理解决方案将如何影响此策略。 如果你的公司没有当前数据分类策略，你应该在规划移动设备管理解决方案时配合引入此功能。 某些组织使用 [Active Directory Rights Management Services (ADRMS)](https://technet.microsoft.com/windowsserver/dd448611.aspx) 在文件服务器级别上执行本地数据分类。 某些公司使用的另一个工具是 [Microsoft 数据分类工具包](http://www.microsoft.com/download/details.aspx?id=27123)，用于帮助组织标识、分类和保护其文件服务器上的数据。 

Office 365 提供了一些电子邮件的自动数据分类，可帮助找出应受到保护的敏感信息。 Office 365 使用传输规则（合并到邮件流处理中）来检测敏感信息。 然后 [DLP 功能](http://blogs.office.com/2013/10/28/office-365-compliance-controls-data-loss-prevention/)将通过关键字匹配、字典匹配、正则表达式计算、验证信用卡号上的校验和等内部功能以及其他内容检查来执行深度内容分析，从而检测出邮件正文或附件内的特定内容类型。 

Intune 和 ConfigMgr 未内置数据分类，因此它们依靠使用 Azure RMS 的基于云的分类或使用 ADRMS 的本地分类。 另一个选项是使用[企业移动性套件 (EMS)](http://www.microsoft.com/server-cloud/enterprise-mobility/overview.aspx) 作为你的 MDM 解决方案。 借助 EMS，你将可以访问 [Azure AD Premium](https://msdn.microsoft.com/library/azure/dn532272.aspx) 和 [Azure RMS](https://technet.microsoft.com/library/jj585026.aspx)，二者可用于为数据分类。 使用 Azure RMS 的数据分类可以与混合环境中的本地管理解决方案集成。 

Intune 通过使用合规性策略使 IT 遵从这些策略，这些策略是设备必须遵从的多个规则和设置的集合，以便被条件访问策略视为合规。 也可使用合规性策略来监视和修正与取决于条件访问的设备的合规性问题。 有关详细信息，请参阅[为 Microsoft Intune 管理设备相容性策略](/intune/deploy/introduction-to-device-compliance-policies-in-microsoft-intune)。

使用下表作为参考协助你选择最符合组织的*数据分类*要求的 MDM 选项。

## Intune（独立版）

**优点**

- 不可用

**缺点**

- 不可用

## Office 365 的 MDM

**优点**

- Exchange 传输规则可用于检测敏感信息
- 在合规性中心利用[数据丢失防护 (DLP)](https://technet.microsoft.com/library/ms.o365.cc.DLPLandingPage.aspx)策略来标识跨多个位置的敏感信息

**缺点**

- 文件本身不执行数据分类。 在文件位于移动设备上后，可以不受限制地使用它。

## 混合版（带 ConfigMgr 的 Intune）

**优点**

- 不可用

**缺点**

- 不可用

## 公司移动套件

**优点**

- 利用 Azure RMS 来执行数据分类
- Azure EMS 订阅包含在 RMS 之中
- 对于数据分类，不需要本地基础结构
- 可与现有本地 AD RMS 解决方案集成
- 文件自带保护，这意味着即使该文件保存在不同的位置，它仍然保留其分类。

**缺点**

- 不适用于不采用基于云的解决方案的客户


<!--HONumber=Apr16_HO2-->


