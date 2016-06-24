---
# required metadata

title: 移动设备保护加强计划
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: a4504456-a241-4380-ab92-3bc14c91347c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 移动设备保护加强计划

>[!NOTE]
>本主题是更大的设计注意事项指南的一部分。 如果你希望从指南的开头开始，请查看[主要主题](mdm-design-considerations-guide.md)。 若要获取此完整指南的可下载副本，请访问 [TechNet 库](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)。

虽然本地和远程用户可通过在其移动设备上访问公司资源来提高工作效率，但允许他们这样做也会增加安全威胁，你将需要缓解这些威胁来帮助保护你的公司数据和维护用户隐私。 你的公司可能对如何平衡这些需求有特定的要求。 例如，合规性规则可能因你的公司所经营的行业而异，这可能导致不同的设计决策。
 
但是，需要浏览和遵循移动设备管理中安全性的某些常规方面，而无需考虑该行业。 这些如下图中所示。

![MDM 平台的核心安全功能](./media/MDM_Figure_08.png)

## MDM 解决方案中的安全功能

下图显示任何 MDM 解决方案中所需的核心安全功能。 要考虑的关键领域如下所示：

1. 移动设备级别的数据保护的注意事项：
    - 数据加密
    - 数据分类
    - 客户端隐私
    - 容器化
    - 策略强制
    - 相容性策略
    - 强化
2. 传输过程中的数据保护的注意事项：
    - 数据加密
    - 身份验证
    - 授权
3. 在本地组织中处于静态时的数据保护的注意事项：
    - 数据加密
    - 身份验证
    - 授权
4. 在云中处于静态时的数据保护的注意事项：
    - 数据加密
    - 身份验证
    - 授权

下列部分描述的任务可以帮助你了解你的特定安全需求将如何影响关于业务要求的最佳 MDM 解决方案的决策。

## 关于此步骤

本指南此部分有 12 个步骤。 阅读这些部分的总时间大约为 36 分钟，你也可以跳到特定的部分。

- [收集数据保护要求](mdm-gather-data-protection-requirements.md)
- [指定隐私要求](mdm-specify-privacy-requirements.md)
- [指定访问要求](mdm-specify-your-access-requirements.md)
- [制定事件响应要求](mdm-develop-incident-response-requirements.md)
- [数据加密计划](mdm-data-encryption.md)
- [数据隔离计划](mdm-data-segregation.md)
- [强化移动设备](mdm-hardening-mobile-devices.md)
- [客户端隐私](mdm-client-privacy.md)
- [数据分类](mdm-data-classification.md)
- [身份验证和授权](mdm-authentication-authorization.md)
- [对资源的访问控制](mdm-access-control-resources.md)




<!--HONumber=Apr16_HO2-->


