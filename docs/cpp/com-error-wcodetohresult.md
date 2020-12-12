---
description: 了解详细信息： _com_error：： WCodeToHRESULT
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: 9925c34f14f0685cb563e37a8cae0970911f009c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295713"
---
# <a name="_com_errorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft 专用**

将16位 *wCode* 映射到32位 HRESULT。

## <a name="syntax"></a>语法

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>parameters

*wCode*<br/>
要映射到32位 HRESULT 的16位 *wCode* 。

## <a name="return-value"></a>返回值

从16位 *wCode* 映射的32位 HRESULT。

## <a name="remarks"></a>备注

请参阅 [WCode](../cpp/com-error-wcode.md) 成员函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error 类](../cpp/com-error-class.md)
