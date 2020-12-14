---
description: 详细了解： vector &lt; bool &gt; ：： reference：： operator bool
title: vector&lt;bool&gt;::reference::operator bool
ms.date: 11/04/2016
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
ms.openlocfilehash: 9b12df8711664aae80d8ed85340b0852b91969ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259313"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

提供从到的隐式转换 `vector<bool>::reference` **`bool`** 。

## <a name="syntax"></a>语法

```cpp
operator bool() const;
```

## <a name="return-value"></a>返回值

[Vector \<bool> ](../standard-library/vector-bool-class.md)对象的元素的布尔值。

## <a name="remarks"></a>备注

`vector<bool>` 对象无法通过此运算符修改。

## <a name="requirements"></a>要求

**标头：**\<vector>

**命名空间:** std

## <a name="see-also"></a>请参阅

[vector \<bool> ：： Reference 类](../standard-library/vector-bool-reference-class.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
