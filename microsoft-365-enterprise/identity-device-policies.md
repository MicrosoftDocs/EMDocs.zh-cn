---
title: "标识和设备访问策略 - Microsoft 365 企业版 | Microsoft Docs"
description: "描述针对标识和设备访问策略和配置的 Microsoft 建议所需的累积策略设置。"
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 8c8be64f8519ab3d19e9a770302967f5690f82d3
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2017
---
# <a name="exchange-online-and-sharepoint-online-policy-settings-overview"></a>Exchange Online 和 SharePoint Online 策略设置概述

## <a name="applicable-to-all-sensitivity-levels"></a>适用于所有敏感级别
Intune（需要一个兼容或已加入域的设备）

用于 Exchange Online 的 Intune MAM

## <a name="baseline"></a>Baseline
要创建新的条件访问策略，请使用管理员凭据登录到 Microsoft Azure 门户。 然后导航到“Azure Active Directory”>“安全”>“条件访问”。

### <a name="conditional-access-policy"></a>条件性访问策略
Azure 条件访问政策需要对中等及以上级别的风险进行 MFA

Intune（需要一个兼容或已加入域的设备）

用于 Exchange Online 的 Intune MAM



## <a name="sensitive"></a>敏感
条件访问较低及以上风险需要进行 MFA



## <a name="highly-regulated"></a>高度管控
MFA 所需的条件访问策略设置
