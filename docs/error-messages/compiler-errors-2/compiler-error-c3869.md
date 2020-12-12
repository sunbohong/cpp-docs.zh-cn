---
description: 了解更多：编译器错误 C3869
title: C3869
ms.date: 11/04/2016
f1_keywords:
- C3869
helpviewer_keywords:
- C3869
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
ms.openlocfilehash: 8b5bcd59bfeb5407edcfbea6217212dfc44c6643
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222783"
---
# <a name="compiler-error-c3869"></a>C3869

gcnew 约束缺少空参数列表 " ( # A1"

**`gcnew`** 指定的特殊约束没有空参数列表。 有关详细信息，请参阅有关 [c + +/cli)  (泛型类型参数的约束 ](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 。

## <a name="example"></a>示例

下面的示例生成 C3869。

```cpp
// C3869.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : gcnew   // C3869
// try the following line instead
// where T : gcnew()
ref class List {};
```
