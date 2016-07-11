---
title: "Windows Phone 上的条件访问的最终用户体验"
description: 
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 906566e0-f05e-4af5-b4d5-0efb083dca76
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5f1c98cc916bee9bb83249a16a52a5fdd3810142
ms.openlocfilehash: 1527f382ab35dd47d1342eb6e320048f76d62e60


---

# Windows Phone

根据在最终用户设备上运行的操作系统版本，用户看到的注册过程和屏幕会略有不同。  本主题描述 Windows Phones 的最终用户体验。

## 注册

1.  如果用户已在 Intune 中注册并且合规，则他们在 Windows 设备上不会看到任何区别；他们将继续可以访问电子邮件。 尚未在 Intune 中注册的用户会收到类似于此示例的隔离电子邮件：

    ![显示用户在 Windows Phone 上接收到的隔离电子邮件的屏幕截图](./media/ProtectEmail/EUX-Windows-quarantineEmail.png)

    用户单击“立即开始”  以开始注册其设备。

2.  在“公司访问设置”屏幕上，用户单击“开始”  以开始设置其设备并检查它是否合规。

    ![显示 Windows Phone 上“公司访问设置”屏幕的屏幕截图](./media/ProtectEmail/EUX-Windows1-company-Access-Setup.png)

3.  在“注册你的设备”屏幕上，用户单击“确认注册”  以开始注册其设备。

    ![显示 Windows Phone 上“设备注册”屏幕的屏幕截图](./media/ProtectEmail/EUX-Windows3-enroll-Device.png)

    在注册过程中，会安装移动设备管理配置配置文件，以使你（即 IT 管理员）可以远程管理设备。 系统可能会提示用户接受授权工作区加入的证书。

    ![显示 Windows Phone 上“工作区加入”的屏幕截图](./media/ProtectEmail/EUX-Windows4-workplaceJoin1.png)

4.  用户使用用于 Office 的电子邮件地址来登录。 他们登录之后，可能需要再次单击“确认注册”  以继续注册其设备。

    ![显示 Windows Phone 上正在进行“的工作区加入”的屏幕截图](./media/ProtectEmail/EUX-Windows5-workplaceJoin2.png)

    会检查设备以验证它是否已注册。

    ![显示 Windows Phone 上开始设备注册的屏幕截图](./media/ProtectEmail/EUX-Windows6-checking-Enrollment.png)

5.  用户随后通过选择其设备并单击“选择” 来完成注册过程。 如果未显示其设备，则他们可以选择“未在列出的设备中见到我的设备”  来重试。

    ![显示用户必须针对 Windows Phone 确认其设备的屏幕截图](./media/ProtectEmail/EUX-Windows7-confirm-Device.png)

    会检查设备以验证它是否符合公司策略。

    ![显示正在检查 Windows Phone 合规性的屏幕截图](./media/ProtectEmail/EUX-Windows9-checking-Compliance.png)

6.  如果存在合规性问题，则系统会提示用户解决问题（如创建有效密码），然后单击“检查法规遵从性”  以继续。

    ![显示用户必须解决 Windows Phone 合规性问题的屏幕截图](./media/ProtectEmail/EUX-Windows13-resolve-Compliance.png)

    在验证了合规性之后，用户会看到正在激活注册。

    ![显示 Windows Phone 上开始注册激活的屏幕截图](./media/ProtectEmail/EUX-Windows10-activating-Enrollment.png)

7.  注册已激活，用户单击“继续”  以完成该过程。 用户随后单击“完成”  以退出设置。

    ![显示 Windows Phone 上完成公司访问设置的屏幕截图](./media/ProtectEmail/EUX-Windows11-COMPLETE.png)

    注册了用户且验证了合规性之后，应该在几分钟内可访问电子邮件。

如果用户遵循这些步骤以进行注册并合规，但仍然无法在其移动设备上访问其电子邮件，则他们可以按照以下这些附加步骤来尝试并解决问题：

-   首先，验证其设备是否已注册。 如果未注册，则用户执行以上步骤。

-   通过单击“检查法规遵从性” 来验证设备是否合规。 如果发现合规性错误，则用户可以遵循特定于其移动设备的有关如何解决错误（如重置其密码）的说明。

-   致电技术支持。

## 问题和解决方案
默认情况下，每 8 小时会检查一次设备，以确保它们仍然合规。 如果以前合规的设备在以后被视为不合规（例如，添加或更改了合规性策略），则用户可以执行这些步骤以使其设备重新合规：

1.  用户会通过电子邮件或在其设备上收到声明其设备不合规的通知。 此时，设备会在 Exchange 中受到隔离。

2.  如果用户尝试访问电子邮件，则他们会从 Intune 公司门户重定向回“公司访问设置”屏幕，在其中会显示他们不合规。

    ![显示 Windows Phone 变得不合规的屏幕截图](./media/ProtectEmail/EUX-Windows14-OutOfCompliance.png)

3.  用户单击“继续”  ，会向其显示阻止访问电子邮件的合规性问题。

4.  在他们解决了问题之后，他们会单击“检查法规遵从性”  以验证是否解决了问题。

5.  如果问题得到解决，则用户单击“继续”  以完成该过程。 应在几分钟内可再次访问电子邮件。

### 后续步骤
最终用户体验在其他移动设备上会稍有不同。 你可以了解有关 [Android](end-user-experience-conditional-access-android.md) 和 [iOS](end-user-experience-conditional-access-ios.md) 最终用户体验的更多信息。



<!--HONumber=Jun16_HO4-->


