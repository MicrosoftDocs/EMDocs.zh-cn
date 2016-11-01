---
title: "使用分类、标记和保护来保护数据 | Azure 信息保护"
description: "此方案描述如何使用企业移动性 + 安全性，通过采用 Microsoft Azure 信息保护功能分类、标记和保护数据。"
author: yuridio
manager: swadhwa
ms.date: 10/18/2016
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 65409d5c-4f1b-4026-86e9-e65e1c4fe2b4
translationtype: Human Translation
ms.sourcegitcommit: eebc6bd4fa3bbe0f600b5309489817f615560243
ms.openlocfilehash: 1447ae5bf5662781571b3f6417e25d21cbc24397


---

# 使用分类、标记和保护来保护数据 

现今，已实现从多台设备跨组织边界进行信息共享。  务必确保在此过程中不会泄露重要的公司数据，同时保证用户可以安全地共享重要内容以开展工作。 随着外包等趋势的出现，可能需要与承包商和供应商共享公司机密数据。 由于并非所有内容都需要相同保护，公司面临识别需要和不需要保护的数据的难题。

继续阅读以了解有关企业移动性 + 安全性如何帮助处理这种情况的详细信息。

## 企业移动性 + 安全性可提供哪些帮助？
 
企业移动性 + 安全性 (EMS) 是唯一一个不仅保护设备自身上的公司数据，另外还通过标识、设备、应用和数据四重保护措施来提供保护的综合性云解决方案。 EMS 可帮助解决移动优先、云优先世界中的其中一个重大难题，即如何随时向员工传送安全数据。 使用 EMS，可以让员工在组织内外安全地进行协作。 EMS 允许 IT 管理员利用 Azure 信息保护帮助保护文件级的公司数据。 通过使用此功能，用户可以确信，无论数据存储的位置、共享的对象、处于静止状态还是在传输中，都会始终得到保护。 

## 建议的解决方案

通过 Azure 信息保护，组织可以在创建或修改数据时分类、标记和保护数据。 使用 Azure 信息保护，用户可以：

- 根据机密性手动或自动地分类数据和添加标签
- 通过加密、身份验证和使用权限保护数据
- 为最终用户启用直观、非侵入式体验

组织也有权访问详细跟踪和报告，可以查看共享数据所发生的状况，从而更好地管理数据。 下图概括了信息保护生命周期：

![信息保护生命周期](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig1.png)

观看此简短视频，快速了解 Azure 信息保护如何简化分类、标记和保护信息（即使信息已不在组织内）。

<iframe src="https://channel9.msdn.com/Shows/Mechanics/An-Introduction-to-Microsoft-Azure-Information-Protection/player" width="560" height="315" allowFullScreen frameBorder="0"></iframe>

## 实现本解决方案的方式

请遵循以下步骤使用 Azure 信息保护实现数据分类、标记和保护：

- 步骤 1：准备数据分类和保护
- 步骤 2：配置信息保护策略和标签
- 步骤 3：实现基于内容的自动分类
- 步骤 4：为自动和建议分类配置条件

## 如何通过 Azure 信息保护使用分类、标记和保护来保护数据

公司需要识别哪些数据需要保护以及哪些数据不需要相同级别的保护。 以下步骤将介绍 IT 实现 Azure 信息保护所必须执行的核心任务。

### 步骤 1：准备文档保护和内容分类

实现此解决方案之前，请查看 [Azure 信息保护要求](requirements-azure-infoprotect.md)并确保已激活 Azure 权限管理。 如已激活，则应在 Azure 门户中看到以下屏幕：

![Azure 门户](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig2.png)

激活 Azure 权限管理后，便可以使用此信息保护解决方案所支持的应用程序和服务保护重要数据。 还可以管理和监视组织所拥有的受保护文件和电子邮件。 必须先激活 Azure 权限管理才能在 Office、SharePoint 和 Exchange 中使用权限管理功能保护敏感或机密文件。

### 步骤 2：配置信息保护策略和标签

计划实现信息保护策略和标签时，请使用以下指南：

- 根据机密性分类数据
- 首先分类机密性最高的数据
- IT 可以设置自动规则；用户可以补充规则 
- 关联可视标记和保护等操作

下图演示了如何实现此操作：

![分类](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig3.png)

Azure 信息保护附带默认标签，但是你可以[自定义](configure-policy-new-label.md)并创建用户可在信息保护栏中看到的自己的标签或子标签。 

> [!IMPORTANT] 
> 标签是写入文档的元数据。 标签以明文形式呈现，以便 DLP 引擎等其他系统可以读取。

在以下示例中，你可以看到在“机密”标签下创建的自定义子标签：

![Label](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig4.png)

在定义使用（默认或自定义）标签的方式后，[配置标签以应用权限管理保护](configure-policy-protection.md#to-configure-a-label-to-apply-rights-management-protection)。 

### 步骤 3：实现基于内容的自动分类

通过 Azure 信息保护，将数据分类和保护控件集成到 Office 和其他常见应用程序。 此集成提供简单的单击选项以保护用户处理的数据。 在 Azure 门户中，可以将预定义的模式（如“信用卡号”或“美国社会保障号”）用作自动分类的条件。 或者，可以使用文本模式和正则表达式来定义自定义字符串或模式。

配置标签的条件时，可以自动将标签分配到文档/电子邮件，或者也可以提示用户选择建议的标签。 有关如何执行此配置的详细信息，请阅读[如何配置 Azure 信息保护的自动和建议分类的条件](configure-policy-classification.md)。


### 步骤 4：为自动和建议分类配置条件

IT 管理员可以设置策略，以自动对数据应用分类和保护。 还可以根据所处理的内容设置策略，并且可以配置策略以提示用户选择建议的分类。 内置条件的列表为：

- SWIFT 代码
- 信用卡号
- ABA 路由号码
- 美国身份证号 (SSN)
- 国际银行帐号 (IBAN)

有关这种实现的更多详细信息，请阅读[有关内置条件的信息](configure-policy-classification.md#information-about-the-built-in-conditions)。



<!--HONumber=Oct16_HO3-->


