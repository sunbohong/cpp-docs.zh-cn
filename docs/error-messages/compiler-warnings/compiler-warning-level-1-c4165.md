---
description: 了解详细信息：编译器警告 (等级 1) C4165
title: 编译器警告 (等级 1) C4165
ms.date: 11/04/2016
f1_keywords:
- C4165
helpviewer_keywords:
- C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
ms.openlocfilehash: 7b82db7421493b1687b35e61da988b68a577e8a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267035"
---
# <a name="compiler-warning-level-1-c4165"></a>编译器警告 (等级 1) C4165

"HRESULT" 正在转换为 "bool";是否确实要这样做？

在 [if](../../cpp/if-else-statement-cpp.md) 语句中使用 hresult 时，hresult 将转换为 [布尔](../../cpp/bool-cpp.md) 值，除非显式将该变量测试为 HRESULT。 默认情况下，此警告处于关闭状态。

## <a name="example"></a>示例

下面的示例生成 C4165

```cpp
// C4165.cpp
// compile with: /W1
#include <windows.h>
#pragma warning(1:4165)

extern HRESULT hr;
int main() {
   if (hr) {
   // try either of the following ...
   // if (FAILED(hr)) { // C4165 expected
   // if (hr != S_OK) {
   }
}
```
