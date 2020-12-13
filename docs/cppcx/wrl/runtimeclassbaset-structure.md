---
description: 了解详细信息： RuntimeClassBaseT 结构
title: RuntimeClassBaseT 结构
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
ms.openlocfilehash: 48f03a5d54eba455b60646ed47c48e228f07863e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135286"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT 结构

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>parameters

*RuntimeClassTypeT*<br/>
指定一个或多个 [RuntimeClassType](runtimeclasstype-enumeration.md) 枚举器的标志字段。

## <a name="remarks"></a>备注

为 `QueryInterface` 操作和获取接口 id 提供帮助器方法。

## <a name="members"></a>成员

### <a name="protected-methods"></a>受保护的方法

名称                                                         | 描述
------------------------------------------------------------ | -----------------------------------------------------------------------------
[RuntimeClassBaseT：： AsIID](#asiid)                           | 检索指向指定接口 ID 的指针。
[RuntimeClassBaseT：： GetImplementedIIDS](#getimplementediids) | 检索由指定类型实现的接口 Id 的数组。

## <a name="inheritance-hierarchy"></a>继承层次结构

`RuntimeClassBaseT`

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="runtimeclassbasetasiid"></a><a name="asiid"></a> RuntimeClassBaseT：： AsIID

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>parameters

*T*<br/>
实现由参数 *riid* 指定的接口 ID 的类型。

*实现*<br/>
模板参数 *T* 指定的类型的变量。

*riid*<br/>
要检索的接口 ID。

*ppvObject*<br/>
如果此操作成功，则为指向参数 *riid* 指定的接口的指向指针的指针。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为说明错误的 HRESULT。

### <a name="remarks"></a>备注

检索指向指定接口 ID 的指针。

## <a name="runtimeclassbasetgetimplementediids"></a><a name="getimplementediids"></a> RuntimeClassBaseT：： GetImplementedIIDS

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>parameters

*T*<br/>
*实现* 参数的类型。

*实现*<br/>
指向参数 *T* 指定的类型的指针。

*iidCount*<br/>
要检索的接口 Id 的最大数目。

*iid*<br/>
如果此操作成功完成，则为类型 *T* 实现的接口 id 的数组。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则为说明错误的 HRESULT。

### <a name="remarks"></a>备注

检索由指定类型实现的接口 Id 的数组。
