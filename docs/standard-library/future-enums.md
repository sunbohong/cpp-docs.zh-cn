---
title: '&lt;future&gt; 枚举'
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 45dc3277b3f14b7f9dbb043cf9db1f1865d4e4c9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838017"
---
# <a name="ltfuturegt-enums"></a>&lt;future&gt; 枚举

[future_errc](#future_errc)\
[future_status](#future_status)\
[启动](#launch)

## <a name="future_errc-enumeration"></a><a name="future_errc"></a> future_errc 枚举

为 [future_error](../standard-library/future-error-class.md) 类报告的所有错误提供符号名称。

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status-enumeration"></a><a name="future_status"></a> future_status 枚举

为计时等待函数可返回的原因提供符号名称。

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch-enumeration"></a><a name="launch"></a> 启动枚举

展示描述模板函数 [async](../standard-library/future-functions.md#async) 的可能模式的位掩码类型。

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>另请参阅

[\<future>](../standard-library/future.md)
