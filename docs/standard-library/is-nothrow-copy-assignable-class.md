---
description: 了解详细信息： is_nothrow_copy_assignable 类
title: is_nothrow_copy_assignable 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: 43618158e33a393012a9f7a4a3ad14c816e3cd6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230804"
---
# <a name="is_nothrow_copy_assignable-class"></a>is_nothrow_copy_assignable 类

测试类型是否具有编译器已知不会引发的复制赋值运算符。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>parameters

*关心*\
要查询的类型。

## <a name="remarks"></a>备注

类型谓词的实例适用于可引用类型 *T* ，其中 `is_nothrow_assignable<T&, const T&>` 保留为 true; 否则为 false。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)\
[is_nothrow_assignable 类](../standard-library/is-nothrow-assignable-class.md)
