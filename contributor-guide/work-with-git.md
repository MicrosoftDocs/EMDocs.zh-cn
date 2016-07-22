<properties pageTitle="Git 命令可用于创建新项目或更新现有项目" description="有关使用 Azure 技术内容 GitHub 存储库的步骤。" metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/24/2016" ms.author="v-jocgar" />

# 使用 Git

步骤如下：
- [ ] #22 替换已完成项目的 EMS URL（请参阅说明的末尾）

## 标准进程（分支中工作）
按照本文中的步骤，在你的计算机上创建本地工作分支，以便你可以为 Microsoft.com/ems 的技术文档部分创建新项目或更新现有项目。

1. 启动 Git Bash。 

2. 更改为存储库 `emdocs`：

        cd emdocs
        
3. 创建新的工作分支：

        git checkout <branchname>

4. 创建新的本地工作分支：

        git pull origin master:<branchname>

5. 创建新项目或更改为现有项目。 将 Atom (http://atom.io) 用作 Markdown 编辑器（或你喜欢的其他编辑器），以创建并打开新的 Markdown 文件。 创建或修改项目和图像之后，请转到下一步。

6. 添加并提交你创建的任何新文件：

        git add <path-to-file>
        git commit –m "<comment>"
        
   或者，仅提交你修改过的特定文件：

        git commit -a –m "<comment>"

7. 让你的源了解你创建了本地工作分支：

        git push origin <branchname>

8. 在 GitHub 上将所做的更改推送到你的分支中：

        git push origin <branchname>

9. 当准备好将你的内容提交到主分支以执行暂存、验证和/或发布操作时，在 GitHub UI 中，创建从你的分支到主分支的“拉取”请求。

10. 拉取请求的收件人将查看你的拉取请求、提供反馈和/或接受你的拉取请求。 

11. 有选择地验证你的已发布文章或所做更改
<span style="color:red;">查看已发布的文章需要正确的 URL。</span>
 http://docs.microsoft.com/ems/articles/name-of-your-article-without-the-MD-extension


<!--HONumber=Mar16_HO2-->


