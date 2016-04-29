<properties pageTitle="在停用或重命名 EMS 技术文章时须遵循的步骤" description="在停用或重命名 EMS 技术文章时须遵循的步骤。" metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar" />

# 在重命名或停用 EMS 技术文章时须遵循的步骤

步骤如下：
- [ ] #57 确认能否以这种方式停用 EMS 内容。 这看起来更像是一组仅限内部执行的过程。 
- [ ] #58 确认外部作者能否对 Microsoft 内容运行 Web 分析工具。 
- [ ] #59 测试在存储库中查找交叉链接的过程。
- [ ] #60 确认 EMS 文档的 URL。  
- [ ] #61 确认外部作者能否删除交叉链接。 
- [ ] #62 确认外部作者能否创建重定向。
- [ ] #63 确认外部作者能否从存储库中删除文章。
- [ ] #64 确认外部作者能否请求从搜索引擎中删除 Microsoft 内容。


<span style="color:red;">确认能否以这种方式停用 EMS 内容。 这看起来更像是一组仅限内部执行的过程。 </span>
本指南面向被列为需要在 http://docs.microsoft.com/ems 的技术文档部分中停用的文章的作者的行业专家 (SME)。 如果文件需要重命名，这些步骤也适用。

SME 作者需要按照几个步骤操作以正常停用内容，这样网站用户就不会在我们停用网站中的内容时获得不愉快的体验。 不到万不得已不要删除或重命名文章！

如果你是我们 EMS 社区的成员，并认为出于某种原因应停用某篇文章，请对这篇文章发表评论，让作者知道其文章存在问题。

## 第 1 步：管理入站链接

确定是否有任何非 Microsoft 入站链接指向你的内容。 博客、论坛和其他 Web 内容常常会指向文章。 通常情况下，你可以与博客所有者合作，共同更改这些链接，也可以删除或更新论坛帖子中的链接。 <span style="color:red;">确认外部作者能否对 Microsoft 内容运行 Web 分析。 </span>借助 Web 分析工具，你可以判断是否有任何可能需要以这种方式管理的流量较高的入站链接。

## 第 2 步：从技术存储库中删除指向文章的所有交叉链接
<span style="color:red;">测试在存储库中查找交叉链接的过程。</span>
1. 确保你是在最新的本地分支中操作：运行 `git pull origin master`（或此命令的相应变体）。

2.  <span style="color:red;">确认存储库中的路径。</span>扫描 \EMDocs\Solutions 和 \EMDocs\Token 文件夹，确定其中是否有任何文章和标记链接到你要停用的文章。如果有，请删除这些交叉链接，或将它们替换为相应的新交叉链接。 如果你已安装搜索和替换实用工具，则可以使用此工具来查找交叉链接。 如果你没有安装，则可以免费使用 Windows PowerShell。 下面介绍了如何使用 PowerShell 来查找交叉链接：

 a. 启动 Windows PowerShell。

 b. 在 PowerShell 提示符处，将文件夹更改为 \EMDocs\Solutions：

 `cd \EMDocs\Solutions`

 c. 键入以下命令，以列出引用了你要删除的文章的所有文件：

 `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name`

  如果你想将包含文件名的列表发送到文本文件（例如，名为 psoutput.txt 的文本文件）中，你可以：

  `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name | Out-File C:\Users\<your account>\psoutput.txt`

3. 添加并提交所有更改，将它们推送到源，然后创建拉取请求，将所做的更改从源移到主存储库的主分支中。

## 第 3 步：删除所有交叉链接 
<span style="color:red;">确认外部作者能否删除交叉链接。 </span>
如果<span style="color:red;">确认 EMS 文档的 URL。 </span> http://docs.microsoft.com/ems 中的其他网页对文章进行了交叉引用，你需要删除交叉引用，然后视情况为已停用的网页创建重定向。 对于此部分，你需要与负责维护和更新服务的文档登录页的人员合作。 如果你不知道此人是谁，请与你的内容团队合作伙伴联系。 负责维护和更新文档登录页的人员需要执行以下两项操作：

1. 在 Visual Studio 中，扫描**整个** EMS Web 解决方案，确定其中是否存在对要停用的文件的交叉引用。 删除交叉引用，或将其替换为更新后的交叉引用。 你需要删除 HTML 链接及其相关资源字符串。 

2. <span style="color:red;">确认外部作者能否创建重定向。</span>如果存在替换文章，请创建重定向，将访问者转到此文章。 

3. 将更改签入存储库。

## 第 4 步：停用文章
<span style="color:red;">确认外部作者能否从存储库中删除文章。</span>
在你完成前三步并且这些更改生效后，你可以从存储库中删除文章。

## 第 5 步：从搜索引擎中删除缓存页
<span style="color:red;">确认外部作者能否请求从搜索引擎中删除 Microsoft 内容。</span>
只有当因法律问题或严重的客户问题而需要快速删除内容时，才执行此步操作。 普通优先级页删除应仅由自然搜索引擎进程来处理。 转到下面这些网页，从搜索引擎中删除缓存网页：

[必应](https://www.bing.com/webmaster/tools/content-removal?rflid=1)
[Google](https://www.google.com/webmasters/tools/removals?pli=1)


### 返回主页

- [概述文章](./../README.md)
- [指南文章的索引](./contributor-guide-index.md)


<!--HONumber=Mar16_HO2-->


