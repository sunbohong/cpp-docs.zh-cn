---
description: 了解更多： Platform：： IBoxArray 接口
title: Platform::IBoxArray 接口
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IBoxArray
- VCCORLIB/Platform::IBoxArray::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: 8b87a00d709bec8af016de4532c7c4ec759d72fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195139"
---
# <a name="platformiboxarray-interface"></a>Platform::IBoxArray 接口

`IBoxArray` 是在应用程序二进制接口 (ABI) 之间传递或在 `Platform::Object^` 元素的集合中存储（如 XAML 控件）的值类型数组的包装器。

## <a name="syntax"></a>语法

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>parameters

*T*<br/>
每个数组元素中的装箱值的类型。

### <a name="remarks"></a>备注

`IBoxArray` 是的 c + +/CX 名称 `Windows::Foundation::IReferenceArray` 。

### <a name="members"></a>成员

`IBoxArray` 接口继承自 `IValueType` 接口。 `IBoxArray` 还包括这些成员：

|方法|描述|
|------------|-----------------|
|值|返回此 `IBoxArray` 实例以前存储的未装箱数组。|

## <a name="iboxarrayvalue-property"></a><a name="value"></a> IBoxArray：： Value 属性

返回此对象中最初存储的值。

### <a name="syntax"></a>语法

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>parameters

*T*<br/>
装箱值的类型。

### <a name="property-valuereturn-value"></a>属性值/返回值

返回此对象中最初存储的值。

### <a name="remarks"></a>备注

有关示例，请参见 [装箱](../cppcx/boxing-c-cx.md)。

## <a name="see-also"></a>请参阅

[Array 和 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
