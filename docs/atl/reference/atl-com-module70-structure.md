---
description: 了解详细信息： _ATL_COM_MODULE70 结构
title: _ATL_COM_MODULE70 结构
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: db2139d1c816c13e6da104f6a6d785ef35a07721
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165403"
---
# <a name="_atl_com_module70-structure"></a>_ATL_COM_MODULE70 结构

由 ATL 中与 COM 相关的代码使用。

## <a name="syntax"></a>语法

```cpp
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```

## <a name="members"></a>成员

`cbSize`<br/>
用于版本控制的结构的大小。

`m_hInstTypeLib`<br/>
此模块的类型库的句柄实例。

`m_ppAutoObjMapFirst`<br/>
数组元素的地址，指示此模块的对象映射项的开头。

`m_ppAutoObjMapLast`<br/>
数组元素的地址，指示此模块的对象映射项的结尾。

`m_csObjMap`<br/>
用于序列化对对象映射项的访问的关键部分。 由 ATL 在内部使用。

## <a name="remarks"></a>备注

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) 定义为 _ATL_COM_MODULE70 的 typedef。

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="see-also"></a>请参阅

[类和结构](../../atl/reference/atl-classes.md)
