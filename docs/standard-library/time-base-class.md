---
description: 了解详细信息： time_base 类
title: time_base 类
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: cad27546109cf8ed6d8314869a3306f238cc6528
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289564"
---
# <a name="time_base-class"></a>time_base 类

类作为类模板 time_get 的各个方面的基类，只定义枚举类型 `dateorder` 和此类型的几个常量。

## <a name="syntax"></a>语法

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>备注

每个常量以不同的方式对日期组件进行排序。 这些常量包括：

- `no_order` 指定无特定顺序。

- `dmy` 指定订单 day、month 和 year，如2月1979。

- `mdy` 指定订单 month，day，then year，如1979年12月2日。

- `ymd` 指定订单 year、month 和 day，如1979/12/2。

- `ydm` 指定订单 year，day，then month，如1979：12十二月。

## <a name="requirements"></a>要求

**标头：**\<locale>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
