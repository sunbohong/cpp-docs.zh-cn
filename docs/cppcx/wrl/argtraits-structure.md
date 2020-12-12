---
description: 了解详细信息： ArgTraits 结构
title: ArgTraits 结构
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: b44cd1ff8d5aa4355385629cc08321dfe353e24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175906"
---
# <a name="argtraits-structure"></a>ArgTraits 结构

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>parameters

*TMemberFunction*<br/>
不能与任何方法签名匹配的 ArgTraits 结构的 Typename 参数 `Invoke` 。

*TDelegateInterface*<br/>
委托接口。

*TArg1*<br/>
方法的第一个参数的类型 `Invoke` 。

*TArg2*<br/>
方法的第二个参数的类型 `Invoke` 。

*TArg3*<br/>
方法的第三个参数的类型 `Invoke` 。

*TArg4*<br/>
方法的第四个参数的类型 `Invoke` 。

*TArg5*<br/>
方法的第五个参数的类型 `Invoke` 。

*TArg6*<br/>
方法的第六个参数的类型 `Invoke` 。

*TArg7*<br/>
方法的第七个参数的类型 `Invoke` 。

*TArg8*<br/>
方法的第八个参数的类型 `Invoke` 。

*TArg9*<br/>
方法的第九个参数的类型 `Invoke` 。

## <a name="remarks"></a>备注

`ArgTraits`结构声明指定的委托接口和具有指定数量的参数的匿名成员函数。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称       | 描述
---------- | ----------------------
`Arg1Type` | TArg1 的 typedef。
`Arg2Type` | TArg2 的 typedef。
`Arg3Type` | TArg3 的 typedef。
`Arg4Type` | TArg4 的 typedef。
`Arg5Type` | TArg5 的 typedef。
`Arg6Type` | TArg6 的 typedef。
`Arg7Type` | TArg7 的 typedef。
`Arg8Type` | TArg8 的 typedef。
`Arg9Type` | TArg9 的 typedef。

### <a name="public-constants"></a>公共常量

名称                     | 描述
------------------------ | ---------------------------------------------------------------------------------------
[ArgTraits：： args](#args) | 保留委托接口的方法的参数数目 `Invoke` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`ArgTraits`

## <a name="requirements"></a>要求

**标头：** 事件。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="argtraitsargs"></a><a name="args"></a> ArgTraits：： args

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
static const int args = -1;
```

### <a name="remarks"></a>备注

保留委托接口的方法的参数数目 `Invoke` 。 当 `args` 等于-1 时，不能与 `Invoke` 方法签名匹配。
