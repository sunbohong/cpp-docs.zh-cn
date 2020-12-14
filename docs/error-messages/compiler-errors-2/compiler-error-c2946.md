---
description: 了解更多：编译器错误 C2946
title: 编译器错误 C2946
ms.date: 11/04/2016
f1_keywords:
- C2946
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
ms.openlocfilehash: 7a74b17c10acd55a254c0d7fba5c8269689e3094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249498"
---
# <a name="compiler-error-c2946"></a>编译器错误 C2946

显式实例化；“类”不是模板类专用化

不能显式实例化非模板化的类。

## <a name="example"></a>示例

下面的示例生成 C2946。

```cpp
// C2946.cpp
class C {};
template C;  // C2946
int main() {}
```
