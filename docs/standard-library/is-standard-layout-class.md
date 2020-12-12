---
description: 了解详细信息： is_standard_layout 类
title: is_standard_layout 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: 8f1f24fcb29e862dff10c2a51d1c9d0b2b28541f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271247"
---
# <a name="is_standard_layout-class"></a>is_standard_layout 类

测试类型是否为标准布局。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>parameters

*Ty*\
要查询的类型

## <a name="remarks"></a>备注

如果类型 *Ty* 是具有内存中成员对象的标准布局的类，则此类型谓词的实例为 true; 否则为 false。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
