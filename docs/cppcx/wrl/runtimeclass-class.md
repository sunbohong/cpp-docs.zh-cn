---
description: 了解详细信息： RuntimeClass 类
title: RuntimeClass 类
ms.date: 09/11/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
ms.openlocfilehash: f62eec0b5ac9b8fc8ecac390ea07077743fdcb51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330762"
---
# <a name="runtimeclass-class"></a>RuntimeClass 类

表示一个 WinRT 或 COM 类，该类继承指定接口并提供指定的 Windows 运行时、经典 COM 和弱引用支持。

此类提供 WinRT 和 COM 类的样板实现，提供、等的实现 `QueryInterface` ， `AddRef` `Release` 管理模块的引用计数，并支持为可激活对象提供类工厂。

## <a name="syntax"></a>语法

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>parameters

*classFlags*<br/>
可选参数。 一个或多个 [RuntimeClassType](runtimeclasstype-enumeration.md) 枚举值的组合。 `__WRL_CONFIGURATION_LEGACY__`可以定义宏来更改项目中所有运行时类的 classFlags 的默认值。 如果已定义，则默认情况下，RuntimeClass 实例是非 agile 实例。 如果未定义，则默认情况下，RuntimeClass 实例为敏捷。 若要避免出现多义性， `Microsoft::WRL::FtmBase` 请在或中指定 `TInterfaces` `RuntimeClassType::InhibitFtmBase` 。 请注意，如果同时使用 InhibitFtmBase 和 FtmBase，则对象将为敏捷。

*TInterfaces*<br/>
对象实现的接口的列表 `IUnknown` ， `IInspectable` 或由 [RuntimeClassType](runtimeclasstype-enumeration.md)控制的其他接口。 它还可以列出派生自的其他类，特别是 `Microsoft::WRL::FtmBase` 使对象具有 agile 并导致其实现 `IMarshal` 。

## <a name="members"></a>成员

`RuntimeClassInitialize`<br/>
如果 `MakeAndInitialize` 模板函数用于构造对象，则为初始化对象的函数。 如果对象已成功初始化，则返回 S_OK; 如果初始化失败，则返回 COM 错误代码。 COM 错误代码传播为的返回值 `MakeAndInitialize` 。 请注意， `RuntimeClassInitialize` 如果 `Make` 使用模板函数构造对象，则不会调用方法。

### <a name="public-constructors"></a>公共构造函数

| “属性”                                               | 描述                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass：： RuntimeClass](#runtimeclass)        | 初始化类的当前实例 `RuntimeClass` 。   |
| [RuntimeClass：： ~ RuntimeClass](#tilde-runtimeclass) | 取消初始化类的当前实例 `RuntimeClass` 。 |

### <a name="public-methods"></a>公共方法

| “属性”                                                      | 描述                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass：： AddRef](#addref)                           | 递增当前对象的引用计数 `RuntimeClass` 。                              |
| [RuntimeClass：:D ecrementReference](#decrementreference)   | 递减当前对象的引用计数 `RuntimeClass` 。                              |
| [RuntimeClass：： GetIids](#getiids)                         | 获取一个数组，该数组可以包含当前对象实现的接口 Id `RuntimeClass` 。 |
| [RuntimeClass：： GetRuntimeClassName](#getruntimeclassname) | 获取当前对象的运行时类名称 `RuntimeClass` 。                                  |
| [RuntimeClass：： GetTrustLevel](#gettrustlevel)             | 获取当前对象的信任级别 `RuntimeClass` 。                                         |
| [RuntimeClass：： GetWeakReference](#getweakreference)       | 获取一个指针，该指针指向当前对象的弱引用对象 `RuntimeClass` 。                 |
| [RuntimeClass：： InternalAddRef](#internaladdref)           | 将引用计数递增到当前 `RuntimeClass` 对象。                               |
| [RuntimeClass：： QueryInterface](#queryinterface)           | 检索指向指定接口 ID 的指针。                                                 |
| [RuntimeClass：： Release](#release)                         | 对当前对象执行 COM 释放操作 `RuntimeClass` 。                             |

## <a name="inheritance-hierarchy"></a>继承层次结构

这是实现详细信息。

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft::WRL

## <a name="runtimeclassruntimeclass"></a><a name="tilde-runtimeclass"></a> RuntimeClass：： ~ RuntimeClass

取消初始化类的当前实例 `RuntimeClass` 。

```cpp
virtual ~RuntimeClass();
```

## <a name="runtimeclassaddref"></a><a name="addref"></a> RuntimeClass：： AddRef

递增当前对象的引用计数 `RuntimeClass` 。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

## <a name="runtimeclassdecrementreference"></a><a name="decrementreference"></a> RuntimeClass：:D ecrementReference

递减当前对象的引用计数 `RuntimeClass` 。

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

## <a name="runtimeclassgetiids"></a><a name="getiids"></a> RuntimeClass：： GetIids

获取一个数组，该数组可以包含当前对象实现的接口 Id `RuntimeClass` 。

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>parameters

*iidCount*<br/>
此操作完成后，数组 *iid* 中的元素总数。

*iid*<br/>
此操作完成后，指向接口 ID 数组的指针。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为 E_OUTOFMEMORY。

## <a name="runtimeclassgetruntimeclassname"></a><a name="getruntimeclassname"></a> RuntimeClass：： GetRuntimeClassName

获取当前对象的运行时类名称 `RuntimeClass` 。

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>parameters

*runtimeName*<br/>
此操作完成后，运行时类名称。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

### <a name="remarks"></a>备注

如果 `__WRL_STRICT__` 或未定义，则发出断言错误 `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` 。

## <a name="runtimeclassgettrustlevel"></a><a name="gettrustlevel"></a> RuntimeClass：： GetTrustLevel

获取当前对象的信任级别 `RuntimeClass` 。

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>parameters

*trustLvl*<br/>
此操作完成后，为当前对象的信任级别 `RuntimeClass` 。

### <a name="return-value"></a>返回值

始终 S_OK。

### <a name="remarks"></a>备注

如果 `__WRL_STRICT__` 或未定义，则发出断言错误 `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` 。

## <a name="runtimeclassgetweakreference"></a><a name="getweakreference"></a> RuntimeClass：： GetWeakReference

获取一个指针，该指针指向当前对象的弱引用对象 `RuntimeClass` 。

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>parameters

*weakReference*<br/>
此操作完成后，指向弱引用对象的指针。

### <a name="return-value"></a>返回值

始终 S_OK。

## <a name="runtimeclassinternaladdref"></a><a name="internaladdref"></a> RuntimeClass：： InternalAddRef

将引用计数递增到当前 `RuntimeClass` 对象。

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>返回值

生成的引用计数。

## <a name="runtimeclassqueryinterface"></a><a name="queryinterface"></a> RuntimeClass：： QueryInterface

检索指向指定接口 ID 的指针。

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>parameters

*riid*<br/>
接口 ID。

*ppvObject*<br/>
此 opereation 完成后，为由 *riid* 参数指定的接口的指针。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

## <a name="runtimeclassrelease"></a><a name="release"></a> RuntimeClass：： Release

对当前对象执行 COM 释放操作 `RuntimeClass` 。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

### <a name="remarks"></a>备注

如果引用计数变为零，则 `RuntimeClass` 删除对象。

## <a name="runtimeclassruntimeclass"></a><a name="runtimeclass"></a> RuntimeClass：： RuntimeClass

初始化类的当前实例 `RuntimeClass` 。

```cpp
RuntimeClass();
```
