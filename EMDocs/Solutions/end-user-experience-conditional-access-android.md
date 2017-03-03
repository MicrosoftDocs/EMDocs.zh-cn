---
title: "Android 设备上的条件访问的最终用户体验"
description: "注册 Android 设备的最终用户体验。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b5e4330-6fa5-445c-b73e-86ce5b9c7964
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: fc06debb97cdbd3be1a241a711f36f6c530d65cf


---

# <a name="android"></a>Android

根据在最终用户设备上运行的操作系统版本，用户看到的注册过程和屏幕会略有不同。 本主题描述了注册 Android 设备的最终用户体验。

## <a name="enrolling"></a>注册

1.  当用户尝试访问电子邮件时，会收到类似于此示例的隔离电子邮件：

    ![显示用户在 Android 设备上接收到的隔离电子邮件的屏幕截图](./media/ProtectEmail/EUX-Android-quarantine-Email.png)

    用户单击“立即开始”  以开始注册其设备。

    > [!NOTE]
    > 如果用户没有为其设备设置默认浏览器，则系统会在设备注册过程中和注册激活过程中提示用户允许用于打开浏览器窗口的链接。 出现提示时，他们必须每次选择相同浏览器，否则注册过程会失败。

2.  系统会提示用户从相应的应用商店安装 Intune 公司门户应用。

    ![显示 Android 设备上 Intune 公司门户的屏幕截图](./media/ProtectEmail/EUX-Android-Portal.png)

    安装之后，用户会打开该应用并使用其公司凭据进行登录。

3.  在“公司访问设置”屏幕上，用户单击“开始”  以开始设置其设备并检查它是否合规。

    ![显示 Android 设备上“公司访问设置”屏幕的屏幕截图](./media/ProtectEmail/EUX-Android-company-Access-Setup.PNG)

4.  在“设备注册”屏幕上，用户单击“注册”  以开始注册其设备。

    ![显示 Android 设备上“设备注册”屏幕的屏幕截图](./media/ProtectEmail/EUX-Android-device-Enroll.png)

5.  用户必须在出现提示时通过单击“激活”  来激活设备管理员，否则设备注册过程会取消。

    ![显示用户必须在 Android 设备上激活设备管理员的屏幕截图](./media/ProtectEmail/EUX-Android-activate-DeviceAdmin.PNG)

    设备注册开始。 根据设备，可能会在注册过程中出现证书安装提示或 Samsung KNOX 隐私策略提示。 为使你（即 IT 管理员）可以远程管理设备，这些是必需的。 设备会注册到 Intune，并通过 Azure Active Directory 建立设备标识。

    ![显示 Android 设备上开始设备注册的屏幕截图](./media/ProtectEmail/EUX-Android-enrolling-Device.png)

6.  注册成功完成之后，用户单击“继续”  以开始在设备上检查合规性。

    ![显示 Android 设备上设备注册成功的屏幕截图](./media/ProtectEmail/EUX-Android-enroll-Success.png)

    如果存在合规性问题，则系统会提示用户解决问题（如创建有效密码），然后单击“检查法规遵从性”  以继续。

    ![显示用户必须解决 Android 设备合规性问题的屏幕截图](./media/ProtectEmail/EUX-Android-resolve-Compliance-Issues.png)

7.  设备完全合规之后，用户单击“继续”  以启动注册激活。 这会将 AAD 设备标识与 Exchange 提供的 EAS ID 相连接。

    > [!NOTE]
    > 在 Android 上，默认浏览器会在注册激活过程中出现几秒钟。 如果用户尚未选择默认浏览器，则系统会提示他们选择浏览器。 完成公司访问设置时，用户在每次出现提示时必须选择相同浏览器。

    ![显示 Android 设备合规的屏幕截图](./media/ProtectEmail/EUX-Android-compliance-Successful.PNG)

8.  注册激活将完成，用户单击“完成”  以退出注册和合规性验证过程。

    ![显示 Android 设备上完成公司访问设置的屏幕截图](./media/ProtectEmail/EUX-Android-all-Successful2.PNG)

    注册了用户且验证了合规性之后，应该在几分钟内可访问电子邮件。

如果用户遵循这些步骤以进行注册并合规，但仍然无法在其移动设备上访问其电子邮件，则他们可以按照以下这些附加步骤来尝试并解决问题：

1.  首先，验证其设备是否已注册。 如果未注册，则用户执行以上步骤。

2.  通过单击“检查法规遵从性” 来验证设备是否合规。 如果发现合规性错误，则用户可以遵循特定于其移动设备的有关如何解决错误（如重置其密码）的说明。

3.  致电技术支持。

## <a name="issues-and-solutions"></a>问题和解决方案
默认情况下，每 8 小时会检查一次设备，以确保它们仍然合规。 如果以前合规的设备在以后被视为不合规（例如，添加或更改了合规性策略），则用户可以执行这些步骤以使其设备重新合规：

1.  用户会通过电子邮件或在其设备上收到声明其设备不合规的通知。 此时，设备会在 Exchange 中受到隔离。

2.  当用户尝试访问电子邮件时，他们会看到隔离电子邮件，告知他们必须先解决合规性问题，然后才能进行访问。 当用户单击隔离电子邮件中的超链接时，它会将他们重定向到 Intune 公司门户中的“公司访问设置”屏幕（通过默认浏览器和 Google Play），在其中会显示设备不合规。

    ![显示 Android 设备变得不合规的屏幕截图](./media/ProtectEmail/EUX-Android-outOfCompliance.png)

3.  用户单击“继续”  ，会向其显示阻止访问电子邮件的合规性问题。

    ![显示用户必须解决 Android 设备合规性问题的屏幕截图](./media/ProtectEmail/EUX-Android-resolve-Compliance-Issues.png)

4.  在他们解决了问题之后，他们会单击“检查法规遵从性”  以验证是否解决了问题。

5.  如果问题得到解决，则用户单击“继续”  以完成该过程。 应在几分钟内可再次访问电子邮件。

### <a name="where-to-go-from-here"></a>后续步骤
最终用户体验在其他移动设备上会稍有不同。 你可以了解有关 [iOS](end-user-experience-conditional-access-ios.md) 和 [Windows Phone](end-user-experience-conditional-access-winphone.md) 的最终用户体验的详细信息。



<!--HONumber=Jan17_HO1-->


