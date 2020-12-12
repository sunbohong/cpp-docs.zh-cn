---
description: 了解更多：编译器错误 C3382
title: 编译器错误 C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: 582a807ac43d6110fb0f19aef5806e4118516db2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285651"
---
# <a name="compiler-error-c3382"></a>编译器错误 C3382

不支持将“sizeof”与 /clr:safe 一同使用

**/clr:safe** 编译的输出文件是可验证类型安全的文件，不支持 sizeof ，因为 sizeof 运算符的返回值是 size_t，其大小因操作系统而异。

有关详细信息，请参阅

- [sizeof 运算符](../../cpp/sizeof-operator.md)

- [/cgthreads（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)

- [Visual C++ 64 位迁移的常见问题](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>示例

下面的示例生成 C3382。

```cpp
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```
