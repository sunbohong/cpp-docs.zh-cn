---
description: 了解详细信息： chrono 文本
title: chrono 文本
ms.date: 11/04/2016
ms.assetid: 1a9e23b1-256f-4570-8226-5fa7364fb032
ms.openlocfilehash: 497094d920a25635496fb0aa30295d378571418c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325150"
---
# <a name="chrono-literals"></a>chrono 文本

 (c + + 14) \<chrono> 标头定义12个 [用户定义的文本](../cpp/user-defined-literals-cpp.md) ，以方便使用表示小时、分钟、秒、毫秒、微秒和纳秒的文本。 每个用户定义的文本都具有一个整型重载和一个浮点重载。 这些文本是在 literals::chrono_literals 内联命名空间中定义的，当 std::chrono 位于范围内时，该命名空间将被自动置于范围中。

## <a name="syntax"></a>语法

```cpp
inline namespace literals {
  inline namespace chrono_literals {
    // return integral hours
    constexpr chrono::hours operator"" h(unsigned long long Val);

    // return floating-point hours
    constexpr chrono::duration<double, ratio<3600>> operator"" h(long double Val);

    // return integral minutes
    constexpr chrono::minutes(operator"" min)(unsigned long long Val);

    // return floating-point minutes
    constexpr chrono::duration<double, ratio<60>>(operator"" min)(long double Val);

    // return integral seconds
    constexpr chrono::seconds operator"" s(unsigned long long Val);

    // return floating-point seconds
    constexpr chrono::duration<double> operator"" s(long double Val);

    // return integral milliseconds
    constexpr chrono::milliseconds operator"" ms(unsigned long long Val);

    // return floating-point milliseconds
    constexpr chrono::duration<double, milli> operator"" ms(long double Val);

    // return integral microseconds
    constexpr chrono::microseconds operator"" us(unsigned long long Val);

    // return floating-point microseconds
    inline constexpr chrono::duration<double, micro> operator"" us(long double Val);

    // return integral nanoseconds
    inline constexpr chrono::nanoseconds operator"" ns(unsigned long long Val);

    // return floating-point nanoseconds
    constexpr chrono::duration<double, nano> operator"" ns(long double Val);

  } // inline namespace chrono_literals
} // inline namespace literals
```

## <a name="return-value"></a>返回值

采用参数的文本 **`long long`** 返回值或相应的类型。 采用浮点参数的文本返回 [duration](../standard-library/duration-class.md)。

## <a name="example"></a>示例

下面的示例演示如何使用 chrono 文本。

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```
