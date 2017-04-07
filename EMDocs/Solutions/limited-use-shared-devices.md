---
title: "启用使用受限的共享设备解决方案 | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 3/24/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d78e2b94-8ad3-4703-b7f0-db070288a20b
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d4362764cad9264c513ca745c45b96590b18928f
ms.openlocfilehash: 98efafde6981fa8cb0c49c4b22729c64c8386754
ms.lasthandoff: 03/24/2017


---
# <a name="enable-a-limited-use-shared-device-solution-with-intune"></a>通过 Intune 启用使用受限的共享设备解决方案
有时员工需要共享设备来访问应用和公司数据，以完成只需要特定设置和应用的基本任务。 这在零售商店、生产车间和运输行业较常见。 其他较常见的情况是需要在会议、酒店大厅、学校或图书馆等场所使用可公开访问的设备以交互方式访问资源的客户（而非员工）。 在某些情况下，你可能只需要向浏览的用户显示自动运行的演示文稿或提供静态信息。

在无其他选择的情况下，可以全屏运行应用以提供安全的交互式展台用户体验，同时还可以保护公司资产不受可疑用户活动的侵害。 此功能使 IT 能够提供更高的安全性以及可自定义对体验，从而保证员工的工作效率并满足客户需求。

## <a name="how-can-enterprise-mobility--security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？
借助 EMS，你可以提供用于创建一个高效的工作区，并在任何场合满足客户需求的功能和体验。 无论使用 iOS、MacOS、Android 还是 Windows Mobile 公司所有的设备，Microsoft Intune 都能帮助你提高员工的工作效率并向客户传达信息，同时保证公司数据安全。

### <a name="recommended-solution"></a>建议的解决方案
借助 Intune，可以利用面向 iOS 或 Android 移动设备的展台模式配置策略设置以及已分配的 Windows Mobile 电话访问权限来锁定设备，以便只有某些特定应用或功能可以正常运行。 Intune 配置策略是控制移动设备和计算机上的功能的设置的组合。 使用包含建议设置或自定义设置的模板创建策略，然后将其部署到设备或用户组。 例如，可以将展台模式配置策略部署到设备，让设备只运行一个指定的托管应用，也可以禁用设备上的音量按钮。 这些设置可用于设备的演示模型，也可用于专门执行一个功能的设备（如销售点设备）。

### <a name="how-to-implement-this-solution"></a>实现本解决方案的方式
此解决方案的其余部分分为以下各节，展示如何配置：
- **适用于 iOS 的展台模式**。 本部分说明了如何使用展台模式 Intune 配置策略设置锁定 iOS 设备。
- **适用于 Android 的展台模式**。 本部分说明了如何使用 Samsung KNOX 设备的展台模式 Intune 配置策略设置锁定 Android 设备。
- **适用于 Windows 的已分配的访问策略**。 本节介绍如何使用 EnterpriseAssignedAccess 配置服务提供程序 (CSP) 来锁定 Windows 10 移动版设备，以提供分配的访问权限体验。

## <a name="kiosk-mode-for-ios"></a>适用于 iOS 的展台模式
Intune 提供了可以在 iOS 设备上配置的大量内置常规设置，其中包括允许你锁定托管 iOS 设备的展台模式配置设置。  

在为展台模式配置 iOS（8.0 及更高版本）设备之前，必须首先在 Mac 设备上使用 [Apple 配置器工具](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)，或者部署注册配置文件以[注册通过 Apple 设备注册计划 (DEP) 购买的 iOS 设备](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)，使设备处于监督模式。 在此操作完成后，可以使用 Intune 配置策略部署展台模式配置设置来控制应用和设备设置。

在 Intune 管理员控制台中，只需依次导航到 Intune 管理控制台的“策略”和“iOS”节点，创建一个新的 **iOS 常规配置（iOS 8.0 及更高版本）**策略，然后定义展台模式设置。 这些设置最重要的一点是定义在设备处于展台模式时允许运行的托管应用。

![iOS 展台模式策略设置](..\Solutions\media\limited-use-devices\kiosk-mode-policy.png)

你可以指定托管应用或来自 Apple 应用商店的应用，但在应用展台模式策略后，设备上将无法运行其他任何应用。 此外，请注意，部署该策略后，它只会影响处于监督模式的 iOS 设备。

> [!NOTE]
> 如果在部署配置策略之后安装已指定的应用，设备将在重启后才会进入展台模式。

## <a name="kiosk-mode-for-android"></a>适用于 Android 的展台模式
锁定 Android KNOX 标准版（4.0 及更高版本）设备的方式类似于将 iOS 设备置于展台模式的方式。 在 Intune 管理员控制台中，只需依次导航到 Intune 管理控制台的“策略”和“Android”节点，创建一个新的**常规配置（Android 4 及更高版本，Samsung KNOX 标准版 4.0 及更高版本）**策略，然后定义展台模式设置。

可用于配置 Android KNOX 设备的设置较少，但最重要的一点仍然是展台模式下允许运行托管应用。 如果不小心谨慎，这些设备将不支持应用商店应用，并且部署的策略将在接收该策略的任何 Samsung KNOX 设备（包括 BYOD 个人设备）上运行。 为此，应仅将适用于 Android 设备的展台模式设置部署到管理需要作为展台设备进行管理的公司所有的设备的批量注册的人员。

> [!NOTE]
> 如果在部署配置策略之后安装已指定的应用，设备将在重启后才会进入展台模式。

## <a name="assigned-access-policies-for-windows"></a>适用于 Windows 的已分配的访问策略
也可以将 Windows 10 移动版（版本 1511 及更高版本）设备配置为展台设备，但使用的是自定义 Windows 配置策略而不是常规配置策略。 你可以通过此类策略利用 [Windows 10 OMA-URI 设置](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings)通过 Intune 来管理设备配置设置。

> [!TIP]
> [配置服务提供程序 (CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) 在 Windows 10 中公开 OMR-URI 设备配置设置。

[EnterpriseAssignedAccess CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/enterpriseassignedaccess-csp)用于锁定 Windows 10 设备以提供分配的访问权限体验。 此外，还可以使用该 CSP 来配置其他设置，如语言、主题，或在设备上配置自定义布局。

若要创建适用于 Windows 设备的策略，需要依次转到 Intune 管理控制台的“策略”节点和“Windows”，创建一个新的**自定义配置（Windows 10 桌面版和移动版及更高版本）**策略。 你需要在该位置提供 CSP 信息并导入定义要应用到此策略部署面向的 Windows 设备的设置的有效 XML 文件。  

![OMA-URI 设置](..\Solutions\media\limited-use-devices\settings.png)

若要创建一个简单的分配的访问策略，请提供名称、说明的基本元数据，将数据类型设置为**字符串 (XML)**，然后输入*区分大小写的*OMA URI 值的 **./Vendor/MSFT/EnterpriseAssignedAccess/AssignedAccess/AssignedAccessXml**。 在以下示例 .XML 中，设备将被锁定，以便仅允许列表（本例中为 Microsoft Edge）中指定的应用程序可在设备上使用。 无法被允许列表中 [Windows 10 移动版应用产品 ID](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/customize/mdm/enterpriseassignedaccess-csp#productid) 识别的应用仍会在设备上安装，但会在视图中隐藏并阻止启动。 若要输入所需的 .XML 数据，只需导入包含以下示例信息的新的 .XML 文件或复制并将其作为单行格式的 XML 粘贴到**值**文本区域：


> [!IMPORTANT]
> 将提供的格式化 XML 示例粘贴到值框中时，请务必将整个 XML 格式设置为单行。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<HandheldLockdown version="1.0">
   <Default>
      <ActionCenter enabled="false" />
      <Apps>
         <!-- Microsoft Edge -->
         <Application productId="{395589FB-5884-4709-B9DF-F7D558663FFD}" autoRun="true">
            <PinToStart>
               <Size>Medium</Size>
               <Location>
                  <LocationX>0</LocationX>
                  <LocationY>0</LocationY>
               </Location>
            </PinToStart>
         </Application>
      </Apps>
      <Buttons>
         <ButtonLockdownList>
            <!-- Lockdown all buttons -->
            <Button name="Search">
               <ButtonEvent name="Press" />
               <ButtonEvent name="PressAndHold" />
            </Button>
            <Button name="Camera">
               <ButtonEvent name="Press" />
               <ButtonEvent name="PressAndHold" />
            </Button>
         </ButtonLockdownList>
         <ButtonRemapList />
      </Buttons>
      <MenuItems>
         <DisableMenuItems />
      </MenuItems>
      <Settings>
         <System name="Microsoft.WiFi" />
         <System name="Microsoft.About" />
         <System name="Microsoft.Feedback" />
         <System name="Microsoft.CompanyAccount" />
         <System name="Microsoft.VPN" />
      </Settings>
      <StartScreenSize>Small</StartScreenSize>
   </Default>
</HandheldLockdown>

```
成功创建策略后，将其部署到你想要配置为展台设备的 Windows 设备组。

> [!IMPORTANT]
> 请务必将分配的访问策略部署到正确的组。 除了恢复设备的出厂设置外，没有其他方法可以撤销已分配的访问策略。

### <a name="learn-more"></a>了解详细信息
[开始使用企业移动性 + 安全性](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft 企业移动性](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

