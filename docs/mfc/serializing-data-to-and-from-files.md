---
description: 了解详细信息：将数据序列化到文件中
title: 针对文件进行数据序列化
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
ms.openlocfilehash: 58956b2f11b8f0131aae74a6c5b51715fe25c7e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217440"
---
# <a name="serializing-data-to-and-from-files"></a>针对文件进行数据序列化

持久性的基本思路是，对象应该能够将其当前状态（由其成员变量的值指示）写入永久性存储。 稍后，可以通过读取或 "反序列化" 对象在持久性存储区中的状态来重新创建该对象。 此处的关键点在于对象本身负责读取和写入其自己的状态。 因此，要使类成为持久性类，必须实现基本序列化操作。

该框架提供了用于将文档保存到磁盘文件以响应 "文件" 菜单上的 "保存" 和 "另存为" 命令的默认实现，以及用于在响应 "打开" 命令时加载磁盘文件中的文档。 只需很少的工作即可实现文档在文件中写入和读取数据的功能。 您必须执行的主要操作是重写文档类中的 [序列化](../mfc/reference/cobject-class.md#serialize) 成员函数。

MFC 应用程序向导 `CDocument` `Serialize` 在创建的文档类中放置成员函数的主干替代。 实现应用程序的成员变量后，可以 `Serialize` 使用将数据发送到连接到文件的 "存档对象" 的代码来填充替代。 [CArchive](../mfc/reference/carchive-class.md)对象类似于 c + + iostream 库中的 **cin** 和 **cout** 输入/输出对象。 但是， `CArchive` 会写入和读取二进制格式，而不是格式化文本。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [序列化](../mfc/serialization-in-mfc.md)

- [序列化中文档的角色](#_core_the_document.92.s_role_in_serialization)

- [序列化中的数据角色](#_core_the_data.92.s_role_in_serialization)

- [跳过序列化机制](../mfc/bypassing-the-serialization-mechanism.md)

## <a name="the-documents-role-in-serialization"></a><a name="_core_the_document.92.s_role_in_serialization"></a> 序列化中文档的角色

如果实现了文档的成员函数，框架将自动响应 "文件" 菜单的 "打开"、"保存" 和 "另存为" 命令 `Serialize` 。 例如，ID_FILE_OPEN 命令调用应用程序对象中的处理程序函数。 在此过程中，用户将看到并响应 "文件打开" 对话框，框架获取用户选择的文件名。 框架创建一个 `CArchive` 对象集，用于将数据加载到文档中并将存档传递到 `Serialize` 。 框架已打开文件。 文档成员函数中的代码 `Serialize` 通过存档读取中的数据，并根据需要重新构造数据对象。 有关序列化的详细信息，请参阅文章 [序列化](../mfc/serialization-in-mfc.md)。

## <a name="the-datas-role-in-serialization"></a><a name="_core_the_data.92.s_role_in_serialization"></a> 序列化中的数据角色

通常，类类型数据应该能够序列化自身。 也就是说，当你将对象传递给存档时，对象应该知道如何将自身写入存档，以及如何从存档中读取自身。 MFC 提供了以这种方式使类可序列化的支持。 如果您设计一个类来定义数据类型，并且您打算序列化该类型的数据，则为序列化设计。

## <a name="see-also"></a>请参阅

[使用文档](../mfc/using-documents.md)
