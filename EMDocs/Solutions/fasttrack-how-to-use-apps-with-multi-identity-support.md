---
title: 如何使用具有多身份标识支持的应用程序
description: 如何使用具有多身份标识支持的应用
keywords: ''
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: 586ecd93-b097-42a0-9229-bcf3b781021c
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: 93c2572546cab512623cb96412ee064da8a3c233
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196434"
---
# <a name="how-to-use-apps-with-multi-identity-support"></a>如何使用具有多身份标识支持的应用

在本方案中，我们以 Microsoft Word 为例。 你可以将这些相同步骤应用到 Office 365 中的其他应用中。

1. 在你的设备上打开“Word”  应用。 此示例使用的是 iOS 设备。
2. 点击“新建”创建新的 Word 文档。

   ![显示用户选择“新建”以开始创建 Word 文档的屏幕截图。](./media/ft-multiID-1-createDoc.png)

3. 输入所选的句子，然后点击“保存”。 将显示两个存储位置选项：个人位置和工作位置。 由于尚未确定该文档是工作用途还是个人用途，因此本阶段中的应用策略并不处于活动状态。

   ![显示用户在新建 Word 文档中键入句子的屏幕截图。](./media/ft-multiID-2-saveDoc.png)

4. 将该文档保存到你的“工作位置”，例如 OneDrive for Business。 由于 OneDrive for Business 被识别为工作位置，因此文档现在被标记为公司数据，并且将应用策略限制。
5. 现在，打开刚刚保存到工作位置的文档，然后复制文本。 打开个人“Facebook”帐户并尝试粘贴复制的文本。 你应无法将该内容粘贴到新的 Facebook 帖子中。 粘贴选项并不灰显，但当按“粘贴” 时没有任何反应。 这是因为策略限制阻止在个人应用中共享企业数据。

   ![显示用户从 Word 文档复制文本的屏幕截图。 ](./media/ft-multiID-3-copyText.png)

   ![显示用户未能成功将文本粘贴到 Facebook 中的屏幕截图。](./media/ft-multiID-4-pasteInFB.png)
6. 接下来，重复步骤 2 和步骤 3，再创建一个新的 Word 文档。 键入所选的句子，这次将其保存至个人位置，例如 **OneDrive - 个人**。 该文档被标记为个人文档，并且不会应用企业策略限制。

   ![显示用户将句子键入新建 Word 文档的屏幕截图。](./media/ft-multiID-5-createDoc.png)

7. 打开刚刚保存到个人位置的文档，然后复制文本。 再次打开“Facebook”并粘贴复制的文本。 由于该文档被标记个人文档，因此你能够将其内容粘贴到 Facebook 帖子中。

   ![显示用户将文本成功粘贴到 Facebook 中的屏幕截图。](./media/ft-multiID-6-copyText.png)

## <a name="want-to-learn-more"></a>了解更多信息？

请参阅 [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)（企业移动性 + 安全性）。
