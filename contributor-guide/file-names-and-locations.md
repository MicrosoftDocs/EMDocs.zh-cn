<properties pageTitle="EMS 技术文章的文件名和位置" description="介绍了文章的文件结构，以及你在新建文章时应遵循的命名约定。" metaKeywords="" services="" solutions="" documentationCenter="" authors="tysonn" videoId="" scriptId="" manager="required" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# EMS 技术文章的文件名和位置
步骤如下： 
- [ ] #7 拉取服务数据域作为示例
- [ ] #8 确认文件命名模式
- [ ] #9 提供文件命名模式的替换示例
- [ ] #10 确保所有链接（尤其是定位标记）都能正常工作

在技术内容存储库中，我们对所有文章使用一个文件夹（即 **articles** 文件夹）。 因此，没有文件夹层次结构，所有文章都存在于平面文件结构中。 如果创建文件夹并在其中添加文章，那么你的文章将无法发布。

我们不使用文件结构作为组织原则，而是使用严格的文件命名约定，以便明确标识主题，且有助于访问者在 Web 上轻松找到相应文章。

以下为必备知识：

+ [文件命名规则]
+ [文件名模式]
+ [示例]
+ [文件名审批]

## 文件命名规则

- 不得包含空格或标点。 使用连字符分隔文件名中的字词。
- 全部使用小写字母
- 不得超过 80 个字符 - 这是发布系统的限制
- 使用具体的操作动词，如 develop、buy、build、troubleshoot。 不得使用动词的“ing”形式（动名词）。
- 不得使用多义词 - 不得包含 a、and、the、in、or 等。
- 所有文件都必须是 Markdown 文件，并且使用 .md 文件扩展名。

## 文件名模式

以下为一般的命名模式：

<span style="color:red;">需要对此文件命名模式进行确认。</span>
 **service-platform-language-content-product-version.md**

根据此模式中适用的部分，检查存储库中的文章列表，掌握现有名称的情况。 

## 示例
<span style="color:red;"> **需要为 docs.microsoft.com/ems 中的这部分提供替换示例**  </span>

下面是遵循命名模式的有效名称的一些示例：

- cloud-services-dotnet-continuous-delivery.md
- mobile-services-ios-get-started.md
- documentdb-manage-account.md
- mobile-services-dotnet-backend-get-started-settings-sync.md
- active-directory-java-authenticate-users-access-control-eclipse.md
- virtual-machines-install-windows-server-2008r2.md

## 文件名审批

我们的拉取请求审阅者小组负责审阅首次提交到存储库中的新文件的文件名。 拉取请求审阅者应审阅文件名，并提供反馈（如果需要更改文件名的话）。 必须先更正文件名，然后拉取请求才能被接受。 参与者可以轻松地将更新推送到挂起的拉取请求。

## 返回主页

- [概述文章](./../README.md)
- [指南文章的索引](./contributor-guide-index.md)


<!--Anchors-->
[Rules for naming files]: #rules
[File name patterns]: #pattern
[Examples]: #standard-examples
[File name approval]: #file-name-approval


<!--HONumber=Mar16_HO2-->


