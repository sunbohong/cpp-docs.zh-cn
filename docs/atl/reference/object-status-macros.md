---
title: 对象状态宏
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: d9e2223739dc3d0636337e2e2f713c80dff50131
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835228"
---
# <a name="object-status-macros"></a>对象状态宏

此宏可设置属于 ActiveX 控件的标志。

|名称|说明|
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|在 ATL ActiveX 控件中用于设置 OLEMISC 标志。|

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="declare_olemisc_status"></a><a name="declare_olemisc_status"></a> DECLARE_OLEMISC_STATUS

在 ATL ActiveX 控件中用于设置 OLEMISC 标志。

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>参数

*miscstatus*<br/>
所有适用的 OLEMISC 标志。

### <a name="remarks"></a>注解

此宏用于设置 ActiveX 控件的 OLEMISC 标志。 有关更多详细信息，请参阅 [IOleObject：： GetMiscStatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>另请参阅

[宏](../../atl/reference/atl-macros.md)
