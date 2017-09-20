---
title: "使用 Microsoft Intune 部署 Office 365 专业增强版 - Microsoft 365 企业版 | Microsoft Docs"
description: "描述如何使用 Microsoft Intune 部署 Microsoft Office 365 专业增强版。"
author: jeffgilb
manager: femila
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/10/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: e631ca9282fc937279c7e2d639f1ecf509ceeab5
ms.sourcegitcommit: a5900174df584bee2f94086668cb0eff53bd5ed0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2017
---
# <a name="deploy-office-365-proplus-with-microsoft-intune"></a>使用 Microsoft Intune 部署 Office 365 专业增强版
Microsoft 365 企业版是一套现代工作区解决方案，让每个人都能发挥创造力、并安全地协同工作。 Microsoft 365 企业版解决方案是企业移动性 + 安全性 (EMS)、Office 365 和 Windows 10 团队之间紧密协作的成果。 这种协作产生了创新的解决方案，例如，可以使用 Intune 将 Office 365 专业增强版应用程序部署到 Windows 10 设备。 

现在执行以下这些操作比以往更容易：选择特定的 Office 365 专业增强版应用（使用即点即用），将其部署到运行 Windows 10 创意者更新的已注册设备，以及通过 Azure 上新的 Intune 门户查看部署指标。 而且还能与 Windows AutoPilot 方便地协同工作，通过在全新安装体验 (OOBE) 期间仅提供公司凭据使员工的设备准备就绪，而 Azure AD 和 Intune 在后台同时运行以注册设备、部署所需配置，现在还可安装 Office 365 专业增强版应用。

![简化 Windows 10 管理并降低 EMS 的总拥有成本](./media/deploy-office-proplus-intune/windows-10-management-ems.png)

可以[在此处下载该信息图](https://gallery.technet.microsoft.com/Infographic-Simplify-37e77674)。

## <a name="deploy-office-365-proplus-with-intune"></a>使用 Intune 部署 Office 365 专业增强版 
了解如何使用 Intune 配置 Office 365 专业增强版部署。

通过新的 Intune 门户，可轻松添加和自定义 Office 365 专业增强版部署。 选择 Office 365 专业增强版套件 (Windows 10) 应用类型后，可以采取三个简单步骤自定义 Office 应用的部署。

首先，选择想要在最终用户设备上安装的应用程序：

![选择要部署的应用程序](./media/deploy-office-proplus-intune/Configure-App-Suite.png)

接下来，配置应用程序套件的信息。 例如，对于要在 Intune 公司门户中显示的应用，建议在此套件中添加简短说明：

![配置应用程序套件信息](./media/deploy-office-proplus-intune/App-Suite-Information.png)

最后，配置几个安装设置，如系统体系结构或更新通道：

![配置安装设置](./media/deploy-office-proplus-intune/App-Suite-Settings.png)

在可用情况下，最终用户可以通过 Intune 公司门户安装 Office 应用。 否则，用户只能进行无提示安装。 用户在设备上安装 Office 后，即可登录、激活产品并体验最新功能，因为 [Office 通过服务自动保持更新](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。

> [!NOTE]
> 目前，只有未安装 Office 现有版本的设备才支持这种形式的 Office 365 专业增强版部署。 对于已安装 Office 现有版本的设备，建议先删除 Office 的所有版本，然后再注册。 我们正在与 Windows 和 Office 团队合作，致力于未来的增强功能，以支持带有现有 Office 部署的设备。

## <a name="learn-more"></a>了解详细信息
有关分步说明的详细信息，请参阅[使用 Intune 部署适用于 Windows 10 的 Office 365](https://docs.microsoft.com/intune/apps-add-office365)。