---
title: 'progid (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: 136c651ec92c78339c2f701804a6a409523dd30f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839993"
---
# <a name="progid"></a>progid

指定 COM 对象的 ProgID。

## <a name="syntax"></a>语法

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>参数

*name*<br/>
表示对象的 ProgID。

Progid 提供了一个可读版本的类标识符 (CLSID) 用于标识 COM/ActiveX 对象。

## <a name="remarks"></a>注解

使用 `progid` c + + 特性可以指定 COM 对象的 ProgID。 ProgID 的格式为 *name1*。 如果未指定 ProgID 的 *版本* ，则默认版本为1。 如果未指定*name1*，则默认名称为*classname。* 如果未指定 `progid` 并且指定 `vi_progid` 了，则将从中获取 *name1* ， `vi_progid` 并追加 (下一个序列号) 版本。

如果使用的特性块 `progid` 还不使用 `uuid` ，编译器将检查注册表以查看是否 `uuid` 存在指定的 `progid` 。 如果 `progid` 未指定，则版本 (和 coclass 名称，如果创建组件类) 将用于生成 `progid` 。

`progid` 隐含 `coclass` 特性，即，如果指定，则与 `progid` 指定 `coclass` 和 `progid` 特性相同。

`progid`特性使类在指定的名称下自动注册。 生成的 .idl 文件将不显示 `progid` 值。

如果在使用 ATL 的项目中使用此属性，则该属性的行为将发生更改。 除了上述行为，使用此属性指定的信息在函数中使用 `GetProgID` ，并由 `coclass` 属性注入。 有关详细信息，请参阅 [coclass](coclass.md) 特性。

## <a name="example"></a>示例

有关使用的示例，请参阅 [coclass](coclass.md) 的示例 `progid` 。

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|`class`, `struct`|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[类特性](class-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID 密钥](/windows/win32/com/-progid--key)
