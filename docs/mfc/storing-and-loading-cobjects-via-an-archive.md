---
description: 了解详细信息：通过存档存储和加载 Cobject
title: 通过存档存储和加载 CObject
ms.date: 11/04/2016
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: c84c507fc556268eea526c1350211fd4b82f54fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216556"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>通过存档存储和加载 CObject

通过存档存储和加载 `CObject` 需要额外考虑。 在某些情况下，应调用 `Serialize` 对象的函数，其中 `CArchive` 对象是调用的参数，而不是 `Serialize` 使用的 **<\<** or **>>** 运算符 `CArchive` 。 需要记住的重要一点是， `CArchive` **>>** 运算符 `CObject` 基于 `CRuntimeClass` 之前通过存储存档写入文件的信息在内存中构造。

因此，无论你使用的是 `CArchive` **<\<** and **>>** 运算符还是调用 `Serialize` ，都取决于你是否 *需要* 加载存档以便基于以前存储的信息动态重建对象 `CRuntimeClass` 。 `Serialize`在以下情况下使用函数：

- 反序列化对象时，您事先知道对象的确切类。

- 反序列化对象时，已为其分配内存。

> [!CAUTION]
> 如果使用函数加载对象 `Serialize` ，则还必须使用函数来存储对象 `Serialize` 。 不要使用 `CArchive` **<<** 运算符进行存储，然后使用函数加载 `Serialize` ，或者使用函数存储， `Serialize` 然后使用 `CArchive >>` 运算符加载。

下面的示例阐释了这种情况：

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

总之，如果可序列化类将嵌入的定义 `CObject` 为成员，则 *不* 应将 `CArchive` **<\<** and **>>** 运算符用于该对象，但应改为调用 `Serialize` 函数。 此外，如果可序列化的类定义指向 (的指针 `CObject` 或从) 派生的对象 `CObject` 作为成员，但在其自己的构造函数中构造此其他对象，则还应调用 `Serialize` 。

## <a name="see-also"></a>请参阅

[序列化：序列化对象](../mfc/serialization-serializing-an-object.md)
