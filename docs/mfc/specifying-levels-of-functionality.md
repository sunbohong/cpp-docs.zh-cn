---
description: 了解详细信息：指定功能级别
title: 指定功能级别
ms.date: 11/06/2018
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
ms.openlocfilehash: 1b016cd5a41d3e09790f678a2d49d88df33d9782
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216842"
---
# <a name="specifying-levels-of-functionality"></a>指定功能级别

本文介绍如何将以下级别的功能添加到 [CObject](../mfc/reference/cobject-class.md)派生类：

- 运行时类信息

- 动态创建支持

- 序列化支持

有关功能的一般说明 `CObject` ，请参阅 [从 CObject 派生类一](../mfc/deriving-a-class-from-cobject.md)文。

## <a name="to-add-run-time-class-information"></a>添加运行时类信息

1. 派生类 `CObject` ，如从 [CObject 派生类一](../mfc/deriving-a-class-from-cobject.md) 文中所述。

1. 在类声明中使用 DECLARE_DYNAMIC 宏，如下所示：

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. 在实现文件 ( 中使用 IMPLEMENT_DYNAMIC 宏。类的 CPP) 。 此宏采用类及其基类的名称作为参数，如下所示：

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
> 始终将 IMPLEMENT_DYNAMIC 放 ( 实现文件中。类的 CPP) 。 在编译过程中只应计算 IMPLEMENT_DYNAMIC 宏一次，因此不应在 ( 的接口文件中使用。H) 可能包括在多个文件中。

## <a name="to-add-dynamic-creation-support"></a>添加动态创建支持

1. 从派生类 `CObject` 。

1. 在类声明中使用 DECLARE_DYNCREATE 宏。

1. 定义不带参数的构造函数 (默认构造函数) 。

1. 使用类实现文件中的 IMPLEMENT_DYNCREATE 宏。

## <a name="to-add-serialization-support"></a>添加序列化支持

1. 从派生类 `CObject` 。

1. 重写 `Serialize` 成员函数。

   > [!NOTE]
   > 如果直接调用 `Serialize` ，即不希望通过多态指针序列化对象，则省略步骤3到5。

1. 在类声明中使用 DECLARE_SERIAL 宏。

1. 定义不带参数的构造函数 (默认构造函数) 。

1. 使用类实现文件中的 IMPLEMENT_SERIAL 宏。

> [!NOTE]
> "多态指针" 指向类的对象 () 或从 (说，B) 派生的任何类的对象调用它。 若要通过多态指针进行序列化，框架必须确定它要序列化 (B) 的对象的运行时类，因为它可能是从某个基类派生的任何类的对象 () 。

有关如何在从派生类时启用序列化的详细信息 `CObject` ，请参阅文章 MFC 和[序列化](../mfc/serialization-in-mfc.md)[中的文件](../mfc/files-in-mfc.md)。

## <a name="see-also"></a>请参阅

[从 CObject 派生类](../mfc/deriving-a-class-from-cobject.md)
