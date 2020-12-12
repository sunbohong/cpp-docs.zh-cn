---
description: 详细了解：编译器警告 (级别 4) C4214
title: 编译器警告（等级 4）C4214
ms.date: 11/04/2016
f1_keywords:
- C4214
helpviewer_keywords:
- C4214
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
ms.openlocfilehash: afc3f425f0d37b3fb3063d18cb514336271a30ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297299"
---
# <a name="compiler-warning-level-4-c4214"></a>编译器警告（等级 4）C4214

使用了非标准扩展： int 以外的位域类型

对于默认的 Microsoft 扩展 (/Ze) ，位域结构成员可以是任何整数类型。

## <a name="example"></a>示例

```c
// C4214.c
// compile with: /W4
struct bitfields
{
   unsigned short j:4;  // C4214
};

int main()
{
}
```

此类位域在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 中无效。
