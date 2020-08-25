---
title: 注册表数据交换宏
ms.date: 11/04/2016
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
ms.openlocfilehash: 507db77b525c526fe1cd47c7d75c34e15a6a0628
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834539"
---
# <a name="registry-data-exchange-macros"></a>注册表数据交换宏

这些宏执行注册表数据交换操作。

|名称|说明|
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|标记注册表数据交换映射的开头。|
|[END_RDX_MAP](#end_rdx_map)|标记注册表数据交换映射的结尾。|
|[RDX_BINARY](#rdx_binary)|将指定的注册表项与类型为 BYTE 的指定成员变量关联。|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|将指定的注册表项与 CString 类型的指定成员变量关联。|
|[RDX_DWORD](#rdx_dword)|将指定的注册表项与 DWORD 类型的指定成员变量关联。|
|[RDX_TEXT](#rdx_text)|将指定的注册表项与 TCHAR 类型的指定成员变量关联。|

## <a name="requirements"></a>要求

**标头：** atlplus

## <a name="begin_rdx_map"></a><a name="begin_rdx_map"></a> BEGIN_RDX_MAP

标记注册表数据交换映射的开头。

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>注解

以下宏在注册表数据交换映射中用于读取和写入系统注册表中的条目：

|宏|描述|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|将指定的注册表项与类型为 BYTE 的指定成员变量关联。|
|[RDX_DWORD](#rdx_dword)|将指定的注册表项与 DWORD 类型的指定成员变量关联。|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|将指定的注册表项与 CString 类型的指定成员变量关联。|
|[RDX_TEXT](#rdx_text)|将指定的注册表项与 TCHAR 类型的指定成员变量关联。|

当代码需要在系统注册表和 RDX 映射中指定的变量之间交换数据时，应使用全局函数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)或与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏创建的名称相同的成员函数。

## <a name="end_rdx_map"></a><a name="end_rdx_map"></a> END_RDX_MAP

标记注册表数据交换映射的结尾。

```
END_RDX_MAP
```

## <a name="rdx_binary"></a><a name="rdx_binary"></a> RDX_BINARY

将指定的注册表项与类型为 BYTE 的指定成员变量关联。

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>参数

*rootkey*<br/>
注册表项的根。

*键值*<br/>
注册表子项。

*valuename*<br/>
注册表项。

*职员*<br/>
要与指定的注册表项关联的成员变量。

*member_size*<br/>
成员变量的大小（以字节为单位）。

### <a name="remarks"></a>注解

此宏与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏一起使用，以便将成员变量与给定的注册表项关联。 全局函数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)或与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏创建的相同名称的成员函数应用于在系统注册表和 RDX 映射中的成员变量之间进行数据交换。

## <a name="rdx_cstring_text"></a><a name="rdx_cstring_text"></a> RDX_CSTRING_TEXT

将指定的注册表项与 CString 类型的指定成员变量关联。

```
RDX_CSTRING_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>参数

*rootkey*<br/>
注册表项的根。

*键值*<br/>
注册表子项。

*valuename*<br/>
注册表项。

*职员*<br/>
要与指定的注册表项关联的成员变量。

*member_size*<br/>
成员变量的大小（以字节为单位）。

### <a name="remarks"></a>注解

此宏与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏一起使用，以便将成员变量与给定的注册表项关联。 全局函数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)或与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏创建的相同名称的成员函数应用于在系统注册表和 RDX 映射中的成员变量之间进行数据交换。

## <a name="rdx_dword"></a><a name="rdx_dword"></a> RDX_DWORD

将指定的注册表项与 DWORD 类型的指定成员变量关联。

```
RDX_DWORD(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>参数

*rootkey*<br/>
注册表项的根。

*键值*<br/>
注册表子项。

*valuename*<br/>
注册表项。

*职员*<br/>
要与指定的注册表项关联的成员变量。

*member_size*<br/>
成员变量的大小（以字节为单位）。

### <a name="remarks"></a>注解

此宏与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏一起使用，以便将成员变量与给定的注册表项关联。 全局函数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)或与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏创建的相同名称的成员函数应用于在系统注册表和 RDX 映射中的成员变量之间进行数据交换。

## <a name="rdx_text"></a><a name="rdx_text"></a> RDX_TEXT

将指定的注册表项与 TCHAR 类型的指定成员变量关联。

```
RDX_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>参数

*rootkey*<br/>
注册表项的根。

*键值*<br/>
注册表子项。

*valuename*<br/>
注册表项。

*职员*<br/>
要与指定的注册表项关联的成员变量。

*member_size*<br/>
成员变量的大小（以字节为单位）。

### <a name="remarks"></a>注解

此宏与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏一起使用，以便将成员变量与给定的注册表项关联。 全局函数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)或与 BEGIN_RDX_MAP 和 END_RDX_MAP 宏创建的相同名称的成员函数应用于在系统注册表和 RDX 映射中的成员变量之间进行数据交换。

## <a name="see-also"></a>另请参阅

[宏](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
