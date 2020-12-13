---
description: 了解详细信息： helpcontext
title: 'helpcontext (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: cfedec2f7650490dd266331e6853ba47265aa4ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335719"
---
# <a name="helpcontext"></a>helpcontext

指定一个上下文 ID，该 ID 允许用户在 **帮助** 文件中查看有关此元素的信息。

## <a name="syntax"></a>语法

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>parameters

*id*<br/>
帮助主题的上下文 ID。 有关上下文 Id 的详细信息，请参阅 [HTML 帮助： Context-Sensitive 程序的帮助](../../mfc/html-help-context-sensitive-help-for-your-programs.md) 。

## <a name="remarks"></a>备注

**Helpcontext** c + + 特性具有与 [helpcontext](/windows/win32/Midl/helpcontext) MIDL 特性相同的功能。

## <a name="example"></a>示例

有关如何使用 **helpcontext** 的示例，请参阅 [defaultvalue](defaultvalue.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**interface**、 **`typedef`** ， **`class`** 、method、property|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[接口特性](interface-attributes.md)<br/>
[类特性](class-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)
