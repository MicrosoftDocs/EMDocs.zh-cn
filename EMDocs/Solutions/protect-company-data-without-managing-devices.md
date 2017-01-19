---
title: "使用 Intune 在不管理设备的情况下保护公司数据 | Microsoft Docs"
description: "Microsoft Intune 中的 EMS 提供了创新的数据丢失防护功能。 通过此功能，可保护公司数据并保留员工熟悉的 Office 365 应用的出色用户体验，而无需管理其设备。"
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 12/15/2016
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b46877f3-cf32-4919-ba63-4df55cd2af32
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 83e901c3f5d9e6e35aea989de146e59ddc3354ef
ms.openlocfilehash: 19d2c610417667aec3346ac7d25d2bac95c7d8ba


---

# <a name="protect-company-data-without-managing-devices-with-intune"></a>使用 Intune 在不管理设备的情况下保护公司数据
我们生活在一个移动的世界，员工需要在其移动设备上移动访问公司数据和高效率工具。 由于其普及性和重要性，许多组织通过在保留出色的最终用户体验的同时防止数据从 Office 移动应用丢失，寻求对 Office 365 数据的进一步保护。 IT 需要保护对 Office 365 的访问，并防止公司数据从组织不拥有或管理的移动设备和应用丢失。 问题在于，IT 需要保护公司数据的安全，但许多员工对 IT 取得其个人设备的控制权有隐私方面的顾虑。

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>企业移动性 + 安全性 (EMS) 可提供什么帮助？

Microsoft Intune 中的 EMS 提供了创新的数据丢失防护功能。 通过此功能，可保护公司数据并保留员工熟悉的 Office 365 应用的出色用户体验。 无需用户注册其设备进行管理也可实现，这可显著增加自带设备办公计划成功的可能性以及 IT 策略的最终用户合规性。 你获取所需的控制，用户则享受他们所期望的新式体验。  由于可直接将 Microsoft Intune 用于 Azure Active Directory 和 Office 365 以管理对公司数据的访问并保护公司数据，所以无需安装和维护本地基础结构或通过其路由所有流量。

### <a name="recommended-solution"></a>建议的解决方案

Microsoft Intune 使组织能够在不要求员工注册到设备管理的情况下，提供对移动应用的访问并防止 Office 365 数据泄露。 如有需要，仍可完成设备管理 (MDM)，但现在不是必需。 Intune 强大的应用程序保护功能可帮助 IT 保护应用级别的公司数据，无需管理实际设备。 对于高度机密的数据，可通过 Azure 信息保护进一步将保护扩展到文件级别。 员工、供应商和合作伙伴可使用他们最喜欢的移动设备访问熟悉的高效率工具和公司数据，无需担心侵犯隐私的风险。 如果 IT 已采用了一个 MDM 解决方案，Intune 可添加高级 Office 365 访问控制数据丢失防护，无需将设备从当前 MDM 解决方案中注销后重新注册到 Intune MDM 中。

请观看此演示，了解如何使用不需要用户设备注册到 Intune MDM 的 Intune 创新性应用程序保护功能，防止数据从移动应用丢失（包括 O365 和内部业务线 (LOB) 应用）：

<iframe width="675" height="480"  src="https://www.youtube.com/embed/BcwgKmsAy18?list=TLGGQ9qBhVYxOZIxMzEyMjAxNg" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>实现本解决方案的方式

此解决方案的其余部分分为以下各节，展示如何使用 Intune 保护 Office 365 公司数据：

- **使用 Intune 移动应用保护策略保护应用数据**。 本部分介绍如何创建和部署 Microsoft Intune 应用程序保护策略，向非托管移动设备的用户提供数据丢失防护功能（如复制/粘贴/另存为/PIN/加密/选择性擦除/等）。

- **仅允许支持应用保护策略的移动应用访问 Office 365 服务**。 在此部分，将了解如何创建仅允许支持 Intune MAM 策略的移动应用访问 O365 服务（如 Exchange Online）的策略。

## <a name="protect-app-data-with-intune-mobile-app-protection-policies"></a>使用 Intune 移动应用保护策略保护应用数据

在非托管设备上保护应用数据时，部署应用的方式与在托管设备上的部署方式不同。 用户会在他们个人的 iOS 或 Android 设备上从公共应用商店下载 Office 365 应用，然后照常使用他们的工作帐户登录。

在 Azure 门户可轻松为 iOS 和 Android 设备创建用于这些应用的应用保护策略。 这类策略允许限制用户操作（如剪切、复制、粘贴和另存为）或者强制实施 PIN、要求加密以及选择性地从移动应用擦除公司数据。 将它们分配给用户时，应用保护策略将自动由 Intune 应用，并强制在个人和工作帐户与应用之间实施。 因为 Intune 与 Azure AD 和 Office 365 无缝集成，所以保护工作数据的同时，相同 Office 应用中的个人数据保持不变。

>[!NOTE]
>这类应用保护策略适用于 Intune 使用 [Windows 信息保护 (WIP) 策略](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune)作为移动设备管理的 Windows 10 计算机。

下面介绍了如何轻松选择要保护的应用、配置应用保护策略设置，并在登录 Azure 门户后将策略部署到最终用户的组：

>[!TIP]
>要查找 Intune 应用保护策略设置，只需使用 Intune 管理员凭据登录 [Azure 门户](https://portal.azure.com)，并在门户顶部的“搜索资源”框中搜索 **Intune 应用保护**即可。 从该位置完成所有以下步骤。

-   **创建移动应用保护策略。** 除为策略命名（以及有选择性地提供说明）外，要[创建应用保护策略](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#create-an-app-protection-policy)只需定义平台、选择想要保护的应用并配置要强制实施的策略设置即可：

> **定义平台**：创建新策略时能够选择 iOS 或 Android 平台，但不能在此处创建适用于 Windows 设备的应用保护策略。 可改为[使用 Windows 信息保护 (WIP) 策略](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune)。

> 从可在非托管设备上得到保护的可用应用列表中**选择一个或多个应用**作为目标。 随着受支持的应用越来越多，它们会自动添加到可用应用列表中。 默认情况下，不会选中任何应用，但可按住 Ctrl 并单击选择多个想要使用策略进行保护的应用。 或者，也可以[添加我们自己的适用于 iOS 或 Android 的业务线 (LOB) 应用](https://docs.microsoft.com/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune)。

> [为 iOS 或 Android](https://docs.microsoft.com/en-us/intune-azure/manage-apps/app-protection-policies#policy-settings)**配置所需策略设置**用于数据重定位（剪切、复制、粘贴、另存为、加密等）和访问（需要 PIN、脱机时间间隔等）。

- 通过[选择将应用策略的用户组](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#deploy-a-policy-to-users)，**向用户组部署应用保护策略**。 可以是已在 Office 365 中管理的相同组或在 Azure Active Directory 中可用的任何组。

最终用户首次打开受应用保护策略保护的应用时，将收到一条消息，告知他们 IT 部门现在正在应用中保护公司数据。 如果已将策略“访问权限”设置配置为需要 PIN 或密码，系统还会提示用户先创建一个 PIN 或密码，然后才可获得访问 Android 设备中受保护应用的权限，如下所示：

![应用保护策略 PIN 要求](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig1.png)

因为应用保护策略适用于应用级别，而不适用于设备级别，因此 Intune 通过限制在托管应用和个人应用之间，以及相同应用内的公司帐户和个人帐户之间共享公司数据，并且仅允许公司数据保存到已批准位置，使 IT 部门可轻松保护公司数据。 若要在移动时获得访问重要公司工具和数据的权限，使用移动设备的员工无需再放弃对其设备的控制权。

>[!TIP]
>对于高度机密的数据，可通过 Azure 信息保护使用的保护技术将保护进一步扩展到文件级别：[Azure 权限管理 (Azure RMS)。](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

## <a name="allow-only-mobile-apps-that-support-app-protection-policies-to-access-office-365-services"></a>仅允许支持应用保护策略的移动应用访问 Office 365 服务
默认情况下，所有用户和所有应用都有权访问 Exchange Online 托管的公司信息。 借助 Intune，可通过仅对支持 Intune 应用保护策略的应用配置限制访问 Office 365 服务的应用条件性访问策略，轻松控制向其授予访问权限的人员和应用。 例如，从 [Azure 门户](https://portal.azure.com)，可仅对 Android 和 iOS（无论设备是否进行了托管）上的特定组和应用创建限制访问 Exchange Online 的策略。

- **对 Exchange Online 创建应用保护条件性访问策略。** [这些策略的创建位置](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-exchange-online)与之前讨论的应用保护策略的创建位置相同。 除了定义允许访问 Exchange Online 的应用外，还需要定义用户访问组，管理与 Exchange Online 的连接。

- 用户首次尝试使用受策略支持的应用访问 Exchange Online 时，需要**配置代理应用**。 对于 iOS 设备，代理应用是 Microsoft Authenticator 应用，而 Android 设备需要安装 Intune 公司门户应用。 虽然[这些代理应用](https://docs.microsoft.com/intune/deploy-use/use-apps-with-mam-ca)将向 Azure AD 注册设备以提供设备标识验证，但它们不会将设备注册到管理中。

借助用于 Exchange Online 的条件性访问策略，用户尝试使用如 Android 设备上所示的本机电子邮件客户端访问其公司电子邮件时，将收到一封电子邮件，如下所示：

![应用保护策略 Outlook 应用要求](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig2.png)

最终用户点击电子邮件中的“立即开始”链接时，设备的默认 Web 浏览器将打开并显示 https://portal.manage.microsoft.com/OutlookRedirect.aspx。 此时，系统将提示用户从设备使用的应用商店安装免费的 Microsoft Outlook 应用。

### <a name="learn-more"></a>了解详细信息

[开始使用企业移动性 + 安全性](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft 企业移动性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Jan17_HO1-->


