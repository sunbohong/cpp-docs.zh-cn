---
description: 了解详细信息： is_nothrow_destructible 类
title: is_nothrow_destructible 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_destructible
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
ms.openlocfilehash: 017cc6de7ce5c618fcc3f47540efd34b5fdc40a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323613"
---
# <a name="is_nothrow_destructible-class"></a>is_nothrow_destructible 类

测试类型是否易损坏，以及编译器是否已知此析构函数不会引发。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>parameters

*关心*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *T* 是易损坏类型，则类型谓词的实例为 true，并且编译器知道析构函数不会引发。 否则为 false。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
