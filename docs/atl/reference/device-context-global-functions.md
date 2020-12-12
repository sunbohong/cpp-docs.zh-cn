---
description: 了解详细信息：设备上下文全局函数
title: 设备上下文全局函数
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: f5e87271170e29a2f0cc4d42b4e7739a5fd869ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139901"
---
# <a name="device-context-global-functions"></a>设备上下文全局函数

此函数为给定设备创建设备上下文。

|名称|描述|
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|创建设备上下文。|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a> AtlCreateTargetDC

为 [DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) 结构中指定的设备创建设备上下文。

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>parameters

*hdc*<br/>
中设备上下文的现有句柄，或为 NULL。

*ptd*<br/>
中指向 `DVTARGETDEVICE` 结构的指针，该结构包含有关目标设备的信息。

### <a name="return-value"></a>返回值

返回中指定的设备的设备上下文的句柄 `DVTARGETDEVICE` 。 如果未指定设备，则会将句柄返回到默认显示设备。

### <a name="remarks"></a>备注

如果结构为 NULL，并且 *hdc* 为 null，则为默认显示设备创建设备上下文。

如果 *hdc* 不为 null，并且 *ptd* 为 null，则函数返回现有的 *hdc*。

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="see-also"></a>请参阅

[函数](../../atl/reference/atl-functions.md)
