---
description: 了解详细信息： _ATL_WIN_MODULE70 结构
title: _ATL_WIN_MODULE70 结构
ms.date: 11/04/2016
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
ms.openlocfilehash: 11b7fdad71fa8c7b615a0e6873571c38420c9b5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158616"
---
# <a name="_atl_win_module70-structure"></a>_ATL_WIN_MODULE70 结构

由 ATL 中的窗口化代码使用。

## <a name="syntax"></a>语法

```cpp
struct _ATL_WIN_MODULE70 {
    UNIT cbSize;
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```

## <a name="members"></a>成员

`cbSize`<br/>
用于版本控制的结构的大小。

`m_csWindowCreate`<br/>
用于序列化对窗口注册代码的访问。 由 ATL 在内部使用。

`m_pCreateWndList`<br/>
用于将窗口绑定到其对象。 由 ATL 在内部使用。

`m_rgWindowClassAtoms`<br/>
用于跟踪窗口类注册，使其能够在终止时正确注销。 由 ATL 在内部使用。

## <a name="remarks"></a>备注

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) 定义为的 typedef `_ATL_WIN_MODULE70` 。

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="see-also"></a>请参阅

[类和结构](../../atl/reference/atl-classes.md)
