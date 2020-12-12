---
description: 了解详细信息： odl
title: 'odl (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.odl
helpviewer_keywords:
- odl attribute
ms.assetid: 75dcb314-b50f-4a63-9180-507ac1bc78f3
ms.openlocfilehash: 00228a11876a551a02a292fc4f20ea67f55506c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329735"
---
# <a name="odl"></a>odl

将接口标识为对象描述语言 (ODL) 接口。 MIDL 编译器不需要 **odl** 特性;它只是为了兼容 odl 文件。

## <a name="syntax"></a>语法

```cpp
[odl]
```

## <a name="remarks"></a>备注

**Odl** c + + 特性具有与 [odl](/windows/win32/Midl/odl) MIDL 特性相同的功能。

## <a name="example"></a>示例

```cpp
// cpp_attr_ref_odl.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLIb")];

[odl, oleautomation, dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyInterface
{
   HRESULT x();
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
class cmyClass : public IMyInterface
{
public:
   HRESULT x(){}
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**interface**|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[接口特性](interface-attributes.md)
