---
description: 了解详细信息：初始化文档和视图
title: 初始化文档和视图
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
ms.openlocfilehash: ea0840faefac0ae5a8b4cee0fe3b707a92737c70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208029"
---
# <a name="initializing-documents-and-views"></a>初始化文档和视图

文档以两种不同的方式创建，因此您的文档类必须支持这两种方式。 第一种方式，用户可以使用“文件”-&gt;“新建”命令创建一个新的空白文档。 在这种情况下，请在替代类[CDocument](reference/cdocument-class.md)的[OnNewDocument](reference/cdocument-class.md#onnewdocument)成员函数的重写中初始化该文档。 第二种方式，用户可以使用“文件”菜单上的“打开”命令来创建一个内容读取自某个文件的新文档。 在这种情况下，请初始化类的 [OnOpenDocument](reference/cdocument-class.md#onopendocument) 成员函数的重写中的文档 `CDocument` 。 如果两个初始化操作相同，则可以从这两个重写中调用一个公用成员函数，或者 `OnOpenDocument` 可以调用 `OnNewDocument` 来初始化一个干净的文档，然后完成打开操作。

创建文档之后，将创建视图。 初始化视图的最佳时机是在框架创建完文档、框架窗口和视图之后。 您可以通过重写[CView](reference/cview-class.md)的[OnInitialUpdate](reference/cview-class.md#oninitialupdate)成员函数来初始化您的视图。 如果需要在文档每次更改时重新初始化或调整任何内容，则可以重写 [OnUpdate](reference/cview-class.md#onupdate)。

## <a name="see-also"></a>请参阅

[初始化和清理文档和视图](initializing-and-cleaning-up-documents-and-views.md)
