---
description: 了解详细信息：编译器警告 (等级 1) C4399
title: 编译器警告（等级 1）C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: a1d0fab62d13c08fb2117279d9173786c65d846f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311131"
---
# <a name="compiler-warning-level-1-c4399"></a>编译器警告（等级 1）C4399

> "*symbol*"：在用/clr： pure 编译时，不应将每进程符号标记 __declspec (dllimport) 

## <a name="remarks"></a>备注

**/Clr： pure** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

本机映像中的数据或具有本机和 CLR 构造的映像的数据无法导入到纯映像。 若要解决此警告，请用 **/clr** (not **/clr： pure**) 或 delete 进行编译 `__declspec(dllimport)` 。

## <a name="example"></a>示例

下面的示例生成 C4399。

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
