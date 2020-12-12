---
description: 了解详细信息： DontUseNewUseMake 类
title: DontUseNewUseMake 类
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
ms.openlocfilehash: f6b6740e472123e59565e3bad16e4a535a4e17fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272898"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake 类

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>备注

阻止 `new` 在中使用运算符 `RuntimeClass` 。 因此，你必须改为使用 [Make 函数](make-function.md) 。

## <a name="members"></a>成员

### <a name="public-operators"></a>公共运算符

名称                                             | 描述
------------------------------------------------ | ---------------------------------------------------------------------------
[DontUseNewUseMake：： operator new](#operator-new) | 重载运算符 `new` 并防止在中使用它 `RuntimeClass` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`DontUseNewUseMake`

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="dontusenewusemakeoperator-new"></a><a name="operator-new"></a> DontUseNewUseMake：： operator new

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>parameters

*__unnamed0*<br/>
一个未命名的参数，它指定要分配的内存字节数。

*虚拟*<br/>
要分配的类型。

### <a name="return-value"></a>返回值

提供了一种方法，以便在重载运算符时传递其他参数 `new` 。

### <a name="remarks"></a>备注

重载运算符 `new` 并防止在中使用它 `RuntimeClass` 。
