---
description: 了解更多：编译器错误 C2286
title: 编译器错误 C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 89c8b69c42188d448fad0cd08287773d7a713d08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298456"
---
# <a name="compiler-error-c2286"></a>编译器错误 C2286

指向 "identifier" 表示形式成员的指针已设置为 "继承"-声明已忽略

类存在两个不同的指向成员的指针表示形式。

有关详细信息，请参阅 [继承关键字](../../cpp/inheritance-keywords.md)。

## <a name="example"></a>示例

下面的示例生成 C2286：

```cpp
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```
