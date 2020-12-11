---
description: 了解详细信息： _AtlCreateWndData 结构
title: _AtlCreateWndData 结构
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: 912f2d108baa9cae1b91a34f3c5e386339d11f0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158603"
---
# <a name="_atlcreatewnddata-structure"></a>_AtlCreateWndData 结构

此结构包含 ATL 中的窗口代码中的类实例数据。

## <a name="syntax"></a>语法

```cpp
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>成员

`m_pThis`<br/>
**`this`** 用于获取对窗口过程中的类实例的访问权限的指针。

`m_dwThreadID`<br/>
当前类实例的线程 ID。

`m_pNext`<br/>
指向下一个对象的指针 `_AtlCreateWndData` 。

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="see-also"></a>请参阅

[类和结构](../../atl/reference/atl-classes.md)
