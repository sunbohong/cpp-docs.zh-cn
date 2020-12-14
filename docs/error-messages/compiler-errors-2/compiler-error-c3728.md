---
description: 了解更多：编译器错误 C3728
title: 编译器错误 C3728
ms.date: 11/04/2016
f1_keywords:
- C3728
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
ms.openlocfilehash: 0cfcbd38928a153e3f5a58c1ec66b7e1c5bfd08d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245091"
---
# <a name="compiler-error-c3728"></a>编译器错误 C3728

"event"：事件没有引发方法

使用一种语言（如 c #）创建的元数据不允许从定义该事件的类的外部引发事件， [#using](../../preprocessor/hash-using-directive-cpp.md) 指令附带了，使用 CLR 编程的 Visual C++ 程序尝试引发该事件。

若要在以 c # 语言编写的程序中引发事件，则包含事件的类还需要定义引发事件的公共方法。
