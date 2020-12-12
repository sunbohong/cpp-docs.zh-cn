---
description: 了解详细信息： COM 映射全局函数
title: COM 映射全局函数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: ee502a68a0a3b21849d2fabdadcc9ecbbcc1602d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141331"
---
# <a name="com-map-global-functions"></a>COM 映射全局函数

这些函数为 COM 映射实现提供支持 `IUnknown` 。

|函数|描述|
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|委托给 `IUnknown` 非聚合对象的。|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|生成用于比较接口的有效代码 `IUnknown` 。|

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a> AtlInternalQueryInterface

检索指向所请求的接口的指针。

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>parameters

*pThis*<br/>
中指向对象的指针，该对象包含向公开的接口的 COM 映射 `QueryInterface` 。

*pEntries*<br/>
中一组 `_ATL_INTMAP_ENTRY` 结构，可访问可用接口的映射。

*iid*<br/>
中所请求的接口的 GUID。

*ppvObject*<br/>
弄指向在 *iid* 中指定的接口指针的指针; 如果找不到接口，则为 NULL。

### <a name="return-value"></a>返回值

标准的 HRESULT 值之一。

### <a name="remarks"></a>备注

`AtlInternalQueryInterface` 仅处理 COM 映射表中的接口。 如果对象已聚合，则 `AtlInternalQueryInterface` 不会委托给外部未知。 您可以将接口输入到 COM 映射表中，其中的宏 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 或其变量之一。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

## <a name="inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a> InlineIsEqualIUnknown

对于测试的特殊情况，请调用此函数 `IUnknown` 。

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>parameters

*rguid1*<br/>
中要比较的 GUID `IID_IUnknown` 。

## <a name="see-also"></a>请参阅

[函数](../../atl/reference/atl-functions.md)<br/>
[COM 映射宏](../../atl/reference/com-map-macros.md)
