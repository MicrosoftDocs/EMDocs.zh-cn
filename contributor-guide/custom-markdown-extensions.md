<properties pageTitle="我们的技术文章中使用的自定义 Markdown 扩展"  description="列出在 docs.microsoft.com/ems 技术文章中启用嵌入视频、说明和提示、可重用内容及其他项的自定义 Markdown 扩展。" services="" solutions="" documentationCenter="" authors="v-jocgar" manager="robmazz" editor=""/>

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar"/>

## EMS 的自定义 Markdown 扩展
步骤如下：
- [ ] #34 确认针对说明、重要事项等使用了 Markdown 扩展。 
- [] #35 确认 EMS 使用标记和正确的目录位置。
- [ ] #36 确认自定义图标文件可用且已安装在正确的位置。
- [ ] #37 确认使用媒体文件的标记的目录名称。
- [ ] #38 确认标记使用的正确过程。
- [ ] #39 提供标记使用的语法示例。 
- [ ] #40 确认 EMS 文档 URL。
- [ ] #41 确认外部编写器可以使用第 9 频道的视频。 
- [ ] #42 确认 EMS 视频在第 9 频道上的位置。
- [ ] #43 确认 EMS 视频在第 9 频道上的使用情况。
- [ ] #44 确认视频嵌入语法。
- [ ] #45 需要 Github 中的一个呈现示例。
- [ ] #46 需要 Github 中的一个视频呈现示例。
- [] #47 需要 EMS 文档网站中的一个呈现示例。 
- [ ] #48 确认选择器对 EMS 文章可用
- [ ] #49 需要一个简单选择器替换示例
- [ ] #50 确认简单选择器语法
- [ ] #51 需要替换简单选择器语法
- [ ] #52 需要一个替换简单选择器示例
- [ ] #53 按说明确认双向选择器函数。
- [ ] #54 需要一个替换双向选择器示例
- [ ] #55 确认双向选择器语法
- [ ] #56 需要一个替换双向选择器示例


## Markdown 常规帮助

如果你还未阅读[为 Markdown 中的 EMS 创作](./authoring-in-markdown.md)主题，我们建议你在继续进行操作之前阅读该主题。 

## 我们的技术文章中使用的自定义 Markdown 扩展

对于大多数文章格式设置（如段落、链接、列表和标题等），我们的文章使用 GitHub 风格的 Markdown。但是，如果 Microsoft.com/ems 上的呈现页面需要更丰富的格式设置，我们会使用自定义 Markdown 扩展。 下面是我们当前正在使用的扩展：

+ [说明和提示]
+ [标记]
+ [嵌入的视频]
+ [技术和平台选择器]

## 说明和提示
<span style="color:red;">确认针对说明、重要事项等使用了 Markdown 扩展。</span>
你可以从四种类型的说明和提示中进行选择：

- EMS.NOTE
- EMS.WARNING
- EMS.TIP
- EMS.IMPORTANT

### 使用
一般情况下，在你的整篇文章中尽量少使用说明和提示。 在你使用时，选择适当的说明或提示类型：

- 使用 EMS.NOTE 突出显示强调或补充主要文本关键点的中性或正面信息。 通过说明提供的信息只适用于特殊情况。

  ![](./media/notes-note.png)

- 使用 EMS.WARNING 就将来可能导致问题的条件向用户发出警告。 例如，选择某个选项或作出某个选择可能会将你永久锁定到某个特定方案。

  ![](./media/notes-warning.png)

- 使用 EMS.TIP 帮助你的用户根据其特定需求应用文本中所述的技术和过程。 提示还会建议可能不太明显的替代方法。 但是，提示并不是基本了解文本所必需的。

  ![](./media/notes-tip.png)

- 使用 EMS.IMPORTANT 提供完成任务所必需的信息。

  ![](./media/notes-important.png)

这些说明和提示都支持代码块、图像、列表和链接，但请尽量将你的说明和提示保持简单明了。 如果你发现自己正在创建带有大量格式设置的复杂说明，那么这可能意味着你需要在文章的主要文本中再增加一节。 而且，如果文章中说明过多，可能会让人分散注意力且难以扫描或阅读。

### 示例 Markdown

所有这些示例都显示 EMS.NOTE。 若要使用提示、警告或重要事项，请替换 Markdown 中的“说明”：

    > [EMS.TIP]

    > [EMS.WARNING]

    > [EMS.IMPORTANT]

单段落：

    > [EMS.NOTE] To complete this tutorial, you must have an active Microsoft account. If you don't have an account, you can create a free account in just a couple of minutes.

多段落：

    > [EMS.NOTE] To complete this tutorial, you must have an active Microsoft account.
    >
    > If you don't have an account, you can [create a free account](https://signup.live.com/signup) in just a couple of minutes.

## 令牌
<span style="color:red;">确认 EMS 正在使用标记和正确的目录位置。</span>
我们的 GitHub 存储库中的可重用文本段落被称为“标记”。 当需要在多个文章中使用文本时，可以包含对 Markdown 文件中文本段落的引用。 文本段落（标记）本身是一个简单的 Markdown (.md) 文件。 它可以包含任何有效的 Markdown，包括文本、链接和图像。 

所有标记 Markdown 文件必须位于存储库根中的<span style="color:red;">确认自定义图标文件可用且已安装在正确的位置。</span>[/tokens 目录]（需要正确的位置）。 在文章发布后，标记文本会无缝集成到已发布的主题中。

- 我们使用特定语法来引用标记。

- 置于标记中的媒体文件必须在特定于此标记的 `/media` 文件夹中创建。 标记的媒体文件夹都属于<span style="color:red;">确认使用媒体文件的标记的目录名称</span> [ems-content/tokens/media 文件夹]（需要正确的位置）。 

## 使用
<span style="color:red;">确认标记使用的正确过程。</span>
- 请在多个文章中需要出现相同文本的地方使用标记。
- 标记旨在用于代表大量内容 - 一段或两段、共享的过程或共享的部分。 不要为小于句子的文本使用标记，标记不用于产品名或不完整的句子。
- 不要在其他标记中嵌入标记。 否则，发布系统会出错！
- 不要在文件之间共享媒体。 为每个标记和文章使用名称唯一的单独文件。 将媒体文件存储在与标记关联的媒体文件夹中。
- 不要将标记用作文章的唯一内容。 标记是为了补充文章其余部分的内容。
- 由于所有标记都必须位于 `/token` 目录中，因此文章标记的路径始终为

    ../token

- 不要在文章和标记中重复链接或图像文件名引用。 将“-token”添加到链接引用或媒体文件名以避免重复引用：

 **链接引用**

 更改前：odata.org
 更改后：odata.org-token

 **图像引用**

 更改前：table.png
 更改后：table-token.png

### 标记的 Markdown 示例
<span style="color:red;">提供使用标记的语法示例。 </span>
用于将标记添加到文档文章的语法如下：

    [EMS.TOKEN [token-short-name](../tokens/token-file-name.md)]

示例

    [EMS.INCLUDE [howto-blob-storage](../tokens/howto-blob-storage.md)]

标记的第一部分是不带路径和不带 .md 扩展的标记名称。 第二部分是 /token 目录中标记的相对路径，带有 .md 扩展。

### 呈现

在呈现的 GitHub 页面中，将呈现标记，如下所示：

 [EMS.TOKEN howto-blob-storage]

在<span style="color:red;">确认 EMS 文档 URL</span> http://docs.microsoft.com/ems 上呈现的 HTML 中，标记的 HTML 会合并到文档 HTML 的其余部分。 但是，HTML 将包含一个带有原始标记 Markdown 文件名和 GitHub 提交哈希的 HTML 注释。 包含此注释是用于故障排除目的，以便可以轻松地在 GitHub 中识别和找到源内容：

  ![](./media/token.png)


## 嵌入的视频
<span style="color:red;">确认外部编写器可以使用第 9 频道的视频。</span>
我们的技术文章支持嵌入视频，只要这些视频位于 Microsoft 的[第 9 频道](http://channel9.msdn.com/)网站上。 第 9 频道的视频必须与<span style="color:red;">确认第 9 频道上 EMS 视频的位置。</span>[docs.microsoft.com 视频中心]（需要实际位置）进行集成。 我们当前不支持嵌入的 YouTube 视频，如果社区参与者想要使用的视频发布在 YouTube 上，欢迎**链接--到 YouTube。

### 使用
<span style="color:red;">确认 EMS 视频在第 9 频道上的使用情况。</span>
- 请确保视频位于第 9 频道视频中心。

- 从第 9 频道视频的友好 URL 复制视频 ID。 例如，位于 [https://channel9.msdn.com/Shows/This+Week+On+Channel+9/TWC9-Stacking-Microsoft-Windows-10-Pi-Bobble-Head-your-Nodejs-and-more](https://channel9.msdn.com/Shows/This+Week+On+Channel+9/TWC9-Stacking-Microsoft-Windows-10-Pi-Bobble-Head-your-Nodejs-and-more) 的视频的视频 ID 为 ** ??? **.

### 语法
<span style="color:red;">确认视频嵌入语法。 </span>
    > [EMS.VIDEO video-id-string]

### 呈现
<span style="color:red;">需要 Github 中的一个视频呈现示例。 </span>
在 GitHub 上：[在 Github 上进行添加时，需要有关文章排版布局的示例](something.md)

<span style="color:red;">需要 EMS 文档网站中的一个呈现示例。 </span>
已发布的文章：[在合并时，需要文档网站上文章排版布局的示例]（需要实际位置）

## 技术和平台选择器
<span style="color:red;">确认选择器可用于 EMS 文章</span>
在撰写同一文章的多种风格时，请在技术文章中使用技术和平台切换器来解决跨技术或平台实现中的差别。 这通常最适用于面向开发人员的移动平台内容。 目前，有两种不同类型的选择器：[简单选择器](#simple-selectors)和[双向选择器](#two-way-selectors)。

由于相同的选择器 Markdown 会进入选定内容中的每个主题，我们建议将你的主题的选择器放置在标记中，然后在使用同一选择器的所有主题中引用该标记。

### 简单选择器

简单（单向）选择器将呈现为标题正下方的一组选项按钮。 当客户需要从单个平台或技术集（如 .NET、Node.js 和 Java）中的主题中进行选择时，可使用这些按钮。  为所有选择器使用自定义 Markdown 扩展，不要为选择器使用 HTML。  

<span style="color:red;">需要一个简单选择器替换示例，将此 Azure 版本留在此处供参考。</span>
请参阅[通知中心入门](http://azure.microsoft.com/documentation/articles/notification-hubs-windows-phone-get-started/)，了解作者如何创建同一文章的 8 个版本，但使用选择器实现跨所有版本进行导航。

![简单选择器示例](./media/selectors.png)

#### 语法
<span style="color:red;">确认简单选择器语法</span>
    > [EMS.SELECTOR]
    - [链接 #1 标签](链接 #1 url)
    - [链接 #2 标签](链接 #2 url)

#### 示例
<span style="color:red;">需要替换简单选择器语法</span>
    > [EMS.SELECTOR]
    - [Windows 运行时 8.1 通用](../articles/notification-hubs-windows-store-dotnet-get-started/)
    - [Windows Phone Silverlight 8.x](../articles/notification-hubs-windows-phone-get-started/)
    - [iOS](../articles/notification-hubs-ios-get-started/)
    - [Android](../articles/notification-hubs-android-get-started/)
    - [Kindle](../articles/notification-hubs-kindle-get-started/)
    - [百度](../articles/notification-hubs-baidu-get-started/)
    - [Xamarin.iOS](../articles/partner-xamarin-notification-hubs-ios-get-started/)
    - [Xamarin.Android](../articles/partner-xamarin-notification-hubs-android-get-started/)
    - [Chrome](../articles/notification-hubs-chrome-get-started/)

#### 呈现

<span style="color:red;">需要一个替换简单选择器示例，将该内容留在此处供参考。</span>
上图显示了 docs.microsoft.com/ems 上的呈现。 在呈现的 GitHub 页面中，选择器呈现为链接的项目符号列表。

### 双向选择器
<span style="color:red;">按说明确认双向选择器函数。</span>
双向选择器允许用户从双向矩阵中选择主题。 在一项诸如移动服务的 EMS 技术支持多个后端平台以及多个客户端时，这是必不可少的。 请记住以下几点：

- 尽管下拉文本被设计为 `(Platform | Backend)`，现在也可对其进行自定义。
- 不需要矩阵中每个点的列表项，但只需要具有其中主题 URL 存在且不为副本的点的项。
- 链接可以是任何 URL，尽管它通常是其他 GitHub 主题。

<span style="color:red;">需要一个替换双向选择器示例，将此 Azure 版本留在此处供参考。</span>
请参阅[移动服务入门](http://azure.microsoft.com/en-us/documentation/articles/mobile-services-ios-get-started/)，了解作者如何创建同一文章的 15 个版本（9 个移动客户端平台和 2 个后端平台），但使用选择器实现跨所有版本进行导航。 请注意，有 3 篇文章不包含这两个后端版本。

![双向选择器示例](./media/selector-list.png)

#### 语法
<span style="color:red;">确认双向选择器语法</span>
    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
    - [(Dropdown1Text1 | Dropdown2Text1 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text1 | Dropdown2Text2 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text2 | Dropdown2Text3 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text3 | Dropdown2Text4 )](../articles/dropdown1-text1-dropdown2-text1.md)

#### 示例
<span style="color:red;">需要一个替换双向选择器示例</span>
    > [AZURE.SELECTOR-LIST (平台 | 后端)]
    - [(iOS | .NET)](./mobile-services-dotnet-backend-ios-get-started-push.md)
    - [(iOS | JavaScript)](./mobile-services-javascript-backend-ios-get-started-push.md)
    - [(Windows 运行时 8.1 通用 | C#)](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows 运行时 8.1 通用 C# | Javascript)](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows Phone | .NET)](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)
    - [(Windows Phone | Javascript)](./mobile-services-javascript-backend-windows-phone-get-started-push.md)
    - [(Android | .NET)](./mobile-services-dotnet-backend-android-get-started-push.md)
    - [(Android | Javascript)](./mobile-services-javascript-backend-android-get-started-push.md)
    - [(Xamarin iOS | Javascript)](./partner-xamarin-mobile-services-ios-get-started-push.md)
    - [(Xamarin Android | Javascript)](./partner-xamarin-mobile-services-android-get-started-push.md)
    - [HTML](../articles/mobile-services-html-get-started/)
    - [PhoneGap](../articles/mobile-services-javascript-backend-phonegap-get-started/)
    - [Sencha](../articles/partner-sencha-mobile-services-get-started/)

#### 呈现
<span style="color:red;">需要一个替换双向选择器示例，将该内容留在此处供参考。</span>
上图显示了 azure.microsoft.com 上的呈现。 在呈现的 GitHub 页面中，选择器呈现为链接的项目符号列表。

<!--Anchors-->
[Notes and tips]: #notes-and-tips
[Tokens]: #tokens
[Embedded videos]: #embedded-videos
[Technology and platform selectors]: #technology-and-platform-selectors

## 返回主页

- [Overview article](./../README.md)
- [Index of guidance articles](./contributor-guide-index.md)


<!--HONumber=Mar16_HO2-->


