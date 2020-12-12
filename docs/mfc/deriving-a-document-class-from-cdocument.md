---
description: 了解详细信息：从 CDocument 派生文档类
title: 从 CDocument 派生文档类
ms.date: 11/04/2016
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
ms.openlocfilehash: 9f6dccb5400ba0e62b2f11a3c2d4074cb9bb2f25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327886"
---
# <a name="deriving-a-document-class-from-cdocument"></a>从 CDocument 派生文档类

文档包含和管理应用程序的数据。 若要使用 MFC 应用程序向导提供的文档类，您必须执行以下操作：

- `CDocument`为每种类型的文档从派生一个类。

- 添加成员变量以存储每个文档的数据。

- 重写 `CDocument` 的 `Serialize` 文档类中的成员函数。 `Serialize` 在磁盘上写入和读取文档的数据。

## <a name="other-document-functions-often-overridden"></a>经常重写的其他文档函数

您可能还需要重写其他 `CDocument` 成员函数。 具体而言，通常需要重写 [OnNewDocument](reference/cdocument-class.md#onnewdocument) 和 [OnOpenDocument](reference/cdocument-class.md#onopendocument) ，以初始化文档的数据成员和 [DeleteContents](reference/cdocument-class.md#deletecontents) ，以销毁动态分配的数据。 有关可重写成员的信息，请参阅 *MFC 参考* 中的 [CDocument](reference/cdocument-class.md)类。

## <a name="see-also"></a>请参阅

[使用文档](using-documents.md)
