---
title: 'requestedit (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requestedit
helpviewer_keywords:
- requestedit attribute
ms.assetid: b3c24790-3c4a-4646-8722-03d7b51172ee
ms.openlocfilehash: d5cf2bb8fab75c64d74a2f28964b3019200dad51
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846012"
---
# <a name="requestedit"></a>requestedit

指示该属性支持 `OnRequestEdit` 通知。

## <a name="syntax"></a>语法

```cpp
[requestedit]
```

## <a name="remarks"></a>备注

**Requestedit** c + + 特性具有与[requestedit](/windows/win32/Midl/requestedit) MIDL 特性相同的功能。

## <a name="example"></a>示例

有关**requestedit**的示例用法，请参阅可[绑定](bindable.md)的示例。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|接口方法|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[方法特性](method-attributes.md)<br/>
[数据成员特性](data-member-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)
