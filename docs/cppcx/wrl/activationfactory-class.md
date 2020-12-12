---
description: 了解详细信息： ActivationFactory 类
title: ActivationFactory 类
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
ms.openlocfilehash: 7204a3c2f981947a03efba648dd91b69d582fee1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287835"
---
# <a name="activationfactory-class"></a>ActivationFactory 类

启用 Windows 运行时将激活的一个或多个类。

## <a name="syntax"></a>语法

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>parameters

*I0*<br/>
第零个接口。

*I1*<br/>
第一个接口。

*I2*<br/>
第二个接口。

## <a name="remarks"></a>备注

`ActivationFactory` 为接口提供注册方法和基本功能 `IActivationFactory` 。 `ActivationFactory` 还使您能够提供自定义工厂实现。

下面的代码片段符号说明了如何使用 ActivationFactory。

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

下面的代码段演示如何使用 [实现](implements-structure.md) 结构来指定三个以上的接口 id。

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

“属性”                                                       | 描述
---------------------------------------------------------- | ------------------------------------------
[ActivationFactory：： ActivationFactory](#activationfactory) | 初始化 `ActivationFactory` 类。

### <a name="public-methods"></a>公共方法

“属性”                                                           | 描述
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[ActivationFactory：： AddRef](#addref)                           | 递增当前对象的引用计数 `ActivationFactory` 。
[ActivationFactory：： GetIids](#getiids)                         | 检索已实现接口 ID 的数组。
[ActivationFactory：： GetRuntimeClassName](#getruntimeclassname) | 获取当前实例化的对象的运行时类名称 `ActivationFactory` 。
[ActivationFactory：： GetTrustLevel](#gettrustlevel)             | 获取当前实例化的对象的信任级别 `ActivationFactory` 。
[ActivationFactory：： QueryInterface](#queryinterface)           | 检索指向指定接口的指针。
[ActivationFactory：： Release](#release)                         | 递减当前对象的引用计数 `ActivationFactory` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

## <a name="requirements"></a>要求

**标头：** 模块。h

**命名空间：** Microsoft::WRL

## <a name="activationfactoryactivationfactory"></a><a name="activationfactory"></a> ActivationFactory：： ActivationFactory

初始化 `ActivationFactory` 类。

```cpp
ActivationFactory();
```

## <a name="activationfactoryaddref"></a><a name="addref"></a> ActivationFactory：： AddRef

递增当前对象的引用计数 `ActivationFactory` 。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。

## <a name="activationfactorygetiids"></a><a name="getiids"></a> ActivationFactory：： GetIids

检索已实现接口 ID 的数组。

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>parameters

*iidCount*<br/>
此操作完成后， *iid* 数组中的界面 id 的数量。

*iid*<br/>
此操作完成后，已实现接口 ID 的数组。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。 E_OUTOFMEMORY 是可能的失败 HRESULT。

## <a name="activationfactorygetruntimeclassname"></a><a name="getruntimeclassname"></a> ActivationFactory：： GetRuntimeClassName

获取当前实例化的对象的运行时类名称 `ActivationFactory` 。

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>parameters

*runtimeName*<br/>
此操作完成后，为字符串的句柄，其中包含当前实例化的对象的运行时类名称 `ActivationFactory` 。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。

## <a name="activationfactorygettrustlevel"></a><a name="gettrustlevel"></a> ActivationFactory：： GetTrustLevel

获取当前实例化的对象的信任级别 `ActivationFactory` 。

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>parameters

*trustLvl*<br/>
此操作完成时，实例化的运行时类的信任级别 `ActivationFactory` 。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则，将发出断言错误，并将 *trustLvl* 设置为 `FullTrust` 。

## <a name="activationfactoryqueryinterface"></a><a name="queryinterface"></a> ActivationFactory：： QueryInterface

检索指向指定接口的指针。

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>parameters

*riid*<br/>
接口 ID。

*ppvObject*<br/>
完成此操作后，指向参数 *riid* 指定的接口的指针。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。

## <a name="activationfactoryrelease"></a><a name="release"></a> ActivationFactory：： Release

递减当前对象的引用计数 `ActivationFactory` 。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。
