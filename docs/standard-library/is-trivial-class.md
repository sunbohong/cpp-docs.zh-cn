---
description: 了解详细信息： is_trivial 类
title: is_trivial 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivial
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
ms.openlocfilehash: 56e5a3c915893b88228f4a40307d2c1e3c32555d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247652"
---
# <a name="is_trivial-class"></a>is_trivial 类

测试类型是否为通常类型。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>parameters

*关心*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *T* 是普通类型，则类型谓词的实例为 true; 否则为 false。 常用类型是标量类型、完全可复制类类型、这些类型的数组以及这些类型的 cv 限定版本。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
