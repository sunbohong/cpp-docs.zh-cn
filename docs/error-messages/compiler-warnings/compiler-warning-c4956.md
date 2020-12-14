---
description: 了解更多：编译器警告 C4956
title: 编译器警告 C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: 4a92c6329bf4cdd764fd7f419d8011d4dfde0202
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314836"
---
# <a name="compiler-warning-c4956"></a>编译器警告 C4956

> "*type*"：此类型是不可验证的

## <a name="remarks"></a>备注

当指定了 [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) 而你的代码包含不可验证的类型时，将生成此警告。 **/Clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

有关详细信息，请参阅 [纯代码和可验证代码 (c + +/cli) ](../../dotnet/pure-and-verifiable-code-cpp-cli.md)。

此警告作为错误发出，可通过 [warning](../../preprocessor/warning.md) 杂注或 [/wd](../../build/reference/compiler-option-warning-level.md) 编译器选项禁用该警告。

## <a name="example"></a>示例

下面的示例生成 C4956：

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```
