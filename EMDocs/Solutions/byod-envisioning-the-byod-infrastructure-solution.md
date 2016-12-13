---
title: "构想 BYOD 基础架构解决方案"
description: "本文介绍基于设计过程中所做选择而得出的“自带设备办公”解决方案的定义。"
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ecb6271f-8f38-42bd-aae7-10ba5e17a5f1
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 7dbb0c9b1b2b3b29eb54ad8cdeee527d9d7f078f


---

#<a name="envisioning-the-byod-infrastructure-solution"></a>构想 BYOD 基础架构解决方案

在清晰地定义了要解决的 BYOD 问题之后，你可以开始定义此问题的解决方案，并定义解决方案的详细要求。

## <a name="solution-definition"></a>解决方案定义

若要解决以前发现的问题，并帮助组织鼓励用户自带设备办公，并使用它们访问公司数据，则公司必须从以设备为中心的 IT 方法转换为以人为中心的 IT 方法。 若要定义你自己的 BYOD 基础结构解决方案以达到以下目的，可以使用本指南中的设计注意事项：

- 使用户能够灵活地使用他们自己的设备来访问企业应用和数据。
- 管理从本地和云访问公司资源的设备。
- 通过使用加密和信息保护防止未经授权的本地访问，使 IT 部门能够保护存储在设备上的数据，并且能够在设备丢失或停用，或者员工离职时，通过 Internet 远程擦除公司数据。
- 当用户从本地和云访问资源时为其提供通用标识。
- 使 IT 部门能够管理多个标识，并使信息在不同的环境之间保持同步。
- 支持企业身份验证服务，例如多重身份验证和单一登录。
- 提供信息的安全性和符合性活动，例如符合性认证。

## <a name="solution-requirements"></a>解决方案要求

在允许用户自带设备访问公司的资源之前，必须先修改现有基础结构的技术功能。 此修改旨在了解此新模型的解决方案要求是否已存在，或者是否必须引入新的技术来解决该问题。 若要进行修改，则必须先针对环境定义大量的要求和约束。 一些要求和约束由功能的使用者定义；其他要求和约束由你的现有环境定义，包括现有的技术能力、服务、策略和过程。

确定要求、约束和设计以使用户能够从其托管的设备访问公司资源是一个关键的过程。 环境的初始要求和约束可能会引起初始设计无法满足所有初始要求，因而需要对初始要求和后续设计进行更改。 在最终确定要求和设计之前，在要求和解决方案设计的定义中进行多次迭代是必要的。 因此，你将会反复地浏览本指南。 你可能会发现，在该过程的前期作出的决策排除了在该过程后期中对你而言更可取的方法。

将你对以下各部分中的问题的答案生成一张完整的要求列表，使用户可以从他们的设备访问公司资源，这些设备可由 IT 部门托管，同时保护数据。 这些问题并非特定于供应商，它们可以应用于任何 BYOD 基础结构解决方案。

关于本指南中讲述的 BYOD 问题域将划分为子域的注意事项。 每个子域都将具有一个组件集合。 对于本指南中介绍的每个子域，你有一系列要求：

- [用户和设备要求](byod-user-device-reqs.md)
- [数据访问和保护要求](byod-data-access-protection-reqs.md)
- [管理要求](byod-management-reqs.md)
- [应用要求](byod-app-reqs.md)



<!--HONumber=Nov16_HO4-->


