---
title: "如何注册多重身份验证"
description: "如何设置其他安全性验证的首选方式"
keywords: 
author: craigcaseyMSFT
manager: jeffgilb
ms.date: 09/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 06e21ca9-ed6a-4f6e-a7e2-5445aaeb3552
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e422a74e551753ddb579d98789670cd8c1811b80
ms.openlocfilehash: 4b1c82f5ecd5360b51d0f2af69df77ff2924aa0e


---

# 如何设置其他安全性验证的首选方式



当管理员已将你的帐户配置为要求必须同时使用密码和手机响应以验证你的身份时，将使用“其他安全性验证”设置。 如果管理员已将你的帐户配置为需要其他安全性验证，则你在完成自动注册过程之前将无法登录。

在配置帐户后首次登录时，系统将提示你开始进行自动注册过程。 可以通过单击“立即设置”开始执行此过程。

![提示用户为帐户注册其他安全性验证的屏幕截图](./media/ft-enrollMFA-1-beginProcess.png)

使用注册过程，你将能够指定首选的身份验证方法。 此方法可以是下表所列选项中的任何一种。 如需更多信息（包括演练），只要单击其中一种方法即可。


|方法|说明|
|------------|----------------------------------|
|[移动电话呼叫](#mobile-phone-(text-or-call))|对身份验证电话号码进行自动语音呼叫。 用户接听电话，并按电话拨号键盘中的 # 进行身份验证。 此电话号码将不会同步到本地 Active Directory。|
|[手机短信](#mobile-phone-(text-or-call))|向用户发送包含验证码的短信。 系统会提示用户使用验证码回复短信或在登录界面中输入验证码。|
|[办公电话呼叫](#office-phone-call)|对用户进行自动语音呼叫。 用户接听电话，并按电话拨号键盘中的 # 进行身份验证。|
|[移动应用](#mobile-application)|将通知推送到用户的智能手机或平板电脑上的 Azure 验证器移动应用。 用户在应用中点击“验证”进行身份验证。 此外，该应用程序还可以用作进行脱机身份验证的 OTP 令牌。 用户在登录屏幕上输入令牌进行身份验证。|

_Azure 验证器应用可以 2 种不同模式运行，以提供多重身份验证服务能够提供的附加安全性。 这两种模式是：_

- **通知** - 在此模式下，Azure 验证器应用可防止对帐户进行未经授权的访问并停止欺诈性交易。 此功能是使用推送到你的手机或已注册设备上的通知来完成的。 直接查看通知，如果该通知是合法的，则选择“身份验证”。 否则，你可以选择“拒绝”或选择拒绝并报告欺诈性通知。 有关报告欺诈性通知的信息，请参阅“如何针对多重身份验证使用‘拒绝并报告欺诈’功能”。
- **一次性密码** - 在此模式下，Azure 验证器应用可用作生成 OATH 验证码的软件令牌。 然后可以将此验证码与用户名和密码一起输入，进行第二种形式的身份验证。

Azure 验证器应用可用于 [Windows Phone](http://www.windowsphone.com/en-us/store/app/azure-authenticator/03a5b2bf-6066-418f-b569-e8aecbc06e50)、[Android](https://play.google.com/store/apps/details?id=com.azure.authenticator) 和 [IOS](https://itunes.apple.com/us/app/azure-authenticator/id983156458)。

## 移动电话（短信或呼叫）
如果要使用移动电话作为主要联系方式，可使用以下步骤。 这些步骤将会引导你设置多重身份验证，以使用移动电话呼叫或短信作为联系方法。

1. 在“步骤 1：我们应如何联系你？”中，选择“身份验证电话”。

  ![显示用户希望通过电话进行联系的屏幕截图](./media/ft-enrollMFA-2-securityVerification.png)
2.  在“国家或地区”框中，从下拉列表中一个值。 可能已显示有一个默认值。
3.  在“国家或地区”框旁边的框中，键入你的移动电话号码。 包括区号。
允许有空格，但不允许有标点符号字符。 例如，允许 5554445555 和 555 444 5555，但不允许 555-444-5555 和 (555) 444 5555。
4.  选择想要使用的移动电话通信模式：短信或呼叫。
5.  单击“下一步” 。
6.  单击“立即验证”按钮。 此操作将向你的移动电话发起呼叫或发送短信。 请确保随身携带电话。 根据你选择的模式（短信或呼叫），响应将有所不同。
 - 如果你选择了短信模式，将通过短信向你发送 6 位代码。 请在浏览器的显示框中输入此代码。

        ![Screenshot asking user to enter the code that was texted to them](./media/ft-enrollMFA-3-textCode.png)
 - 如果你选择了呼叫模式，你将收到电话呼叫。 请使用电话上的 # 号响应此呼叫。

        ![Screenshot prompting user to answer their phone to continue enrollment process](./media/ft-enrollMFA-4-phoneCode.png)
7. 单击“下一步” 。
8.  此时，你已设置好联系方法，接着可以设置非浏览器应用（例如 Outlook 2010 或更低版本）的应用密码。 如果你不使用这些应用，请单击“完成”。 否则，请**继续**下一步骤。
9. 如果你正在使用这些应用，请**复制**提供的应用密码。

  ![提示用户输入应用密码的屏幕截图](./media/ft-enrollMFA-5-copyPW.png)
10. 将已复制到剪贴板的密码粘贴到非浏览器应用程序。
11. 单击“完成”。

## 办公电话呼叫
本文此部分将引导你设置 Azure 多重身份验证，以使用办公电话作为主要联系方式。
1. 从下拉列表中选择“办公电话”。

  ![显示用户希望通过办公电话进行联系的屏幕截图](./media/ft-enrollMFA-6-officePhone.png)
2.  在下拉列表中指定你的国家/地区，然后输入办公电话号码。
3.  单击“与我联系”。 这将向你的办公电话发起呼叫。 请务必待在办公电话旁边。
4.  单击“下一步” 。
5.  此时，你已设置好联系方法，接着可以设置非浏览器应用（例如 Outlook 2010 或更低版本）的应用密码。 如果你不使用这些应用，请单击“完成”。 否则，请**继续**下一步骤。
7.  如果你正在使用这些应用，请复制提供的应用密码。
8.  将已复制到剪贴板的密码粘贴到非浏览器应用程序。

  ![提示用户输入应用密码的屏幕截图](./media/ft-enrollMFA-7-pastePW.png)
9.  单击“完成”。

## 移动 应用程序
本文此部分将引导你设置 Azure 多重身份验证，以使用移动电话作为主要联系方式。

Azure 验证器应用可用于 Windows Phone、Android 和 IOS。

1. 从下拉列表中选择“移动应用”。

  ![显示用户希望通过移动应用进行联系的屏幕截图](./media/ft-enrollMFA-8-mobileApp.png)
2.  选择“通知”或“一次性密码”，然后单击“设置”。
3.  在已安装 Azure 验证器应用的手机上，启动该应用并单击“扫描条形码”。

  ![提示用户选择扫描条形码选项的屏幕截图](./media/ft-enrollMFA-9-scanBarcode.png)
4.  扫描“配置手机应用程序”屏幕显示的条形码图片。 单击“完成”关闭条形码屏幕。 如果无法扫描条形码，请手动输入信息。

  ![提示用户扫描移动应用中出现的条形码的屏幕截图](./media/ft-enrollMFA-9-scanBarcode2.png)
5.  在手机上，将开始激活过程，完成此过程后，请单击“与我联系”。 随后会将通知或验证码发送到你的手机。 单击“验证”。

  ![提示用户验证发送到其手机的代码的屏幕截图](./media/ft-enrollMFA-10-verifyActivation.png)
6.  单击“关闭”。 此时，验证应成功。
7.  现在建议输入你的移动电话号码，以免无法访问移动应用。
8.  在下拉列表中指定你的国家/地区，然后在国家/地区旁边的框中输入移动电话号码。 单击“下一步” 。
9.  此时，你已设置好联系方法，接着可以设置非浏览器应用（例如 Outlook 2010 或更低版本）的应用密码。 如果你不使用这些应用，请单击“完成”。 否则，请**继续**下一步骤。
10. 如果你正在使用这些应用，请复制提供的应用密码。
11. 将已复制到剪贴板的密码粘贴到非浏览器应用程序。

  ![提示用户输入应用密码的屏幕截图](./media/ft-enrollMFA-11-securityVerification.png)
12. 单击“完成”。

### 了解更多信息？
请参阅 [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)（企业移动性 + 安全性）。



<!--HONumber=Oct16_HO2-->

