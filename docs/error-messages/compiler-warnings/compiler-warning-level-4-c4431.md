---
description: 详细了解：编译器警告 (级别 4) C4431
title: 编译器警告（等级 4）C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 47e83f5e49ec8a4e54f4cda62267d01bd42f1ce7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251487"
---
# <a name="compiler-warning-level-4-c4431"></a>编译器警告（等级 4）C4431

缺少类型说明符 - 假定为 int。 注意: C 不再支持默认的 int

此错误可能是由于对 Visual Studio 2005 执行的编译器一致性工作引起的：默认情况下，Visual C++ 不再将非类型化的标识符创建为 int。 必须显式指定标识符的类型。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

## <a name="example"></a>示例

下面的示例生成 C4431。

```c
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```
