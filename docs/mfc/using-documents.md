---
description: 了解详细信息：使用文档
title: 使用文档
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
ms.openlocfilehash: 486604733808fb027d6dd0fbf81bb670c85313f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154495"
---
# <a name="using-documents"></a>使用文档

共同工作，文档和视图：

- 包含、管理和显示特定于应用程序的 [数据](../mfc/managing-data-with-document-data-variables.md)。

- 提供一个接口，该接口包含用于操作数据的 [文档数据变量](../mfc/managing-data-with-document-data-variables.md) 。

- 参与 [写入和读取文件](../mfc/serializing-data-to-and-from-files.md)。

- 参与 [打印](../mfc/role-of-the-view-in-printing.md)。

- [处理](../mfc/handling-commands-in-the-document.md) 应用程序的大多数命令和消息。

文档在管理数据时尤其涉及到。 通常在文档类成员变量中存储数据。 视图使用这些变量来访问要显示和更新的数据。 文档的默认序列化机制管理在文件中读取和写入数据。 文档还可以处理命令 (但不能处理除 WM_COMMAND) 之外的 Windows 消息。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [从 CDocument 派生文档类](../mfc/deriving-a-document-class-from-cdocument.md)

- [使用文档数据变量管理数据](../mfc/managing-data-with-document-data-variables.md)

- [序列化传入和传出文件的数据](../mfc/serializing-data-to-and-from-files.md)

- [跳过序列化机制](../mfc/bypassing-the-serialization-mechanism.md)

- [处理文档中的命令](../mfc/handling-commands-in-the-document.md)

- [OnNewDocument 成员函数](../mfc/reference/cdocument-class.md#onnewdocument)

- [DeleteContents 成员函数](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>请参阅

[文档/视图体系结构](../mfc/document-view-architecture.md)
