---
title: 如何管理密码
description: 如何管理密码
keywords: ''
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 162e59f3-33a2-44b5-a59f-24612dc743f3
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: bc2ea11b240fabc94241c9569c8f8df15dd598d4
ms.sourcegitcommit: 573bba4fa70ce651971ec5bafd9967ebdd6bd6c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="how-to-manage-your-own-password"></a>如何管理密码

如果你是使用 Office 365 或 Microsoft 帐户来访问工作资源的组织中的用户（非管理员），请阅读以下部分，了解如何修复有关密码的常见问题。

## <a name="how-to-register-for-password-reset"></a>如何注册以进行密码重置
注册申请密码重置的最快速方法是转到 [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup)。

1.  转到 [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup)。
2.  请输入您的用户名和密码。
3.  通过单击“立即设置”，选择一个注册选项。 在本示例中，我将演示注册**身份验证电话**。
![显示 blahblah 的屏幕截图](./media/ft-mngPW-1-setup.png)
4.  从下拉列表中选择国家/地区代码并输入包含区号的完整电话号码。
![显示如何选择国家/地区代码的屏幕截图。 ](./media/ft-mngPW-2-enterNumber.png)![显示手机号码输入位置的屏幕截图。](./media/ft-mngPW-3-enterNumber2.png)
5.  选择“发短信给我”或“打电话给我”选项其中之一。 在本示例中，我选择“发短信给我”，此操作会向我的电话发送一个 6 位代码。 等待代码发送到手机。  
![显示已发送到手机的 6 位代码的屏幕截图。](./media/ft-mngPW-4-textCode.png)
6.  收到代码后，将其输入到输入框，然后单击“验证”。
7.  看到“谢谢”即表示验证完成！ 现在可以使用已注册的内容，随时转到 [https://passwordreset.microsoftonline.com](https://passwordreset.microsoftonline.com) 来重置密码。![显示完成注册时接收到的感谢消息的屏幕截图。](./media/ft-mngPW-5-thanks.png)

> [!IMPORTANT]
> 如果管理员允许你注册多个选项，强烈建议注册一个备份选项，以防手机丢失或无法访问电子邮件。

## <a name="how-to-reset-your-password"></a>如何重置密码
请按照以下步骤在任何工作或学校帐户的登录屏幕上重置工作或学校帐户的密码。

> [!IMPORTANT]
> 此功能仅在管理员开启后可用。 如未开启，你将看到一条消息，显示你的帐户未启用此功能。 在这种情况下可使用“与管理员联系”链接联系管理员解锁帐户。
> 
> 如果管理员已对你启用此功能，你需要先进行注册，然后才能使用。 为此，可以转到 [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup)。

1. 在任何工作或学校帐户登录页面中单击“无法访问帐户？” 或“忘记密码？” 链接，或直接转到 [https://passwordreset.microsoftonline.com](https://passwordreset.microsoftonline.com)。
   ![显示无法识别用户 ID 或密码时用户接收到的第一条消息的屏幕截图。](./media/ft-mngPW-6-resetPWbegin.png)
2. 在“你是谁？” 页面上，输入工作或学校帐户 ID，并通过验证码证明并非机器人。
   ![提示用户输入用户 ID 和所示图片验证码的屏幕截图。](./media/ft-mngPW-7-enterID.png)
3. 单击“下一步” 。
4. 选择一个选项以重置密码。 根据管理员配置系统的方式，你可能会看到以下一个或多个选择：
   - **向我的备用电子邮件发送电子邮件** - 向你的备用电子邮件或身份验证电子邮件（可选择）发送一封包含 6 位代码的电子邮件。
   - **向我的移动电话发送短信** - 向你的移动电话或身份验证电子邮件（可选择）发送一条包含 6 位代码的短信。
   - **呼叫我的移动电话** - 呼叫你的移动电话或身份验证电话（可选择）- 按 # 键验证呼叫。
   - **呼叫我的办公电话** - 呼叫你的办公室电话 - 按 # 键验证呼叫。
   - **回答我的安全问题** - 显示你需要回答的预先注册的安全问题。
   ![提示用户选择验证时所用联系方法的屏幕截图。](./media/ft-mngPW-8-answerQuestions.png)
5. 我们将使用“向我的移动电话发送短信”选项作为示例。 如果使用基于电话的选项，你需要先验证你的电话号码，然后我们才会发送短信。 输入完整的电话号码，然后单击“下一步”来验证电话号码是否正确并发送短信。
   ![显示用户需输入手机号码以接收验证短信的屏幕截图。](./media/ft-mngPW-9-textNumber.png)
6. 收到短信时，请确保使用消息正文中的验证代码，而不是发送该代码的号码。 获取短信可能会需要几分钟，请耐心等待！  
   ![显示已接收到的验证码的屏幕截图。](./media/ft-mngPW-10-verificationCode.png)
7. 现在，在页面上的输入框中输入手机接收到的代码。
   ![显示用户必须输入刚刚接收到的验证码的屏幕截图。](./media/ft-mngPW-11-enterCode.png)
8. 你的管理员可能要求二次验证步骤，这种情况下请选择一个不同的选项重复步骤 4。
9. 在“选择新密码”屏幕上，选择新密码并确认选择，然后单击“完成”。
   ![显示用户必须输入，然后确认新密码的屏幕截图。](./media/ft-mngPW-12-clickFinish.png)
10. 显示成功页面即表明密码已重置成功！ 现在可使用新密码进行登录。
    ![显示已完成密码重置过程的屏幕截图。](./media/ft-mngPW-13-success.png)
    重置密码时遇到问题？ 请阅读 [common problems and their solutions](https://azure.microsoft.com/documentation/articles/active-directory-passwords-update-your-own-password/#common-problems-and-their-solutions)（常见问题和解决方案）。

### <a name="want-to-learn-more"></a>了解更多信息？
请参阅 [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)（企业移动性 + 安全性）。
