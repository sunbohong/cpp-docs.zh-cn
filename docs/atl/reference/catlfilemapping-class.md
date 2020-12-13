---
description: 了解详细信息： CAtlFileMapping 类
title: CAtlFileMapping 类
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: 875979d47ad4cb5b9c59047eff1f50acd35d1251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147415"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping 类

此类表示内存映射文件，并向 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)的方法添加强制转换运算符。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```cpp
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

### <a name="parameters"></a>parameters

*T*<br/>
用于转换运算符的数据类型。

## <a name="members"></a>成员

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CAtlFileMapping：： operator T *](#operator_t_star)|允许对象隐式转换 `CAtlFileMapping` 为 `T*` 。|

## <a name="remarks"></a>备注

此类添加单个强制转换运算符，以允许将对象隐式转换 `CAtlFileMapping` 为 `T*` 。 其他成员由基类 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)提供。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>要求

**标头：** atlfile

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a> CAtlFileMapping：： operator T *

允许对象隐式转换 `CAtlFileMapping` 为 `T*` 。

```cpp
operator T*() const throw();
```

### <a name="return-value"></a>返回值

返回一个 `T*` 指针，该指针指向内存映射文件的开头。

### <a name="remarks"></a>备注

调用 [CAtlFileMappingBase：：：：](../../atl/reference/catlfilemappingbase-class.md#getdata) 重新解释，并将返回的指针作为 `T*` ，其中 *T* 是用作此类的模板参数的类型。

## <a name="see-also"></a>请参阅

[CAtlFileMappingBase 类](../../atl/reference/catlfilemappingbase-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
