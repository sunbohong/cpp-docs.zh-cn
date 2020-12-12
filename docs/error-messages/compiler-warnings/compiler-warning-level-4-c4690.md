---
description: 详细了解：编译器警告 (级别 4) C4690
title: 编译器警告（等级 4）C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: 1f6d3ee3f6ba20207a355350edda99861d10b5f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133834"
---
# <a name="compiler-warning-level-4-c4690"></a>编译器警告（等级 4）C4690

> \[ emitidl ( pop ) ]：比推送更多的 pop

## <a name="remarks"></a>备注

[emitidl](../../windows/attributes/emitidl.md) 特性的出栈次数比入栈次数多一次。

## <a name="example"></a>示例

下面的示例生成 C4690。 若要解决此问题，请确保该属性在推送后的次数完全相同。

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
