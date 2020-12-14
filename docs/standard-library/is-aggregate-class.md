---
description: 了解详细信息： is_aggregate 类
title: is_aggregate 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_aggregate
helpviewer_keywords:
- is_aggregate
ms.openlocfilehash: 6ca27e6edea42b6c0ae3f0c89749a586adac857b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231363"
---
# <a name="is_aggregate-class"></a>is_aggregate 类

测试类型是否是标记为 `aggregate` 的类类型。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct is_aggregate;
```

### <a name="parameters"></a>parameters

*关心*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *T* 是标记为的类类型，则类型谓词的实例为 true `aggregate` ; 否则为 false。 如果 *T* 是类类型，则它必须是完整类型。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
