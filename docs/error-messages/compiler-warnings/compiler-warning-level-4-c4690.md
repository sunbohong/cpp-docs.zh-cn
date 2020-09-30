---
title: 编译器警告（等级 4）C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: de996128c68ebf96b4a00f6206cbaf54d97ca275
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509964"
---
# <a name="compiler-warning-level-4-c4690"></a>编译器警告（等级 4）C4690

> \[ emitidl ( pop ) ]：比推送更多的 pop

## <a name="remarks"></a>注解

[emitidl](../../windows/attributes/emitidl.md) 特性的出栈次数比入栈次数多一次。

## <a name="example"></a>示例

下面的示例生成 C4690。 若要解决此问题，请确保该属性在推送后的次数完全相同。

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
