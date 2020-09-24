---
title: 用自己的密钥对数据加密进行故障排除
description: 本文提供了一些问题列表，这些问题可阻止 Cloud App Security 访问用于加密静态收集数据的 Azure Key Vault 密钥。
keywords: ''
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 09/24/2020
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.openlocfilehash: ef46f49db6ef22c35326c5fda1a8349c934408d2
ms.sourcegitcommit: c4d433c095ec8bc733daa06f5544d4b04e0323d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91214852"
---
# <a name="troubleshooting-data-encryption-with-your-own-key"></a>用自己的密钥对数据加密进行故障排除

适用范围：*Microsoft Cloud App Security*

本文提供了一些问题列表，这些问题可阻止 Cloud App Security 访问用于加密静态收集数据的 Azure Key Vault 密钥。

> [!IMPORTANT]
> 如果访问 Azure Key Vault 密钥时出现问题，Cloud App Security 将无法加密数据，租户将在一小时内锁定。 当租户锁定时，对其的所有访问都将被阻止，直到解决该问题。 再次访问密钥后，将还原对你的租户的完全访问权限

## <a name="troubleshooting"></a>疑难解答

下表列出了可能会导致数据加密失败的情况，以及可以采取哪些措施来解决这些问题：

| 场景 | 操作 |
| --- | --- |
| <a name="missing-kv-key-permissions"></a>**缺少 Key Vault 或密钥权限** | 在 "所选 Key Vault 中，在" 访问策略 "下，确保选中了以下关键权限：<br />在**密钥管理操作**下<br />-列表<br />**加密操作**下<br />-换行密钥<br />-解包密钥<br /><br />对于所选的密钥，请确保使用的是 RSA 加密并且允许以下操作：<br />-换行密钥<br />-解包密钥<br /> |
| <a name="firewall-block"></a>**Azure Key Vault 防火墙阻止访问密钥** | 在 "所选 Key Vault 中，确保已为防火墙配置以下 IP 地址：<br />- 13.66.200.132<br />- 23.100.71.251<br />- 40.78.82.214<br />- 51.105.4.145<br />- 52.166.166.111 |
| <a name="key-not-enabled"></a>**未启用加密密钥** | 在选定的项的 "设置" 中，确保已启用该密钥。<br />![显示密钥启用选项的屏幕截图](media/cloud-app-security-byok/byok-kv-key-enabled.PNG) |
| <a name="key-not-active"></a>**加密密钥不处于活动状态** | 在选定的项的 "设置" 中，确保激活日期和时间早于当前日期和时间。<br />![显示密钥激活日期的屏幕截图](media/cloud-app-security-byok/byok-kv-key-activation-date.PNG) |
| <a name="key-expired"></a>**加密密钥已过期** | 在选定的项的 "设置" 中，确保未通过过期日期和时间。<br />![显示密钥到期日期的屏幕截图](media/cloud-app-security-byok/byok-kv-key-expiration-date.PNG) |
| <a name="key-not-found"></a>**找不到或已删除加密密钥** | 验证 Key Vault 中是否存在所选的项。 如果已删除密钥，请再次恢复并启用它。 如果已将该密钥移到另一个 Key Vault，请将其移回所选 Key Vault。 |

若遇到任何问题，可随时向我们寻求帮助。 若要获取帮助或支持以解决产品问题，请[打开支持票证](/cloud-app-security/support-and-ts.md)。
