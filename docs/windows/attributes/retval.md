---
description: 了解有关： retval 的详细信息
title: 'retval (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 15bfc994d18a9c61c37402aa763ecbfd96cbd768
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114853"
---
# <a name="retval"></a>retval

指定接收该成员的返回值的参数。

## <a name="syntax"></a>语法

```cpp
[retval]
```

## <a name="remarks"></a>备注

**Retval** c + + 特性具有与 [retval](/windows/win32/Midl/retval) MIDL 特性相同的功能。

**retval** 必须出现在函数声明中的最后一个参数上。

## <a name="example"></a>示例

有关 **retval** 的示例用法，请参阅可 [绑定](bindable.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|Interface 参数，interface 方法|
|**且**|否|
|**必需属性**|**out**|
|**无效的特性**|**in**|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[参数属性](parameter-attributes.md)<br/>
[方法特性](method-attributes.md)
