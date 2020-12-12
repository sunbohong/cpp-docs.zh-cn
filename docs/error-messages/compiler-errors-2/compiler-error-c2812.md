---
description: 了解更多：编译器错误 C2812
title: 编译器错误 C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: d59105397ae773c2a46b04a64eb50da3055c3a4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278412"
---
# <a name="compiler-error-c2812"></a>编译器错误 C2812

> \#/clr： pure 和/clr： safe 不支持导入

## <a name="remarks"></a>备注

**/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

不支持使用 **/clr： pure** 和 **/clr： safe** [#import 指令](../../preprocessor/hash-import-directive-cpp.md)，因为 `#import` 需要使用本机编译器支持库。

## <a name="example"></a>示例

下面的示例生成 C2812。

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```
