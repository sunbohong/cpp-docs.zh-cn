---
description: 了解详细信息： ComPtrRefBase 类
title: ComPtrRefBase 类
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: 4dce58e8292092084916c24153d543f2a45856fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273132"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase 类

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>parameters

*T*<br/>
[ComPtr \<T> ](comptr-class.md)类型或从其派生的类型，而不仅仅是由表示的接口 `ComPtr` 。

## <a name="remarks"></a>备注

表示 [ComPtrRef](comptrref-class.md) 类的基类。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称            | 描述
--------------- | -------------------------------------------------
`InterfaceType` | 模板参数 *T* 的类型的同义词。

### <a name="public-operators"></a>公共运算符

名称                                                                       | 描述
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase：： operator IInspectable * *](#operator-iinspectable-star-star) | 将当前 [ptr_](#ptr) 数据成员强制转换为指向接口的指针 `IInspectable` 。
[ComPtrRefBase：： operator IUnknown * *](#operator-iunknown-star-star)         | 将当前 [ptr_](#ptr) 数据成员强制转换为指向接口的指针 `IUnknown` 。

### <a name="protected-data-members"></a>受保护的数据成员

名称                        | 描述
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase：:p tr_](#ptr) | 指向当前模板参数所指定的类型的指针。

## <a name="inheritance-hierarchy"></a>继承层次结构

`ComPtrRefBase`

## <a name="requirements"></a>要求

**标头：** client.h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="comptrrefbaseoperator-iinspectable-operator"></a><a name="operator-iinspectable-star-star"></a>ComPtrRefBase：： operator IInspectable \* \* 运算符

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>备注

将当前 [ptr_](#ptr) 数据成员强制转换为指向接口的指针 `IInspectable` 。

如果当前不是从派生的，则会发出错误 `ComPtrRefBase` `IInspectable` 。

此强制转换仅在定义时才可用 `__WRL_CLASSIC_COM__` 。

## <a name="comptrrefbaseoperator-iunknown-operator"></a><a name="operator-iunknown-star-star"></a> ComPtrRefBase：： operator IUnknown * * 运算符

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>备注

将当前 [ptr_](#ptr) 数据成员强制转换为指向接口的指针 `IUnknown` 。

如果当前不是从派生的，则会发出错误 `ComPtrRefBase` `IUnknown` 。

## <a name="comptrrefbaseptr_"></a><a name="ptr"></a> ComPtrRefBase：:p tr_

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
T* ptr_;
```

### <a name="remarks"></a>备注

指向当前模板参数所指定的类型的指针。 `ptr_` 是受保护的数据成员。
