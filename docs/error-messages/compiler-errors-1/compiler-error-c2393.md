---
description: 了解更多：编译器错误 C2393
title: 编译器错误 C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: 7cf1b333afac9f976bb4bf38ce769e6982255959
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318983"
---
# <a name="compiler-error-c2393"></a>编译器错误 C2393

> "*symbol*"：不能在段 "*segment*" 中分配每个 appdomain 的符号

## <a name="remarks"></a>备注

**/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

使用 [appdomain](../../cpp/appdomain.md) 变量意味着使用 **/clr： pure** 或 **/clr： safe** 进行编译，并且安全或纯映像不能包含数据段。

有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md) 。

## <a name="example"></a>示例

下面的示例生成 C2393。 若要解决此问题，请不要创建数据段。

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```
