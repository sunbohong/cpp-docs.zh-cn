---
title: 编译器警告（等级 1）C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 7f1c71cb3cd6a99d4ed9960032813e7cebca7591
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685074"
---
# <a name="compiler-warning-level-1-c4364"></a>编译器警告（等级 1）C4364

\#使用以前在位置 (line_number) 上查看的程序集 "file"，不 as_friend 特性;as_friend 未应用

`#using`给定的元数据文件重复了指令，但在 **`as_friend`** 第一次出现时未使用该限定符; 编译器将忽略第二个 **`as_friend`** 。

有关详细信息，请参阅 [友元程序集 (c + +) ](../../dotnet/friend-assemblies-cpp.md)。

## <a name="examples"></a>示例

下面的示例创建一个组件。

```cpp
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

下面的示例生成 C4364。

```cpp
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```
