<properties title="Create tables in markdown" pageTitle="在 EMS 文章的 Markdown 中创建表" description="说明如何在 Markdown 中对表进行编码。" metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar" />

# 在 Markdown 中创建表

步骤如下：
- [ ] #33 将自定义 Markdown 说明语法添加到下面的说明中。

应尽量少在文章中使用表。 只能在这些数据确实要采用表格形式时才使用表。

**注意**
Markdown 表处理较长文本字符串的能力有限，表格单元格内没有自动换行的概念。 单元格将简单地扩展为完整的内容宽度，这样在较小屏幕上查看表就会有一些困难。 将表用于较小信息集，并找到其他可显示较长内容集的有意义的方式。

## Markdown 表语法
在 Markdown 中创建表的最简单方法是使用竖线和连字符。 每列的第二行中至少需要 3 个连字符才能创建表格表头。 表格表头文本自动居中对齐，并将呈现为加粗文本。  

 ![1]

Markdown 自动呈现可选表行阴影。  
 ![2]

你可以使用冒号来调整列：

  	|:-----|   - this is left aligned (default -- can be omitted)
  	|-----:|   - this is right aligned
  	|:-----:|  - this is centered

外部竖线是可选的，并且无需为了正确呈现表而完全对齐文本和竖线。 快速格式设置的示例：

 ![3]

通过 Markdown 读取并将其正确呈现出来。  
 ![4]

如果你使用 HTML 表，并且两个表之间不呈现你的 Markdown，则需要在结束 TABLE 标记后添加一个结束 BR 标记。

![5]

要想快速方便地在 Markdown 中创建表，请尝试 Markdown 表生成器：http://www.tablesgenerator.com/markdown_tables


## 返回主页

- [概述文章](./../README.md)
- [指南文章的索引](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/table-markdown-1.png
[2]: ./media/table-markdown-2.png
[3]: ./media/table-markdown-3.png
[4]: ./media/table-markdown-4.png
[5]: ./media/break-tables.png


<!--HONumber=Mar16_HO2-->


