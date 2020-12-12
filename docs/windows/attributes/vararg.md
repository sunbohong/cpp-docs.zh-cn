---
description: 了解有关以下内容的详细信息： vararg
title: 'vararg (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vararg
helpviewer_keywords:
- vararg attribute
ms.assetid: 20fc3244-18e9-411c-990e-d5b4fa29a570
ms.openlocfilehash: 7eb2df5f0a2be212bc49c69f329f875f02bf408d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329498"
---
# <a name="vararg"></a>vararg

指定该函数采用的参数数目可变。

## <a name="syntax"></a>语法

```cpp
[vararg]
```

## <a name="remarks"></a>备注

**Vararg** c + + 特性具有与 [vararg](/windows/win32/Midl/vararg) MIDL 特性相同的功能。

## <a name="example"></a>示例

下面的代码演示如何使用 **vararg**：

```cpp
// cpp_attr_ref_vararg.cpp
// compile with: /LD
#include "unknwn.h"
#include "oaidl.h"
[module(name="MyLibrary")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface X : public IUnknown
{
   [vararg] HRESULT Button([in, satype(VARIANT)]SAFEARRAY *psa);
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|接口方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[方法特性](method-attributes.md)
