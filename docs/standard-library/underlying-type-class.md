---
description: 了解详细信息： underlying_type 类
title: underlying_type 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: e717abe854f13fc96926deba1d4bf177529618cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132699"
---
# <a name="underlying_type-class"></a>underlying_type 类

生成枚举类型的基础整型类型。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>parameters

*关心*\
要修改的类型。

## <a name="remarks"></a>备注

`type`当 *t* 是枚举类型时，类模板的成员 Typedef 将命名 *t* 的基础整型类型，否则没有成员 typedef `type` 。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
