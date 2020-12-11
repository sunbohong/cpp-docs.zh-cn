---
description: 了解详细信息：用文档数据变量管理数据
title: 使用文档数据变量管理数据
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
ms.openlocfilehash: d05bfe71d080c08b3e0f3bbd416421e612b5d7ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112201"
---
# <a name="managing-data-with-document-data-variables"></a>使用文档数据变量管理数据

将文档的数据实现为文档类的成员变量。 例如，自由曲线程序声明类型的数据成员， `CObList` 这是用于存储指向对象的指针的链接列表 `CObject` 。 此列表用于存储构成手绘直线绘图的点的数组。

如何实现文档的成员数据取决于应用程序的性质。 为帮助您解决问题，MFC 提供了一组 "集合类"-数组、列表和映射 (字典) ，包括基于 c + + 模板的集合，以及封装各种常见数据类型（如、、、和）的类 `CString` `CRect` `CPoint` `CSize` `CTime` 。 有关这些类的详细信息，请参阅 *MFC 参考* 中的 [类库概述](class-library-overview.md)。

定义文档的成员数据时，通常会将成员函数添加到文档类，以设置和获取数据项，并对它们执行其他有用的操作。

视图通过使用视图指针访问文档对象，该文档在创建时安装在视图中。 可以通过调用成员函数在视图的成员函数中检索此指针 `CView` `GetDocument` 。 请确保将此指针转换为您自己的文档类型。 然后，可以通过指针访问公共文档成员。

如果频繁地传输数据需要直接访问，或者您想要使用 document 类的非公共成员，则可能需要使您的视图类成为文档类的 c + + 条款) 中的 friend (。

## <a name="see-also"></a>请参阅

[使用文档](using-documents.md)
