---
description: 了解详细信息： nonextensible
title: 'nonextensible (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: dfb0eda0fc8c6de367ee29ec3786750ba40395ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327444"
---
# <a name="nonextensible"></a>nonextensible

指定 `IDispatch` 实现仅包含接口说明中列出的属性和方法，而不能在运行时与其他成员一起扩展。

## <a name="syntax"></a>语法

```cpp
[nonextensible]
```

## <a name="remarks"></a>备注

**Nonextensible** c + + 特性具有与 [nonextensible](/windows/win32/Midl/nonextensible) MIDL 特性相同的功能。

使用 **nonextensible** 还需要 [oleautomation](oleautomation.md) 属性。

## <a name="example"></a>示例

下面的代码演示 **nonextensible** 属性的一种用法：

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**interface**|
|**且**|否|
|**必需属性**|`dual` and `oleautomation` 、or `dispinterface`|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[接口特性](interface-attributes.md)
