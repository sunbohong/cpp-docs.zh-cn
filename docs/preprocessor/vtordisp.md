---
description: pragma在 Microsoft c + + 中了解有关 vtordisp 的详细信息
title: vtordisp pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragma, vtordisp
- vtordisp pragma
no-loc:
- pragma
ms.openlocfilehash: f8956aa892aae0472001b007137e6f978d91500e
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713137"
---
# <a name="vtordisp-no-locpragma"></a>`vtordisp` pragma

控制隐藏的 `vtordisp` 构造/析构置换成员的添加。 `vtordisp` pragma 是 c + + 特定的。

## <a name="syntax"></a>语法

> **`#pragma vtordisp(`**[ **`push,`** ] *n***`)`**\
> **`#pragma vtordisp(pop)`**\
> **`#pragma vtordisp()`**\
> **`#pragma vtordisp(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**

### <a name="parameters"></a>Parameters

**`push`**\
推送 `vtordisp` 内部编译器堆栈上的当前设置，并将新设置设置 `vtordisp` 为 *n*。  如果未指定 *n* ，则当前 `vtordisp` 设置保持不变。

**`pop`**\
从内部编译器堆栈中移除顶部记录，并将设置还原 `vtordisp` 为删除的值。

*北*\
指定设置的新值 `vtordisp` 。 可能的值为 **`0`** 、、 **`1`** 或 **`2`** ，对应于 **`/vd0`** 、 **`/vd1`** 和 **`/vd2`** 编译器选项。 有关详细信息，请参阅[ `/vd` (禁用构造置换) ](../build/reference/vd-disable-construction-displacements.md)。

**`on`**\
等效于 `#pragma vtordisp(1)`。

**`off`**\
等效于 `#pragma vtordisp(0)`。

## <a name="remarks"></a>注解

**`vtordisp`** pragma 仅适用于使用虚拟基的代码。 如果派生类重写它从虚拟基类继承的虚函数，并且派生类的构造函数或析构函数使用指向虚拟基类的指针调用该函数，则编译器可能会将额外 `vtordisp` 的隐藏字段引入到具有虚拟基的类中。

**`vtordisp`** pragma 会影响后面的类的布局。 **`/vd0`**、 **`/vd1`** 和 **`/vd2`** 编译器选项为完整模块指定相同的行为。 指定 **`0`** 或 **`off`** 取消隐藏 `vtordisp` 成员。 **`vtordisp`** 仅当该类的构造函数和析构函数不能在指针指向的对象上调用虚函数时，才会关闭 **`this`** 。

指定 **`1`** **`on`** 默认值时，将在必要时启用隐藏 `vtordisp` 成员。

指定 **`2`** 将 `vtordisp` 为所有具有虚函数的虚拟基启用隐藏成员。 `#pragma vtordisp(2)` 可能需要确保 **`dynamic_cast`** 在部分构造的对象上的性能正确。 有关详细信息，请参阅 [编译器警告 (等级 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)。

`#pragma vtordisp()`无参数的情况下，会将 `vtordisp` 设置还原为其初始设置。

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
