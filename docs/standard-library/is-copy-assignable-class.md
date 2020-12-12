---
description: 了解详细信息： is_copy_assignable 类
title: is_copy_assignable 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_copy_assignable
helpviewer_keywords:
- is_copy_assignable
ms.assetid: 3ae6bca1-85fb-4829-9ee9-0183b081ff50
ms.openlocfilehash: f13752ce74f316f180fb874572efaf15d1c06c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323793"
---
# <a name="is_copy_assignable-class"></a>is_copy_assignable 类

测试是否可以在赋值时复制类型。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>parameters

*Ty*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *Ty* 是具有复制赋值运算符的类，则类型谓词的实例为 true; 否则为 false。 等效于 is_assignable \<Ty&, const Ty&> 。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
