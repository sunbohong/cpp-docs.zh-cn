---
description: 了解详细信息： is_trivially_destructible 类
title: is_trivially_destructible 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_destructible
helpviewer_keywords:
- is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
ms.openlocfilehash: 41f36c027175cbf67049eed986b9188ba1532048
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154352"
---
# <a name="is_trivially_destructible-class"></a>is_trivially_destructible 类

测试类型是否为普通易损坏类型。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct is_trivially_destructible;
```

### <a name="parameters"></a>parameters

*关心*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *T* 是易损坏类型，则类型谓词的实例为 true，并且编译器知道析构函数不使用任何普通操作。 否则为 false。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
