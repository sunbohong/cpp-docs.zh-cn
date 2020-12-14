---
description: 详细了解：编译器警告 (级别 4) C4001
title: 编译器警告 (等级 4) C4001
ms.date: 11/04/2016
f1_keywords:
- C4001
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
ms.openlocfilehash: c28c1391b120983d72dc6e5b7a96faa937ee2598
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262212"
---
# <a name="compiler-warning-level-4-c4001"></a>编译器警告 (等级 4) C4001

使用了非标准扩展 "单行注释"

> [!NOTE]
> Visual Studio 2017 版本15.5 中已删除此警告，因为单行注释在 C99 中是标准的。

单行注释是 c + + 中的标准，从 C99 开始，C 中的标准。
在严格 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 上，包含单行注释的 C 文件将生成 C4001，因为使用了非标准扩展。 由于单行注释在 c + + 中是标准的，因此在 (/Ze) 编译时，包含单行注释的 C 文件不会生成 C4001。

## <a name="example"></a>示例

若要禁用警告，请取消注释 [#pragma 警告 (disable： 4001) ](../../preprocessor/warning.md)。

```cpp
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```
