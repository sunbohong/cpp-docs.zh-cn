---
title: '双重 (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dual
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
ms.openlocfilehash: 4cc974bef46a403cbdc5b290f623acb06f40722f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845401"
---
# <a name="dual"></a>dual

将一个接口作为双重接口放置在 .idl 文件中。

## <a name="syntax"></a>语法

```cpp
[dual]
```

## <a name="remarks"></a>备注

当 **双重** c + + 特性位于接口之前时，它将使该接口放置在生成的 .idl 文件中的库块内。

## <a name="example"></a>示例

下面的代码是一个在接口定义之前使用 **双重** 的特性块：

```cpp
// cpp_attr_ref_dual.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]

__interface IStatic : IDispatch
{
   HRESULT Func1(int i);
   [   propget,    id(1),    bindable,    displaybind,    defaultbind,    requestedit
   ]
   HRESULT P1([out, retval] long *nSize);
   [   propput,    id(1),    bindable,    displaybind,    defaultbind,    requestedit
   ]
   HRESULT P1([in] long nSize);
};

[cpp_quote("#include file.h")];
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**interface**|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|`dispinterface`|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[按使用情况的属性](attributes-by-usage.md)<br/>
[客户](custom-cpp.md)<br/>
[dispinterface](dispinterface.md)<br/>
对象<br/>
[__interface](../../cpp/interface.md)
