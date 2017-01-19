---
title: "iOS 设备上的条件访问的最终用户体验"
description: "注册 iOS 设备的最终用户体验。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c641ea8-2c0e-490e-b1de-831336f46d19
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: f06e68a00fd97cb48aee21f6ed749f520d157e9b


---

# <a name="ios"></a>iOS

根据在最终用户设备上运行的操作系统版本，用户看到的注册过程和屏幕会略有不同。 本主题描述了注册 iOS 设备的最终用户体验。

## <a name="enrolling"></a>注册

1.  如果用户已在 Intune 中注册并且合规，则他们在 iOS 设备上不会看到任何区别；他们将继续可以访问电子邮件。 如果用户尚未注册，则他们会在启动其邮件应用时看到类似于下面这样的隔离消息：

    ![显示用户在 iOS 设备上接收到的隔离电子邮件的屏幕截图](./media/ProtectEmail/EUX-iOS-Get-Started.PNG)

    用户单击“立即开始”  以开始注册其设备。

2.  系统会提示用户从相应的应用商店安装 Intune 公司门户应用。

    ![显示 iOS 设备上 Intune 公司门户的屏幕截图](./media/ProtectEmail/EUX-iOS-intune-Company-Portal.png)

    安装之后，用户会打开该应用并使用其公司凭据进行登录。

3.  在“公司访问设置”屏幕上，用户单击“开始”  以开始设置其设备并检查它是否合规。

    ![显示 iOS 设备上“公司访问设置”屏幕的屏幕截图](./media/ProtectEmail/EUX-iOS-company-AccessSetup.png)

4.  在“设备注册”屏幕上，用户单击“注册”  以开始注册其设备。

    ![显示 iOS 设备上“设备注册”屏幕的屏幕截图](./media/ProtectEmail/EUX-iOS-device-Enrollment.png)

    在注册过程中，会安装移动设备管理配置配置文件，以使你（即 IT 管理员）可以远程管理设备。 如果出现提示，则用户会输入其密码。

5.  在“公司访问设置”屏幕上，用户单击“继续”  以开始在设备上检查合规性。

    ![显示 iOS 设备上设备注册成功且用户需要检查合规性的屏幕截图](./media/ProtectEmail/EUX-iOS-device-Compliance-Check.png)

    如果存在合规性问题，则系统会提示用户解决问题（如通过创建有效密码），然后单击“检查法规遵从性”  以继续。

    ![显示用户必须解决 iOS 设备合规性问题的屏幕截图](./media/ProtectEmail/EUX-iOS-check-Compliance.png)

6.  设备完全合规之后，用户单击“继续”  以继续进行。

    ![显示 iOS 设备合规且设置已完成的屏幕截图](./media/ProtectEmail/EUX-iOS-compliance-Check-Completed.png)

    注册了用户且验证了合规性之后，应该在几分钟内可访问电子邮件。

如果用户遵循这些步骤以进行注册并合规，但仍然无法在其移动设备上访问其电子邮件，则他们可以按照以下这些附加步骤来尝试并解决问题：

-   首先，验证其设备是否已注册。 如果未注册，则用户执行以上步骤。

-   通过单击“检查法规遵从性” 来验证设备是否合规。 如果发现合规性错误，则用户可以遵循特定于其移动设备的有关如何解决错误（如重置其密码）的说明。

-   致电技术支持。

## <a name="issues-and-solutions"></a>问题和解决方案
默认情况下，每 8 小时会检查一次设备，以确保它们仍然合规。 如果以前合规的设备在以后被视为不合规（例如，添加或更改了合规性策略），则用户可以执行这些步骤以使其设备重新合规：

1.  用户会通过电子邮件或在其设备上收到声明其设备不合规的通知。 此时，设备会在 Exchange 中受到隔离。

2.  如果用户尝试访问电子邮件，则他们会从 Intune 公司门户重定向回“公司访问设置”屏幕，在其中会显示他们不合规。

    ![显示 iOS 设备变得不合规的屏幕截图](./media/ProtectEmail/EUX-iOS-fallOut-Compliance.png)

3.  用户单击“继续”  ，会向其显示阻止访问电子邮件的合规性问题。

    ![显示用户必须解决 iOS 设备合规性问题的屏幕截图](./media/ProtectEmail/EUX-iOS-check-Compliance.png)

4.  在他们解决了问题之后，他们会单击“检查法规遵从性”  以验证是否解决了问题。

5.  如果问题得到解决，则用户单击“继续”  以完成该过程。

    ![显示 iOS 设备合规且设置已完成的屏幕截图](./media/ProtectEmail/EUX-iOS-compliance-Check-Completed.png)

    应在几分钟内可再次访问电子邮件。

### <a name="where-to-go-from-here"></a>后续步骤
最终用户体验在其他移动设备上会稍有不同。 你可以了解有关 [Android](end-user-experience-conditional-access-android.md) 和 [Windows Phone](end-user-experience-conditional-access-winphone.md) 的最终用户体验的详细信息。



<!--HONumber=Jan17_HO1-->


