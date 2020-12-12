---
description: 了解详细信息： treat_as_floating_point 结构
title: treat_as_floating_point 结构
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 498421d454de1e15ea52282665bcf9ae7d045946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169055"
---
# <a name="treat_as_floating_point-structure"></a>treat_as_floating_point 结构

指定是否可将 `Rep` 视为浮点类型。

## <a name="syntax"></a>语法

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>备注

仅当专用化 `treat_as_floating_point<Rep>` 派生自 [true_type](../standard-library/type-traits-typedefs.md#true_type) 时，才可将 `Rep` 视为浮点类型。 类模板可专用于用户定义类型。

## <a name="requirements"></a>要求

**标头：**\<chrono>

**命名空间：** std::chrono

## <a name="see-also"></a>请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
