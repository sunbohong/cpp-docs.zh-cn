---
description: 详细了解：编译器警告 (等级 3) C4240
title: 编译器警告（等级 3）C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: 95e704b6ad91ff77c4def0b4fa1fe8fad002e5ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344193"
---
# <a name="compiler-warning-level-3-c4240"></a>编译器警告（等级 3）C4240

使用了非标准扩展：对 "classname" 的访问现在被定义为 "访问说明符"，而以前被定义为 "access 说明符"

在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 下，不能更改对嵌套类的访问。 在默认的 Microsoft extension (/Ze) 下，可以用此警告来处理。

## <a name="example"></a>示例

```cpp
// C4240.cpp
// compile with: /W3
class X
{
private:
   class N;
public:
   class N
   {   // C4240
   };
};

int main()
{
}
```
