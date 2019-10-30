---
title: IT 管理员最终用户 Intune 注册说明
description: IT 管理员最终用户 Intune 注册说明
keywords: ''
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: 5c13446e-aa31-47df-ad9d-373be7660197
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: 2b9f32d79ab00c55962df67cab9bc2bad9549c44
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196808"
---
# <a name="end-user-intune-enrollment-instructions-for-it-administrators"></a>IT 管理员最终用户 Intune 注册说明

该文档包含你可自定义和提供给用户的注册说明，以帮助用户在 Microsoft Intune™ 中注册 iOS 和 Android 设备（对于 Windows 设备，请参阅[“通过 Intune 使用 Windows 设备”](/intune-user-help/using-your-windows-device-with-intune)）。 我们建议复制本文档中你认为最适合于用户的部分。 例如，建议对每个设备平台生成一个单一文档或添加更多屏幕截图。

除了这些书面说明外，还可以添加 [https://channel9.msdn.com/Series/IntuneEnrollment](https://channel9.msdn.com/Series/IntuneEnrollment) 中任何 Intune 最终用户视频的超链接。

> [!NOTE]
> Microsoft、Intune 和 Office 365 是 Microsoft Corporation 的注册商标。 iPhone、Mac 和 Apple 是 Apple，Inc. 的商标是 Google Inc. 的商标。 Samsung KNOX 是 Samsung 电子设备有限公司的商标。

## <a name="why-enroll-in-intune"></a>在 Intune 中注册的原因
注册后，可使用移动设备访问工作或学校文件和数据。 还可让 IT 部门来管理这些工作或学校资源并保护其安全，同时使你可以自由地使用首选设备来完成工作。

若要在工作中使用设备，可使用公司门户在 Intune 中注册你的设备。 随后，你便可轻松地找到要安装的公司应用、查看已添加的其他设备，并找到你的 IT 管理员的联系信息。 你还可授予 IT 管理员管理你的设备的权限，以帮助保护设备上的公司信息。 开始注册之前，请确保连接到 Internet 的 wifi 或手机网络连接良好，然后再开始。

## <a name="enroll-your-android-device-in-intune-using-the-intune-company-portal-app"></a>使用 Intune 公司门户应用在 Intune 中注册 Android 设备

这些注册步骤适用于 Samsung Knox Android 设备和“本机”（非 Samsung Knox）Android 设备。 若要确定你的设备是否为 Samsung Knox 设备，请转到“设置”>“关于手机”。 如果未在此处看到列出了“Knox”一词，则你具有本机 Android 设备。 设备上显示的屏幕可能与本部分中的屏幕略有不同。

如果尝试在 Intune 中注册设备时遇到错误，请参阅[将注册错误发送给 IT 管理员](https://technet.microsoft.com/library/mt502762(TechNet.10).aspx#BKMK_andr_send_enroll_errors)。

注册前/后，系统可能会要求你选择最恰当地描述了你使用设备的方式的类别。 IT 管理员将使用此类别来帮助确定你有权访问哪些应用。
1. 请从 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 中将免费的 Microsoft Intune 公司门户应用安装到设备上。
2. 打开 Microsoft Intune 公司门户应用。
3. 在公司门户的“欢迎”屏幕上，点击“登录”，然后使用你的工作或学校帐户登录。

   ![显示 Android 设备上 Intune 公司门户登录屏幕的屏幕截图](./media/ft-userEnrollAndroid-1-signUp.png)

4. 如果 IT 管理员设置了公司条款和条件，请点击“接受”接受这些条款。

   ![Android 设备上请求用户接受条款和条件的屏幕截图](./media/ft-userEnrollAndroid-2-accept.png)
5. 如果使用的设备为 Android 6.0 或更高版本，请执行此步骤；否则，请转到下一步。

   如果 IT 管理员设置了特定策略，则你可能会看到以下其中一条或两条消息：

   - 如果看到消息“是否允许公司门户访问你的联系人？”，请点击“允许”。 点击“允许”是安全的，因为 Microsoft 绝不会访问你的联系人！ 消息文本由 Google 管控，Microsoft 无法更改。 允许访问时，只允许公司门户应用访问数据日志以帮助解决与设备有关的问题。

       ![要求用户允许门户访问 Android 设备上的联系人的屏幕截图](./media/ft-userEnrollAndroid-3-accessContacts.png)
   - 如果看到消息“是否允许公司门户发起和管理电话呼叫?”，请点击“允许”。 点击“允许”是安全的，因为 Microsoft 绝不会发起或管理电话呼叫！ 消息文本由 Google 管控，Microsoft 无法更改。 允许访问仅允许公司门户应用查看你的电话号码和名为 IMEI 的 ID。

       ![要求用户允许门户管理 Android 设备上的电话呼叫的屏幕截图](./media/ft-userEnrollAndroid-4-manageCalls.png)

   如果点击“拒绝”，下次登录到公司门户时将再次出现此消息，但你可点击“不再询问”复选框关闭显示此消息。 如果你以后决定允许访问，请转到“设置”>“应用”>“公司门户”>“权限”>“手机”，然后打开此权限。
6. 使用你的工作或学校帐户和密码登录公司门户应用，然后点击**登录**。

   ![Android 设备上请求用户登录到公司门户的屏幕截图](./media/ft-userEnrollAndroid-5-signIn.png)
7. 在“公司访问设置”页上，点击“开始”。

   ![显示 Android 设备上“公司访问设置”页的屏幕截图](./media/ft-userEnrollAndroid-6-beginSetup.png)
8. 阅读注册设备时可执行的操作，然后点击“继续”。

   ![显示有关为何应注册 Android 设备的信息的屏幕截图](./media/ft-userEnrollAndroid-7-whyEnroll.png)
9. 查看 IT 管理员在你注册的设备上可以看到和不可以看到的内容列表，然后点击“继续”。

   ![Android 设备上显示隐私策略的屏幕截图](./media/ft-userEnrollAndroid-8-privacy.png)
10. 查看点击“注册”后你可能看到的项目。 完成阅读后，点击“注册”。

    ![Android 设备上显示后续注册步骤的屏幕截图](./media/ft-userEnrollAndroid-9-whatNext.png)
11. 在“激活设备管理员”屏幕上，点击“激活”。

    ![Android 设备上请求用户激活设备管理员的屏幕截图](./media/ft-userEnrollAndroid-10-activateAdmin.png)
12. 按照提示输入 PIN 或密码。 如果已经在此设备上设置 PIN 或密码，将不会显示此屏幕或要求你输入新的 PIN 或密码。

    ![Android 设备上提示用户输入 PIN 的屏幕截图](./media/ft-userEnrollAndroid-11-enterPIN.png)
13. 按照以下与所使用的设备类型（本机 Android 或 Samsung Knox）匹配的说明进行操作。 如果并非 Samsung Knox 设备，请遵循本机 Android 的说明。 若要确定你的设备是否为 Samsung Knox 设备，请转到“设置”>“关于手机”。 如果未在此处看到列出了“Knox”一词，则你具有本机 Android 设备。
    - 本机（非 Samsung Knox）设备：在“对证书命名”屏幕上，点击“确定”接受默认证书。

        ![提示用户在本机 Android 设备上接受默认证书的屏幕截图](./media/ft-userEnrollAndroid-12-android.png)
    - Samsung Knox 设备：点击“确认”

        ![提示用户确认 Samsung Knox 设备的隐私策略的屏幕截图](./media/ft-userEnrollAndroid-13-knox.png)

    在 Intune 注册设备时，你会看到以下消息显示在屏幕上。

    ![显示正在注册 Android 设备的屏幕截图](./media/ft-userEnrollAndroid-14-enrollingDevice.png)
14. 在“公司访问设置”屏幕上，点击“继续”。 如果 IT 管理员设置了其他安全要求（例如需要设置密码），请按照屏幕上的说明进行操作，然后在返回到“公司访问设置”屏幕时，点击“继续”。

    ![显示 Android 设备合规和提示用户继续的屏幕截图](./media/ft-userEnrollAndroid-15-coAccessSetup.png)
15. 点击“完成”。

    ![显示 Android 设备上完成公司访问设置的屏幕截图](./media/ft-userEnrollAndroid-16-SetupComplete.png)
16. 你的设备现已在 Intune 中注册，你会返回到公司门户应用。
17. 你需转到“设置”>“安全性”，然后打开“未知源”才能尝试安装公司应用。 如果你在尝试安装应用前未打开此选项，则会看到消息“已阻止安装”。 出于安全性考虑，你的手机已设置为阻止安装未知来源的应用。” 你可点击错误对话框上的“设置”以转到“未知来源”选项。

## <a name="enroll-your-ios-device-in-intune"></a>在 Intune 中注册 iOS 设备
使用这些说明在 Intune 中注册 iOS 设备。 有关注册的详细信息，请参阅[安装公司门户应用并在 Intune 中注册设备后会发生什么？](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_ios_what_happ_enroll)。 如果尝试在 Intune 中注册设备时遇到错误，请参阅[将注册错误发送给 IT 管理员](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_ios_error_enrolling_tbl)。

注册前/后，系统可能会要求你选择最恰当地描述了你使用设备的方式的类别。 IT 管理员将使用此类别来帮助确定你有权访问哪些应用。
1. 请从 App Store 中将免费的 Microsoft Intune 公司门户应用安装到设备上。
2. 打开 Microsoft Intune 公司门户应用。
3. 在公司门户的“欢迎”屏幕上，点击“登录”，然后使用你的工作或学校帐户登录。

   ![iOS 设备上显示 Intune 公司门户登录屏幕的屏幕截图](./media/ft-userEnrollIOS-1-signUp.png)
4. 如果 IT 管理员设置了公司条款和条件，请点击“接受”接受这些条款。
5. 在“公司访问设置”页上，点击“开始”。

   ![iOS 设备上提示用户开始注册过程的屏幕截图](./media/ft-userEnrollIOS-2-coAccessSetup.png)
6. 阅读注册设备时可执行的操作，然后点击“继续”。

   ![显示有关为何应注册 iOS 设备的信息的屏幕截图](./media/ft-userEnrollIOS-3-whyEnroll.png)
7. 查看 IT 管理员在你注册的设备上可以看到和不可以看到的内容列表，然后点击“继续”。

   ![iOS 设备上显示隐私策略的屏幕截图](./media/ft-userEnrollIOS-4-privacy.png)
8. 查看点击“注册”后你可能看到的项目。 完成阅读后，点击“注册”。

   ![iOS 设备上显示后续注册步骤的屏幕截图](./media/ft-userEnrollIOS-5-whatNext.png)
9. 在“安装配置文件”屏幕上，点击“安装”，如有系统提示，请输入密码。

   ![提示用户安装 iOS 设备管理配置文件的屏幕截图](./media/ft-userEnrollIOS-6-installProfile.png)
10. 点击“安装”。

    ![iOS 设备上请求用户点击“安装”按钮安装配置文件的屏幕截图](./media/ft-userEnrollIOS-7-tapInstall.png)
11. 点击“安装”以表示你已阅读警告。

    ![iOS 设备上请求用户表示已阅读配置文件管理警告的屏幕截图](./media/ft-userEnrollIOS-8-readWarning.png)
12. 点击“信任”。

    ![iOS 设备上请求用户验证配置文件源的屏幕截图](./media/ft-userEnrollIOS-9-tapTrust.png)
13. 屏幕更改为显示配置文件已完成安装时，点击“完成”。 “正在注册设备”消息会显示在屏幕上。

    ![iOS 设备上显示配置文件已安装的屏幕截图](./media/ft-userEnrollIOS-10-profileInstalled.png)
14. 当显示一条询问是否要在公司门户中打开页面的消息时，点击**打开**。

    ![iOS 设备上请求用户在公司门户中打开页面的屏幕截图](./media/ft-userEnrollIOS-11-openPage.png)
15. 在“公司访问设置”屏幕上，点击“继续”。 如果 IT 管理员设置了其他安全要求（例如需要设置密码），请按照屏幕上的说明进行操作，直到满足所有合规性要求，然后在返回到“公司访问设置”屏幕时点击“继续”。

    ![显示 iOS 设备合规和提示用户继续的屏幕截图](./media/ft-userEnrollIOS-12-coAccessSetup.png)
16. 点击“完成”。

    ![iOS 设备上显示已完成公司访问设置的屏幕截图](./media/ft-userEnrollIOS-13-setupComplete.png)

你的设备现已在 Intune 中注册，你会返回到公司门户应用。

## <a name="enroll-your-mac-os-x-device-in-intune"></a>在 Intune 中注册 Mac OS X 设备
1. 使用 Safari 浏览器，打开[公司门户网站](https://portal.manage.microsoft.com/)，然后点击通知栏。
2. 点击“未注册此设备，或公司门户无法对其进行识别”。

   ![显示公司门户无法识别 Mac OS X 设备的屏幕截图](./media/ft-userEnrollMacOSx-1-enrollBegin.png)
3. 点击“安装”以开始注册你的设备。

   ![提示用户注册 Mac OS X 设备的屏幕截图](./media/ft-userEnrollMacOSx-2-enrollDevice.png)
4. 在“安装管理配置文件”对话框中，点击“安装”。 如果出现要求你输入凭据的对话框，请输入用户名和密码，然后点击“继续”>“安装”。

   ![提示用户在 Mac OS X 设备上安装管理配置文件的屏幕截图](./media/ft-userEnrollMacOSx-3-installProfile.png)

完成注册后，将出现“管理配置文件”页，显示你的配置文件已通过验证。

  ![显示已验证 Mac OS X 设备上的管理配置文件的屏幕截图](./media/ft-userEnrollMacOSx-4-profileVerified.png)

### <a name="want-to-learn-more"></a>了解更多信息？
请参阅 [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)（企业移动性 + 安全性）。
