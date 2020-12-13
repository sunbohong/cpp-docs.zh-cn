---
description: 了解详细信息： cpp_quote
title: 'cpp_quote (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: fe8424fd16cb75e320f8c1a1f8e3e444cf2185ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333173"
---
# <a name="cpp_quote"></a>cpp_quote

向生成的 .idl 文件发出指定的字符串（不含引号字符）。

## <a name="syntax"></a>语法

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>parameters

*语句*<br/>
C 指令。

## <a name="remarks"></a>备注

如果要将预处理器指令放入 .idl 文件，则 **cpp_quote** c + + 特性非常有用。

你还可以使用 **cpp_quote** ，并将 .h 文件作为 MIDL 编译的一部分生成。 例如，如果你有一个使用 c + + IDL 特性但无法将此文件用于某些任务的 c + + 头文件，则可以对其进行编译，以创建一个应能使用的 MIDL 生成的 .h 文件。

**Cpp_quote** 特性具有与 [cpp_quote](/windows/win32/Midl/cpp-quote) MIDL 特性相同的功能。

## <a name="example"></a>示例

有关示例，请参阅 [双重](dual.md) 示例使用如何使用 **cpp_quote**。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|任何位置|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[独立属性](stand-alone-attributes.md)
