---
description: 了解详细信息： MFC 中的序列化
title: MFC 中的序列化
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: 278de59c6e091fd59826622553f50503b12602bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217570"
---
# <a name="serialization-in-mfc"></a>MFC 中的序列化

本文介绍了 Microsoft 基础类库 (MFC) 中提供的序列化机制，以允许对象在程序运行之间保持不变。

序列化是在持久存储介质（如磁盘文件）中写入或读取对象的过程。 序列化适用于需要在程序执行期间或之后维护结构化数据 (（如 c + + 类或结构) ）的状态的情况。 如果使用 MFC 提供的序列化对象，则可以以标准且一致的方式进行此操作，从而使用户不必手动执行文件操作。

MFC 为类中的序列化提供内置支持 `CObject` 。 因此，从派生的所有类 `CObject` 都可以利用 `CObject` 的序列化协议。

序列化的基本思路是，对象应该能够将其当前状态（通常由其成员变量的值指示）写入持久存储。 稍后，可以通过从存储区中读取或反序列化对象的状态，重新创建对象。 序列化处理对象指针的所有详细信息以及对序列化对象时所使用的对象的循环引用。 关键点在于对象本身负责读取和写入其自己的状态。 因此，要使类可序列化，它必须实现基本的序列化操作。 如序列化项目组中所示，可以轻松地将此功能添加到类中。

MFC 使用类的对象 `CArchive` 作为要序列化的对象和存储介质之间的中介。 此对象始终与 `CFile` 对象关联，从中获取序列化所需的信息，包括文件名以及请求的操作是读取还是写入。 执行序列化操作的对象可以使用对象， `CArchive` 而不考虑存储介质的本质。

`CArchive`对象使用重载插入 (**<\<**) and extraction (**>>**) 运算符来执行写入和读取操作。 有关详细信息，请参阅文章序列化：序列化对象中的 [通过存档存储和加载 cobject](../mfc/storing-and-loading-cobjects-via-an-archive.md) 。

> [!NOTE]
> 不要将 `CArchive` 类与通用 iostream 类（仅用于格式化文本）混淆。 `CArchive`类适用于二进制格式序列化的对象。

如果需要，可以跳过 MFC 序列化，为永久性数据存储创建自己的机制。 你将需要在用户的命令中重写启动序列化的类成员函数。 请参阅 ID_FILE_OPEN、ID_FILE_SAVE 和 ID_FILE_SAVE_AS 标准命令的 [技术说明 22](../mfc/tn022-standard-commands-implementation.md) 中的讨论。

以下文章介绍了序列化所需的两项主要任务：

- [序列化：生成可序列化的类](../mfc/serialization-making-a-serializable-class.md)

- [序列化：序列化对象](../mfc/serialization-serializing-an-object.md)

序列化 [：序列化与数据库输入/输出](../mfc/serialization-serialization-vs-database-input-output.md) 一文介绍了在数据库应用程序中，序列化是适当的输入/输出技术。

## <a name="see-also"></a>请参阅

[概念](../mfc/mfc-concepts.md)<br/>
[常规 MFC 主题](../mfc/general-mfc-topics.md)<br/>
[CArchive 类](../mfc/reference/carchive-class.md)<br/>
[CObject 类](../mfc/reference/cobject-class.md)<br/>
[CDocument 类](../mfc/reference/cdocument-class.md)<br/>
[CFile 类](../mfc/reference/cfile-class.md)
