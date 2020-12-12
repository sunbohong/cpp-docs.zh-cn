---
description: 了解更多：编译器错误 C3012
title: 编译器错误 C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: fff986a984acb62f770d02ff2b7b08c40e8511e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286002"
---
# <a name="compiler-error-c3012"></a>编译器错误 C3012

> "*固有*"：并行区域内不允许直接使用内部函数

[](../../intrinsics/compiler-intrinsics.md) 区域内不允许使用 `omp parallel` 。 若要解决此问题，请将内部函数移出区域，或将其替换为非内部等效项。

## <a name="example"></a>示例

下面的示例生成 C3012，并显示修复此问题的一种方法：

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```
