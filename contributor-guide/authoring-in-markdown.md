<properties pageTitle="为 Markdown 中的 EMS 创作" description="说明如何在 markdown 中依据企业移动性套件存储库设置准则来创建映像。" services=""     solutions="" documentationCenter="" authors="v-jocgar" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# 为 Markdown 中的 EMS 创作

步骤如下： 
- [ ] #23 确认 EMS 文章的图像布局 /articles/<service-directory>/media
- [] #24 提供 /articles/<service-directory>/media 的一个示例
- [ ] #25 确认 EMS 文档页面的 3 个段落中的中心列图像的最大宽度（是 580 px 还是 600px？）
- [ ] #26 确认 EMS 是否另有一组概念图符号，而不同于在 http://aka.ms/CnESymbols 免费提供的符号。 
- [ ] #27 确认参与者指南的 URL
- [ ] #28 确认整个链接方案
- [ ] #29 文章是否按服务子目录进行组织？
- [ ] #30 需要确认定位链接的方法
- [ ] #31 确认链接方法和选择器的使用。
- [ ] #32 测试链接方案，以确保其正常运行

本文包含介绍如何编写 EMS 服务和技术的技术文章的指针。 不论你正在创建新文档还是更新现有文档，这些指南均适用。

## 为什么要进行 EMS 相关编写？

Microsoft 企业移动性套件 (EMS) 专为帮助解决当前移动到基于云的集成式移动服务问题而创建。 从一开始便生成作为云服务的三个核心组件 - Microsoft Azure Active Directory Premium、Microsoft Intune 和 Microsoft Azure 权限管理。 它们被设计为可一起使用，提供与市场上任何其他系列不同的集成式技术系列。 为了能检测本地攻击，EMS 还包括了 Microsoft 高级威胁分析。 使用 EMS，企业用户可在你保护公司资产的同时，在他们喜欢的设备上高效工作。

始终将创建单个产品的文档作为优先事项。 但是，由于 EMS 是一套产品，所以我们期待出现更多的文章和操作方法文档，帮助我们的客户更好地使用这些产品。 我们创建跨产品方案的文档，同时我们还欢迎在自己公司内部亲身体验这些产品的员工和用户分享心得体会。

因此，我们已在 Github 上开放我们的文档，你可以采用多种方式进行参与：
- **更正文本错误。** 我们知道，它们很让我们抓狂，但我们却始终抓不到它们，所以让我们通过 Github 团结起来，共同来解决这些问题。
- **建议新的主题。** 如果某个过程或主题由于经常出现而值得作为一个文档主题，而它又是我们所没有的，那么请务必把它写出来，我们将考虑收录它。
- **添加到我们的 FAQ 中。** 如果你发现自己想了解一些我们未涉及的但却是问题/答案而不是整个主题的信息，请将此新增项提交到 FAQ，我们将会进行审核。 

总之，我们知道你有非常好的建议和观点，我们希望能够方便你参与提高 EMS 的总体性能。 

## 更好的文章提示

进行 EMS 相关编写时，请记住以下事项：

**特定于 EMS 的做法**
- 官方产品名称是“Microsoft 企业移动性套件”，但我们几乎总是说“EMS”，比如“EMS 云标识和访问管理”。
- 在服务或功能名称前第一次在引用中使用“EMS”，后面可以省略它（例如在“EMS 云标识和访问管理”首次使用后，可变为“云标识和访问管理”）。 
- EMS 的所有标题均使用区分大小写的句子。 
- 通常情况下，请尽量避免首字母缩写 - 它们只会使人产生混淆。

**书写的最佳做法**
- 使用自然友好的发音 - 就像你与他人一对一式的交谈。 若要了解详细信息，请参阅[样式和声音主题](./style-and-voice.md)。
- 对你的主题进行拼写检查和语法检查，即使你需要文本剪切并粘贴到 Word 中也要这样做。
- 使用简单的句子。 简单的句子更易于理解，也便于人工和机器对其进行翻译。
- 不要使用评论或旁白打断步骤。
- 在列表或代码片段前面的每个句子中包含单词“following”或“as follows”。
- 对于包含代码片段的步骤，请将关于步骤的其他信息作为注释放在代码中。 
    - 这将减少读者需要阅读的文本量。 
    - 将关键信息复制到代码项目中，以便在用户后期对其进行引用时，可提醒用户代码将执行的操作。

## Markdown 常规帮助
- 有关 markdown 常规提示的信息，请参阅 Github 网站上的 [Markdown 基础知识](https://help.github.com/articles/markdown-basics/)。
- 你还可以下载我们的 [EMS Markdown 速查表](./media/ems-markdown-cheat-sheet.pdf?raw=true)。 
- 如果你需要在 markdown 中创建跨链接的文章，请参阅下面的[链接指南](#guidelines-for-linking-technical-articles)。
- 网站<span style="color:red;">确认 URL</span> http://docs.microsoft.com/ems 支持[隔离代码块](https://help.github.com/articles/creating-and-highlighting-code-blocks/#fenced-code-blocks)。 通过在代码块前后的行中插入一行 3 个反引号字符 (```) 来创建隔离代码块。 这是一种将该代码与其余文本分离的简便方法。   
- EMS 还支持在代码块内中使用[语法突出显示](https://help.github.com/articles/creating-and-highlighting-code-blocks/#syntax-highlighting)功能。 但是，与 GitHub 风格的 Markdown 不同：在代码的第一行中[指定某个特定的语言](https://help.github.com/articles/creating-and-highlighting-code-blocks/#syntax-highlighting)会更改语法配色方案；而 EMS 仅支持**一个**语法突出显示配色方案，而不考虑你指定的编程语言。

## 在 Markdown 中创建图像
通过使用简单的 Markdown 语法，你可以将图像包括在文章中。 

### 图像文件夹创建和链接语法

对于新文章，你需要在以下位置创建一个文件夹：
<span style="color:red;">确定文章存储库的图像布局</span>

    /articles/<service-directory>/media/

例如：
<span style="color:red;">提供一个示例</span>

    /articles/identity-access/media/

在创建文件夹并向其添加图像后，使用以下语法在你的文章中创建图像：

```
![Alt image text](./media/your-image-filename.png)
```

## 特定于企业移动性套件的图像准则

如果不能包括重现步骤，则目前建议使用屏幕截图。 请编写你的内容，以使内容可以长久保留而无需屏幕截图（如有必要）。

在创建和包括图片文件时，请使用下列准则：
- 如有可能，请跨文档共享图片文件。 将 URL 复制到所需的文件中，并将其添加到文章中。 
- 可移植网络图形 (.PNG) 文件比其他格式文件更受欢迎。
- 使用画图中提供的默认宽度的红色正方形 (5 px) 引起人们对屏幕截图中特定元素的注意。  

    例如：

    ![这是将红色正方形用作标注的一个示例。](./media/gs13noauth.png)

- 避免屏幕截图的边缘上出现空白区域。 屏幕截图应该有 1 个像素宽的灰色边框，使屏幕截图的白色区域不会融入网页。
    - 如果你采用在边缘处保留白色背景的方式裁剪屏幕截图，请在该图像的周围添加单个像素的灰色边框。  
    - 如果使用画图，则在默认颜色调色板中使用较浅的灰色 (#C3C3C3)。
![灰色边框](./media/grey-border-in-paint.png)     
    - 如果使用的图形应用需要用 RGB 值，颜色值将是 R195、G195、B195。 
- 在 Visio 中，可以在图像周围轻松添加一个灰色边框。 为此，请执行以下操作： 
  - 选择映像。 
  - 选择行，并确保颜色设置正确。 
  - 将线条粗细更改为 1 1/2 pt。  

    **例如：**

    ![这是在空白区域周围使用灰色边框的示例。](./media/agent-700w.png)

- 含空白区域的概念图像不需要灰色边框。  

    **例如：**

    ![这是一个含空白区域且不含灰色边框的概念图像示例。](./media/ic727360.png)

- 尽量不要使图像太宽。 如果太宽，将自动调整图像。 但是，有时调整图像的大小会导致画质模糊不清，因此，我们建议你将图像宽度限制为<span style="color:red;">确认最大图像宽度</span> 580 像素，如有必要，可在提交之前手动调整图像大小。

- 在屏幕截图中显示命令输出。  如果你的文章中包含用户在 shell 中操作的步骤，那么在屏幕截图中显示命令输出的做法会非常有用。 在这种情况下，通常将 shell 宽度限制为大约 72 个字符，这样可确保图像不会超出宽度准则规定的<span style="color:red;">确认最大图像宽度</span> 580 像素。 在输出屏幕截图前，请调整窗口的大小，以便只显示相关的命令和输出（可根据需要在任意一侧使用空行）。
- 在可能的情况下，拍摄含多个窗口的整个屏幕截图。 在拍摄浏览器窗口的屏幕截图时，将浏览器窗口的大小调整到<span style="color:red;">确定最大图像宽度</span> 580 像素宽或更小，并尽量缩短浏览器窗口的高度，以便该窗口适合你的应用程序大小。

    例如：

    ![这是浏览器窗口屏幕截图的一个示例。](./media/helloworldlocal.png)

- 请谨慎使用显示在屏幕截图中的各种信息。 请确保没有泄露公司内部信息或你的个人信息。
- 在概念图或关系图中，使用云和企业符号和图标集中的正式图标。 <span style="color:red;">确认我们使用这些图标</span>http://aka.ms/CnESymbols 中提供了公共集。


## 技术文章链接准则

| 链接方案 | 目标链接指南  |
|---------------|-----------|
|从一篇 EMS 技术文章链接到另一篇 EMS 技术文章|使用相对链接。|
|链接到文档目录之外的 EMS 页，或链接到 MSDN 库主题、TechNet 库主题或知识库文章|​使用指向文章或主题的实际链接。 删除链接中的语言区域设置 en-us。|
|从 EMS 文章链接到任何其他网页|使用直接链接|

### 使用友好的链接文本

在链接中包含的词语应该友好 - 换言之，它们应该是标准的英语单词或将链接到的页面的标题。 不要使用“单击此处”。 这对 SEO 不利，它不能充分描述目标。

**更正：**
<span style="color:red;">确认参与者指南的 URL</span> 
- `For more information, see the [contributor guide index](https://github.com/Microsoft/EMDocs/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**不正确：**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

<span style="color:red;">确认参与者指南的 URL</span> 
- `For more information, click [here](https://github.com/Microsoft/EMDocs/contributor-guide/contributor-guide-index.md).`

### EMS 相对链接的 Markdown 语法
<span style="color:red;">确认整个链接方案</span> 

若要创建从一篇 EMS 技术文章到另一篇 EMS 技术文章的内联链接，请使用此链接格式。 如果你创建任何新链接（来自或指向目录中的文章），将需要遵循新链接的语法。

文章链接（来自某个子目录或指向根目录中的文章）：

    [link text](../article-name.md)

根目录中的文章链接到某个服务子目录中的文章： 
<span style="color:red;">文章是否按服务子目录进行组织？</span>

    [link text](service-directory/article-name.md)

服务子目录中的文章链接到另一个服务子目录中的文章：

    [link text](../service-directory/article-name.md)
 
目录中的文章链接到同一目录中的另一篇文章：

    [link text](article-name.md)


无需再创建其他的锚 - 已在发布时间为所有 H2 标题自动生成锚。 唯一需要做的事情就是创建指向 H2 部分的链接：
<span style="color:red;">需要确认定位链接方法</span>

    [link](#the-text-of-the-H2-section-separated-by-hyphens)
    [Create cache](#create-cache)

链接到相同子目录的另一篇文章中的锚：

    [link text](article-name.md#anchor-name)
    [Configure your profile](media-services-create-account.md#configure-your-profile)

链接到另一个服务子目录中的锚：

    [link text](service-directory/article-name.md#anchor-name)
    [Configure your profile](service-directory/media-services-create-account.md#configure-your-profile)


## 自定义 markdown 链接语法
<span style="color:red;">确认链接方法和选择器的使用。</span>

由于包括文件位于另一个目录中，你将需要使用如下相对路径。 对于从包括文件指向单个文章的链接，请使用以下格式：

    [link text](../articles/service-folder/article-name.md)
    
了解有关如何在[自定义 markdown 扩展准则](custom-markdown-extensions.md#includes)中使用包含文件的详细信息。

如果你有一个嵌入在包含文件中的选择器，则应使用这种链接： 

    > [EMS.SELECTOR-LIST (Dropdown1 | Dropdown2)]
    - [(Text1 | Example1 )](../articles/service-folder/article-name1.md)
    - [(Text1 | Example2 )](../articles/service-folder/article-name2.md)
    - [(Text2 | Example3 )](../articles/service-folder/article-name3.md)
    - [(Text2 | Example4 )](../articles/service-folder/article-name4.md)

若要链接到 EMS 上的页面（如定价页、服务级别协议页，或任何其他的不是文档文章的页面），请使用绝对 URL，但要省略“en-us”**区域设置。 此处的目标是让链接在 GitHub 中和呈现的站点上工作：

    [link text](https://www.microsoft.com/server-cloud/enterprise-mobility/pricing.aspx)

若要测试你的链接，请将你的页面推送至分叉，在呈现的视图中进行查看，并将其发布到沙盒。 只要分支中存在 URL 的目标，该页面的 GitHub 版本上的跨链接就应正常工作。

## 引用样式链接

使用引用样式链接可使你的源内容易于阅读。 引用样式链接可替换内联链接语法以及允许你将长 URL 移到文章结尾部分的简化语法。 下面是 Daring Fireball 的示例：

内联文本：

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

本文末尾的链接引用：

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/  
    [3]: http://search.msn.com/


## 返回主页

- [文章概述](./../README.md)
- [指南文章的索引](./contributor-guide-index.md)



<!--HONumber=Mar16_HO2-->


