---
description: 详细了解：编译器警告 (级别 4) C4289
title: 编译器警告（等级 4）C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: c0b82702195aa7f5dcd88cd4e9bffbc1bbd1769f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294608"
---
# <a name="compiler-warning-level-4-c4289"></a>编译器警告（等级 4）C4289

使用了非标准扩展 :“var”: 在 for 循环中声明的循环控制变量用在了 for 循环范围外

使用 [/ze](../../build/reference/za-ze-disable-language-extensions.md) 和 **/zc： forScope** 进行编译时，在 [for](../../cpp/for-statement-cpp.md) 循环中声明的变量在 **`for`** -循环范围后使用。

有关如何在带有/Ze 的循环中指定标准行为的信息，请参阅 [/zc： forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) **`for`** 。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

下面的示例生成 C4289：

```cpp
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```
