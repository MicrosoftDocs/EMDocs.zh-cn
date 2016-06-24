<properties pageTitle="企业移动性套件技术文章的元数据" description="说明文章所需的元数据。" metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="required" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/24/2016" ms.author="v-jocgar" />

# 企业移动性套件技术文章的元数据

步骤如下： 
- [ ] #11 确认每个属性的说明是否正确。
- [ ] #12 确认 Properties:Description 部分中的 URL。
- [ ] #13 更新服务列表和值的 ms-service 列表（请参阅 RobMazz 电子邮件 #3 2016-02-18）。
- [ ] #14 确认 Properties:Tags 部分中的 URL（EMS 文章的位置）。
- [ ] #15 确认 Properties:Tags 中的可选标记的短列表 (3)。 应该有更多个标记？ 
- [ ] #16 确认 Tags:ms-services 部分中的服务列表。
- [ ] #17 更新 Tags:mstopic 部分中文章类型（资源类型）的列表（RobMazz 电子邮件 #1 2016-02-18）。
- [ ] #18 更新并批准 Tags:ms.devlang 部分中的编程语言列表（RobMazz 电子邮件 #4 2016-02-18）。
- [ ] #19 确认 Tags:ms.tgt_pltfrm 部分中的目标平台的列表（RobMazz 电子邮件 #2 2016-02-18）。
- [ ] #20 确认所有链接（尤其是定位标记）都正常工作。 

所有的 EMS 技术文章包含两个元数据部分：“属性”部分和“标记”部分。 “属性”部分启用某些网站自动化和 SEO 内容，而“标记”部分启用大量内部内容报告。 这两个部分都是必需的。

- [语法]
- [使用情况]
- [属性和“属性”部分的值]
- [属性和“标记”部分的值]

## 语法

“属性”部分使用以下语法：

    <properties
       pageTitle="Page title that displays in search results and the browser tab | Microsoft EMS"
       description="Article description that will be displayed on landing pages and in most search results"
       services="service-name"
       documentationCenter="dev-center-name"
       authors="GitHub-alias-of-only-one-author"
       manager="manager-alias"
       editor=""
       tags="optional"
       keywords="Separate terms with commas. Check with your SEO champ before you change content in this article containing these terms."/>

“标记”部分使用以下语法：

    <tags
       ms.service="required"
       ms.devlang="may be required"
       ms.topic="article"
       ms.tgt_pltfrm="may be required"
       ms.workload="na"
       ms.date="mm/dd/yyyy"
       ms.author="Your MSFT alias or your full email address;semicolon separates two or more"/>

## 使用

- 元素名称和属性名称区分大小写。
- “属性”部分必须是你的文件的第一行。
- 每个元数据部分之后和你的页面标题之前留一个空白行，以确保页面标题在发布过程中正确转换为 HTML。

## 属性和“属性”部分的值

![](./media/checkmark-small.png)**pageTitle**：必需；对 SEO 很重要。 此属性的文本将显示在浏览器选项卡中，并在搜索结果中以标题形式显示。 使用 55-60 个字符，包括空格和站点标识符 *| Microsoft EMS*（键入为：空格竖线空格 Microsoft EMS）。  pageTitle 应与 H1 不同。

![](./media/checkmark-small.png)**description**：必需；对 SEO（相关性）和网站功能很重要。 说明的长度至少应为 125 个字符，最多为 155 个字符（包含空格）。 说明你的内容的目的，以便客户从搜索结果列表中了解是否应选择你的内容。 值为：

- 此文本可能在 Google 搜索结果中显示为说明或摘要段落。
- 此文本显示在<span style="color:red;">确认 URL</span> [文章索引结果](http://docs.microsoft.com/ems/articles/)中。

![](./media/checkmark-small.png)**services**：介绍服务的文章所必需的。 此值通常称为“服务 slug”。 列出所有适用的服务，用逗号隔开。 你列出的第一项服务将决定页面的导航痕迹以及与页面一起显示的左侧导航。

在指定 services 值和 documentationCenter 值的文章中，services 值将决定痕迹。 你列出的其他值将显示为已发布文章中的标记。 值：

- active-directory
- active-directory-b2c
- active-directory-ds
- app-service-api
- api-management
- app-service
- app-service-mobile
- app-service-web
- application-gateway
- application-insights
- 自动化
- 备份
- 批处理
- best-practice
- 计费
- biztalk-services
- 缓存
- cdn
- cloud-services
- data-catalog
- data-factory
- data-lake-analytics
- data-lake-store
- devtest-lab
- dns
- documentdb
- expressroute
- event-hubs
- hdinsight
- iot-hub
- key-vault
- load-balancer
- machine-learning
- marketplace
- media-services
- mobile-engagement
- mobile-services
- multi-factor-authentication
- notification-hubs
- operational-insights
- operations-management-suite
- powerapps
- recovery-manager
- redis-cache
- remoteapp
- rights-management
- 计划程序
- 搜索
- security-center
- service-bus
- service-fabric
- site-recovery
- sql-database
- sql-data-warehouse
- sql-reporting
- 存储
- 存储
- storsimple
- stream-analytics
- traffic-manager
- virtual-machines
- virtual-network
- visual-studio-online
- vpn-gateway
- web-sites

![](./media/checkmark-small.png)**documentationCenter**：通过开发人员中心重点突出的以开发为中心的文章所必需的。 指定适用于文章的单个开发人员中心或语言。 你列出的值将决定页面的导航痕迹。 在指定 services 值和 documentationCenter 值的文章中，services 值将决定痕迹。 值：

- **.net**
- **nodejs**
- **java**
- **php**
- **python**
- **ruby**
- **mobile**：已弃用。 替换为特定移动平台。
- **ios**：验证此新值
- **android**：验证此新值
- **windows**：验证此新值
- **xamarin**：验证此新值

![](./media/checkmark-small.png)**authors**：必需，只有一个值。 列出主要作者或文章 SME 的 GitHub 帐户。 此属性决定已发布文章的作者署名。 只列出一个，不考虑该属性的复数名称。

![](./media/checkmark-small.png)**manager**：如果你是 Microsoft 参与者，则为必需。 列出技术领域的内容发布管理者的电子邮件别名。 如果你是社区参与者，请包含该属性，但将其留空，以便我们可以进行填写。

![](./media/checkmark-small.png)**editor**：不使用。 不要使用它用于其他目的。

![](./media/checkmark-small.png)**tags**：可选。 仅在以下情况下包含此项：你想要在此文章索引页的文章痕迹下启用一个指向与已批准值之一匹配的文章的预筛选列表的链接<span style="color:red;">确认 URL</span> (http://docs.microsoft.com/ems/articles/)。 当内容分组不是特定于服务时，这些值旨在提供将内容分组到一起的方式。 这些标记还可以提供指示该文章适用的技术堆栈的标签。 此值**不**支持自由格式标记或哈希标记；必须在站点上启用标记。 你可以对一个文章提供用逗号分隔的多个标记值。 批准的值是：

<span style="color:red;">确认这些标记值</span>
  - 体系结构
  - 计费
  - mysql

![](./media/checkmark-small.png)**keywords**：可选。 仅供 SEO champ 使用。 用逗号分隔术语。 **更改或删除这篇文章中包含这些术语的内容之前，请与 SEO champ 确认。** 此属性记录 SEO champ 已锁定为目标并且正在跟踪的关键字以提高搜索排名。 关键字不以发布的 HTML 呈现。 验证不需要此属性。

## 属性和“标记”部分的值

![](./media/checkmark-small.png)**ms.service**：必需。 指定该文章适用的服务、工具或功能。 每页一个值。

 如果页面适用于多个服务，选择最直接适用的服务；例如，使用网站上承载的应用来演示 Service Bus 功能的文章都应有 **service-bus** 值，而不是 **web-sites** 值。 如果页面同等地适用于多个服务，请选择 **multiple**。 如果页面不适用于任何服务（不常见），请选择 **NA**。

<span style="color:red;">确认这些值。</span>
 - **active-directory**
 - **api-management**
 - **app-service**：仅适用于有关 App Service 的一般概念性材料。
 - **app-service-api**
 - **app-service-logic**
 - **app-service-mobile**
 - **app-service-web**
 - **application-insights**
 - **自动化**
 - **备份**
 - **批处理**
 - **biztalk-services**
 - **计费**
 - **缓存**
 - **cdn**
 - **cloud-services**
 - **expressroute**
 - **hdinsight**
 - **iot-hub**
 - **key-vault**
 - **machine-learning**
 - **media-services**
 - **mobile-engagement**
 - **mobile-services**
 - **multi-factor-authentication**
 - **multiple**：该页面同等地适用于多个服务
 - **na**：该页面不适用于任何服务（不常见）
 - **notification-hubs**
 - **operational-insights**
 - **powerapps**
 - **recovery-manager**
 - **redis-cache**
 - **remoteapp**
 - **rights-management**
 - **计划程序**
 - **service-bus**
 - **service-fabric**
 - **site-recovery**：以前为 recovery-services
 - **sql-database**
 - **sql-data-warehouse**
 - **sql-reporting**
 - **存储**
 - **storsimple**
 - **traffic-manager**
 - **virtual-machines**
 - **virtual-network**
 - **visual-studio-online**
 - **vpn-gateway**
 - **web-sites**

![](./media/checkmark-small.png)**ms.devlang**：必需。 指定该文章适用的编程语言。 每页一个值。

 如果页面同等地适用于两种编程语言，请选择 **multiple**。 如果某个页面主要是概念，并且其内容通常也适用于多种编程语言，请选择 **multiple**。 如果页面并非面向开发人员，且与编程语言适用性无关，请选择 **NA**。 使用 **rest-api** 标识 REST API 参考主题。

<span style="color:red;">确认这些值</span>
 - **cpp**
 - **dotnet**
 - **java**
 - **javascript**
 - **multiple**：页面同等地适用于多种编程语言。
 - **na**：页面并非面向开发人员，且不是特定于任何编程语言。
 - **nodejs**
 - **objective-c**
 - **php**
 - **python**
 - **rest-api**
 - **ruby**


![](./media/checkmark-small.png)**ms.topic**：必需。 指定主题类型。 参与者创建的大多数新页面将是文章或引用。

<span style="color:red;">确认这些值</span>
 - **article**：概念性主题、教程、功能指南或其他非引用文章

 - **get-started-article**：分配给服务左侧导航的“入门”部分中突出的文章。

 - **hero-article**：旨在提供某项服务或功能介绍的“hero”教程，该服务或功能可让访问者快速开始使用服务并推动试用注册及 MSDN 激活。 仅将此值分配给在你的服务的文档登录页顶部突出的文章。

 - **reference**：API 引用页面（包括 REST API）或 PowerShell cmdlet 引用页面

![](./media/checkmark-small.png)**ms.tgt_pltfrm**：必需。 指定目标平台，例如 Windows、Linux、Windows Phone、iOS、Android 或特殊缓存平台。 每页一个值。 对于大多数主题，此值将为 **NA**，移动设备和虚拟机除外。

<span style="color:red;">确认这些值</span>
 - **cache-in-role**
 - **cache-multiple**
 - **cache-redis**
 - **cache-service**
 - **cache-shared**
 - **command-line-interface**
 - **ibiza**：使用 Ibiza 门户的内容。 仅当所讨论的功能可跨 Ibiza 门户和当前门户使用时才使用。
 - **mobile-android** 
 - **mobile-html**
 - **mobile-ios**
 - **mobile-kindle**
 - **mobile-multiple**
 - **mobile-nokia-x**
 - **mobile-phonegap**
 - **mobile-sencha**
 - **mobile-windows**
 - **mobile-windows-phone**
 - **mobile-windows-store**
 - **mobile-xamarin**
 - **mobile-xamarin-android**
 - **mobile-xamarin-ios**
 - **multiple**：该页面同等地适用于多个平台
 - **na**：平台说明符不适用于此页
 - **powershell**
 - **vm-linux**
 - **vm-multiple**
 - **vm-windows**
 - **vm-windows-sharepoint**
 - **vm-windows-sql-server**
 - **vs-getting-started**：标识“VS 入门”页面组。 已添加标记 12/1/14。
 - **vs-what-happened**：标识“VS 入门完成的操作”页面。 已添加标记 12/1/14。

![](./media/checkmark-small.png)**ms.workload**：必需。 指定页面适用的工作负载。 每篇文章只有一个值。 

![](./media/checkmark-small.png) **ms.date**：必需。 指定上次查看文章的相关性、准确性、正确屏幕截图和工作链接的日期。 以 mm/dd/yyyy 的格式输入日期。 此日期也以上次更新日期显示在发布文章上。

![](./media/checkmark-small.png) **ms.author**：必需。 指定与该主题相关联的作者。 若要指定多个值，应用分号分隔它们。 Microsoft 别名或完整的电子邮件地址均可接受。 长度不能超过 200 个字符。

## 返回主页

- [概述文章](./../README.md)
- [指南文章的索引](./contributor-guide-index.md)


<!--Anchors-->
[Syntax]: #syntax
[Usage]: #usage
[Attributes and values for the properties section]: #attributes-and-values-for-the-properties-section
[Attributes and values for the tags section]: #attributes-and-values-for-the-tags-section


<!--HONumber=Mar16_HO2-->


