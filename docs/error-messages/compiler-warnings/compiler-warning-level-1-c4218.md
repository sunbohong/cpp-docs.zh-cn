---
description: 了解详细信息：编译器警告 (等级 1) C4218
title: 编译器警告（等级 1）C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 76fc53a5b290a55c73fe036e2fc02b7a1afedd23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266411"
---
# <a name="compiler-warning-level-1-c4218"></a>编译器警告（等级 1）C4218

使用了非标准扩展：必须至少指定一个存储类或一个类型

使用默认的 Microsoft 扩展 (/Ze) ，你可以在不指定类型或存储类的情况下声明变量。 默认类型为 **`int`** 。

## <a name="example"></a>示例

```cpp
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

此类声明在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 下无效。
