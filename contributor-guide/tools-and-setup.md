<properties pageTitle="安装和设置用于在 GitHub 中进行创作的工具" description="在 GitHub 中创作 EMS 内容需要设置的工具和步骤。" services="contributor-guide" documentationCenter="" authors="v-jocgar" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# 安装和设置用于在 GitHub 中进行创作的工具
步骤如下：
- [ ] #21 整个过程需要使用非 Microsoft 帐户和计算机进行测试。 

按照本文中的步骤，设置参与 EMS 技术文档编辑的工具。 

- 如果你不熟悉 Git，你可能想要查看一些 Git 术语：[https://help.github.com/articles/github-glossary](https://help.github.com/articles/github-glossary)。
- 我们还强烈建议你观看这套有关 [Git 和 Github 基础](https://www.youtube.com/playlist?list=PLg7s6cbtAD15G8lNyoaYDuKZSKyJrgwB-)的视频。 视频内容简练且易于上手。  

## 分步说明

- [创建 GitHub 帐户并设置你的个人资料](#create-a-github-account-and-set-up-your-profile)
- [GitHub 中的权限](#permissions-in-github)
- [安装适用于 Windows 的 Git](#install-git-for-windows)
- [启用双因素身份验证](#enable-two-factor-authentication)
- [创建个人访问令牌](#create-a-personal-access-token)
- [安装 Markdown 编辑器](#install-a-markdown-editor)
- [配置 Atom](#configure-atom)
- [从存储库中创建分支](#create-a-branch-from-the-repository)
- [设置远程存储库连接和配置凭据](#set-remote-repository-connection-and-configure-credentials)
- [在本地配置用户名和电子邮件](#configure-your-user-name-and-email-locally)
- [后续步骤](#next-steps)

## 创建 GitHub 帐户并设置你的个人资料

若参与编辑 EMS 技术内容，你需要一个 [GitHub](http://www.github.com) 帐户。

- **个人资料图片**：你的图片（必需）
- **名称**：你的名字和姓氏（必需）
- **电子邮件**：你的电子邮件地址（必需）
- **公司**：你的公司（必需）
- **位置**：列出你的位置（必需）

你的个人资料应类似于此配置文件：

 ![GitHub 配置文件示例](./media/githubprofile.png)

## GitHub 中的权限

具有 GitHub 帐户的任何人都可以通过我们的公共存储库[http://www.github.com/microsoft/emdocs](http://www.github.com/microsoft/emdocs)参与编辑 EMS 技术内容。 不需要任何特殊权限。

## 安装适用于 Windows 的 Git

从 [http://git-scm.com/download/win](http://git-scm.com/download/win) 安装**适用于 Windows 的 Git**。 此下载会安装 Git 版本控制系统，并安装 Git Bash - 你用于与本地 Git 存储库进行交互的命令行应用。

**注意**
此程序并不与“适用于 Windows 的 Github”相同。 “适用于 Windows 的 Github”是一个不同的基于 GUI 的工具，如果你想要自己读取，它也仍然可用。 [https://windows.github.com/](https://windows.github.com/)) 

在安装过程中，你可以选择与 Github 存储库进行交互的方式。 我们建议你仅使用 Git Bash 中的 Git。 
 ![GitHub 配置文件示例](./media/gitbashinstall.png)

## 启用双因素身份验证

如果你正在使用专用的内容存储库，则你需要对 GitHub 帐户启用双因素身份验证 (2FA)。 为此，请按照以下 GitHub 帮助主题中的说明进行操作：

- [关于双因素身份验证](https://help.github.com/articles/about-two-factor-authentication/)

## 创建个人访问令牌
个人访问令牌可在 GitHub 中对你和你所使用的计算机进行身份验证。
1. 在 GitHub 中，单击你自己，然后单击“设置”。
2. 在“个人访问令牌”选项卡上，单击“生成新令牌”。
3. 为令牌提供说明。 
4. 设置作用域。 若要对存储库和用户具有完全访问权限，可选中那些权限复选框。
5. 单击“生成令牌”。
6. 复制显示的令牌并将其粘贴到安全的位置，如电子邮件或 Word 文档。 你需要此令牌向 GitHub 拉取和推送信息。

## 安装 markdown 编辑器

我们在文件中使用简单的“Markdown”表示法，而非复杂的“标记”（HTML、XML 等）来编写内容。 因此，你将需要安装 Markdown 编辑器。 我们使用 Github 风格的 Markdown。 

- **Atom**：大多数参与编辑者都使用 GitHub 的 Atom Markdown 编辑器：[http://atom.io](http://atom.io)。 它不要求提供业务使用许可证，并且它有拼写检查。 
- **记事本**：你可以使用记事本作为一个非常轻量级的选项。
- **Prose**：它是一个简洁的轻量级联机 Markdown 编辑器，提供预览功能并且开放源代码。 请访问 [http://prose.io](http://prose.io) 并授权储存库中的 Prose。
- **[Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx)** - 此空间中的 Microsoft 条目。
- **MarkdownPad 2**：你可以免费使用 [MarkdownPad 2](http://markdownpad.com/)，但如果你购买了许可证，则可以利用 Github 风格的 Markdown 呈现实时预览。  

## 配置 Atom Markdown 编辑器

如果你使用 Atom，你将需要进行一些设置。

- Atom 默认情况下对制表符使用 2 个空格，但 Markdown 需要 4 个空格。 如果你对其保留默认值为二，你的文章在本地预览中看起来会很不错，但将其导入到 docs.microsoft.com 中之后，就会显得不够美观。 因此，将 Atom 配置为使用 4 个空格 - 你可以在“文件”->“设置”->“编辑器设置”-> “Tab 长度”下找到此设置。 
- 你可能还想在本部分中打开软换行功能，其作用与记事本中的“自动换行”相同。 
- 若要打开 markdown 预览，请单击“包”->“Markdown 预览”->“切换预览”。 你可以使用 Ctrl-Shift-M 来切换预览 HTML 视图。 

## 从存储库中创建分支

在 GitHub 中，从存储库创建分支。 

1. 打开 Git Bash。 
2. 在命令提示符下，输入以下命令。 

        git clone https://[your GitHub user name]:[token]@github.com/microsoft/emdocs.git

此命令在你的计算机上创建一个 `emdocs` 目录。  如果你正在使用默认位置，它将位于 `c:\users\<your Windows user name>\emdocs` 中。 例如，此克隆命令会像这样：

        git clone https://smithj:b428654321d613773d423ef2f173ddf4a312345@github.com/microsoft/emdocs.git  

## 设置远程存储库连接和配置凭据

将 Git 配置为在默认情况下使用你的 GitHub ID 和个人访问令牌，以便无需为每个 `push` 或 `pull` 操作手动键入或粘贴访问令牌。 

在 git bash 中运行以下命令：

        cd emdocs
        git remote –v 
        git remote remove origin
        git remote add origin http://<githubID>:<token>@github.com/microsoft/emdocs
        git remote -v

这通常需要一段时间。 执行此操作之后，你不必重新输入凭据。 如果你在另一台计算机上设置这些工具，则只需要再次重复此过程。

## 在本地配置用户名和电子邮件

若要确保正确将你列为参与者，则需要在 Git 中本地配置你的用户名和电子邮件。

1. 启动 Git Bash，然后切换到 emdocs
   ````
   cd emdocs
   ````
2. 配置你的用户名，使其匹配你在 GitHub 配置文件中设置的姓名：

    ````
    git config --global user.name "John Doe"
    ````
3. 配置你的电子邮件，使其匹配你在 GitHub 配置文件中指定的主电子邮件：

    ````
    git config --global user.email "alias@example.com"
    ````
4. 键入 `git config -l` 并查看你的本地设置，以确保配置中的用户名和电子邮件是正确的。

## 后续步骤

- 为了便于你开始编写，请阅读并遵循[使用 Git](./work-with-git.md) 中的说明。


## 返回主页

- [文章概述](./../README.md)
- [指南文章的索引](./contributor-guide-index.md)


<!--Anchors-->
[Create a GitHub account and set up your profile]: #create-a-github-account-and-set-up-your-profile
[Permissions in GitHub]: #permissions-in-github
[Install Git for Windows]: #install-git-for-windows
[Enable two-factor authentication]: #enable-two-factor-authentication
[Create a personal access token]: #create-a-personal-access-token
[Install a markdown editor]: #install-a-markdown-editor
[Configure Atom]:#configure-atom
[Create a branch from the repository]: #create-a-branch-from-the-repository
[Set remote repository connection and configure credentials]: #set-remote-repository-connection-and-configure-credentials
[Configure your user name and email locally]: #configure-your-user-name-and-email-locally
[Next steps]: #next-steps

<!--HONumber=Mar16_HO2-->


