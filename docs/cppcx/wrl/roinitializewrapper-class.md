---
description: 了解详细信息： RoInitializeWrapper 类
title: RoInitializeWrapper 类
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: b7f2c49bd461f08ad732680f1a02968ee7717116
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319295"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper 类

初始化 Windows 运行时。

## <a name="syntax"></a>语法

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>备注

`RoInitializeWrapper` 是初始化 Windows 运行时的便利，并返回一个 HRESULT，指示操作是否成功。 由于类析构函数调用 `::Windows::Foundation::Uninitialize` ，因此的实例 `RoInitializeWrapper` 必须在全局或顶级范围内声明。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

“属性”                                                                    | 描述
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitializeWrapper：： RoInitializeWrapper](#roinitializewrapper)        | 初始化 `RoInitializeWrapper` 类的新实例。
[RoInitializeWrapper：： ~ RoInitializeWrapper](#tilde-roinitializewrapper) | 销毁类的当前实例 `RoInitializeWrapper` 。

### <a name="public-operators"></a>公共运算符

名称                                       | 描述
------------------------------------------ | ------------------------------------------------------------------------
[RoInitializeWrapper：： HRESULT ( # B1 ](#hresult) | 检索构造函数生成的 HRESULT `RoInitializeWrapper` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`RoInitializeWrapper`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装

## <a name="roinitializewrapperhresult"></a><a name="hresult"></a> RoInitializeWrapper：： HRESULT ( # A1

检索最后一个构造函数生成的 HRESULT 值 `RoInitializeWrapper` 。

```cpp
operator HRESULT()
```

## <a name="roinitializewrapperroinitializewrapper"></a><a name="roinitializewrapper"></a> RoInitializeWrapper：： RoInitializeWrapper

初始化 `RoInitializeWrapper` 类的新实例。

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>参数

*flag*<br/>
RO_INIT_TYPE 枚举之一，指定 Windows 运行时提供的支持。

### <a name="remarks"></a>备注

`RoInitializeWrapper`类调用 `Windows::Foundation::Initialize(flags)` 。

## <a name="roinitializewrapperroinitializewrapper"></a><a name="tilde-roinitializewrapper"></a> RoInitializeWrapper：： ~ RoInitializeWrapper

取消 Windows 运行时。

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>备注

`RoInitializeWrapper`类调用 `Windows::Foundation::Uninitialize()` 。
