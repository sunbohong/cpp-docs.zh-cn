---
description: 了解详细信息：序列化：序列化对象
title: 序列化：对象的序列化
ms.date: 11/04/2016
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
ms.openlocfilehash: ec0782f7faa0d6400f40013925f4a53495a76c7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217467"
---
# <a name="serialization-serializing-an-object"></a>序列化：对象的序列化

[序列化：生成可序列](../mfc/serialization-making-a-serializable-class.md)化的类演示如何使类可序列化。 具有可序列化的类后，可以通过 [CArchive](../mfc/reference/carchive-class.md) 对象将该类的对象序列化到文件和从文件序列化。 本文介绍：

- [CArchive 对象是什么](../mfc/what-is-a-carchive-object.md)。

- [创建 CArchive 的两种方法](../mfc/two-ways-to-create-a-carchive-object.md)。

- [如何使用 CArchive <\< and >> 运算符](../mfc/using-the-carchive-output-and-input-operators.md)。

- [通过存档存储和加载 cobject](../mfc/storing-and-loading-cobjects-via-an-archive.md)。

您可以让框架为您的可序列化文档创建存档或自己显式创建 `CArchive` 对象。 \< and >在某些情况下，可以使用或的 <> 运算符 `CArchive` （在某些情况下，通过调用 `Serialize` `CObject` 派生类的函数）在文件和可序列化对象之间传输数据。

## <a name="see-also"></a>请参阅

[序列化](../mfc/serialization-in-mfc.md)
