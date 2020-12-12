---
description: 了解详细信息： _bstr_t：： copy
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 29ca965730dbcc22b4b725661ece68442d39aeba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229335"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Microsoft 专用**

构造封装的 `BSTR` 的副本。

## <a name="syntax"></a>语法

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>parameters

*fCopy*<br/>
如果 **`true`** 为，则 **copy** 返回包含的副本 `BSTR` ，否则 **copy** 返回实际的 BSTR。

## <a name="remarks"></a>备注

返回封装的 `BSTR` 对象的新分配的副本。

## <a name="example"></a>示例

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_bstr_t 类](../cpp/bstr-t-class.md)
