---
title: 用自己的密钥加密 Cloud App Security 静态数据
description: 本文介绍如何使用自己的密钥来加密存储在 Cloud App Security 中的静态数据。
author: shsagir
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: conceptual
ms.date: 09/24/2020
ms.collection: M365-security-compliance
ms.openlocfilehash: 5fee2fb64d11d624a14fafde8b7883ad72404e60
ms.sourcegitcommit: c4d433c095ec8bc733daa06f5544d4b04e0323d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91214851"
---
# <a name="encrypt-cloud-app-security-data-at-rest-with-your-own-key-byok"></a>用自己的密钥加密 Cloud App Security 静态数据 (BYOK) 

适用范围：*Microsoft Cloud App Security*

本文介绍如何将 Cloud App Security 配置为使用自己的密钥来加密它收集的数据，而将其存放在一起。 如果你正在寻找有关将加密应用于存储在云应用中的数据的文档，请参阅 [Azure 信息保护集成](/cloud-app-security/azip-integration.md)。

Cloud App Security 将认真对待你的安全和隐私。 因此，Cloud App Security 开始收集数据后，它将使用自己的托管密钥，根据我们的 [数据安全和隐私](/cloud-app-security/cas-compliance-trust.md) 策略来保护你的数据。 此外，Cloud App Security 允许你使用自己的 Azure Key Vault 密钥对数据进行加密，从而进一步保护静态数据。

> [!IMPORTANT]
> 如果访问 Azure Key Vault 密钥时出现问题，Cloud App Security 将无法加密数据，租户将在一小时内锁定。 当租户锁定时，对其的所有访问都将被阻止，直到解决该问题。 再次访问密钥后，将还原对你的租户的完全访问权限。

## <a name="prerequisites"></a>先决条件

必须在租户的 Azure Active Directory 中注册 **MICROSOFT CLOUD APP SECURITY BYOK** 应用， (与) 租户关联的 Azure AD Cloud App Security。

### <a name="to-register-the-app"></a>注册应用程序

1. 安装 [图形 Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2)。

1. 打开 PowerShell 终端并运行以下命令：

    ``` Powershell
    Connect-AzureAD
    New-AzureADServicePrincipal -AppId 6a12de16-95c8-4e42-a451-7dbbc34634cd
    Set-AzureADServicePrincipal -ObjectId <object_id> -AccountEnabled true
    ```

    其中 *<object_id>* 是上一个命令 () 返回的对象 id `New-AzureADServicePrincipal` 。

> [!NOTE]
>
> - Cloud App Security 为所有新租户加密静态数据。
> - 驻留在 Cloud App Security 超过48小时的任何数据都将被加密。

## <a name="deploy-your-azure-key-vault-key"></a>部署 Azure Key Vault 密钥

1. 创建启用**软删除**和**清除保护**选项的[新 Key Vault](/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key-vault) 。

1. 创建访问策略，填写以下信息，然后单击 " **添加**"。
    1. 单击 " **密钥权限** "，然后从下拉菜单中选择以下权限：

        | 部分 | 所需的权限 |
        | --- | --- |
        | 密钥管理操作 | -列表 |
        | 加密操作 | -换行密钥<br />-解包密钥 |

        ![显示密钥权限选择的屏幕截图](media/cloud-app-security-byok/byok-kv-access-policy-key-perms.PNG)

    2. 在 " **选择主体**" 下，选择 **Microsoft Cloud App Security-BYOK**"。

        ![显示 "添加访问策略" 页的屏幕截图](media/cloud-app-security-byok/byok-kv-add-access-policy.PNG)

    3. 单击“ **保存**”。

1. 创建 [新的 RSA 密钥](/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key)，执行以下操作，然后单击 " **添加**"。

    > [!NOTE]
    > 仅支持 RSA 密钥。

    1. 在 " **允许的操作**" 下，选择以下选项：

        - 环绕键
        - 解包密钥

    2. 复制 **密钥标识符** URI，稍后需要用到它。

    ![显示密钥设置页的屏幕截图](media/cloud-app-security-byok/byok-kv-key-perms.PNG)

1. （可选）如果对选定的网络使用防火墙，请配置以下防火墙设置以授予 Cloud App Security 对指定密钥的访问权限，然后单击 " **保存**"：
    1. 请确保未选择任何虚拟网络。
    1. 添加以下 IP 地址：
        - 13.66.200.132
        - 23.100.71.251
        - 40.78.82.214
        - 51.105.4.145
        - 52.166.166.111
    1. 选择 " **允许受信任的 Microsoft 服务跳过此防火墙**"。

    ![显示防火墙配置的屏幕截图](media/cloud-app-security-byok/byok-kv-firewall.PNG)

## <a name="enable-data-encryption-in-cloud-app-security"></a>在 Cloud App Security 中启用数据加密

启用数据加密时，Cloud App Security 立即使用 Azure Key Vault 密钥来加密静态数据。 由于密钥是加密过程所必需的，因此必须确保指定的 Key Vault 和密钥在任何时候都可以访问。

### <a name="to-enable-data-encryption"></a>启用数据加密

1. 在 Cloud App Security 的菜单栏中，单击 "设置" "齿轮 ![ 设置" 图标， ](media/cloud-app-security-byok/byok-kv-settings-icon.png) 然后选择 " **设置**"。

1. 选择 " **数据加密** " 选项卡。

1. 单击 " **启用数据加密**"。

1. 在 " **Azure Key Vault 密钥 URI** " 框中，粘贴前面复制的密钥标识符 URI 值。

    > [!NOTE]
    > Cloud App Security 始终使用最新的密钥版本，而不考虑 URI 指定的密钥版本。

1. URI 验证完成后，单击 " **启用**"。

> [!NOTE]
> 禁用数据加密时，Cloud App Security 会删除静态数据中的加密。 但是，你的数据将保留 Cloud App Security 的托管密钥。
>
> **禁用数据加密：** 中转到 " **数据加密** " 选项卡，然后单击 " **禁用数据加密**"。

## <a name="key-roll-handling"></a>密钥滚动处理

每次创建为数据加密配置的密钥的新版本时，Cloud App Security 会自动滚动到最新版本的密钥。

## <a name="how-to-handle-data-encryption-failures"></a>如何处理数据加密失败

如果访问 Azure Key Vault 密钥时出现问题，Cloud App Security 将无法加密数据，租户将在一小时内锁定。 当租户锁定时，对其的所有访问都将被阻止，直到解决该问题。 再次访问密钥后，将还原对你的租户的完全访问权限。 有关处理数据加密失败的信息，请参阅 [用自己的密钥对数据加密进行故障排除](ems-cloud-app-security-govt-service-byok-troubleshoot.md)。
