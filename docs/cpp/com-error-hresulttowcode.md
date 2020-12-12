---
description: 了解详细信息： _com_error：： HRESULTToWCode
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: 1bbf62be42d4e34a2ef73493f0449c2ffbaf0646
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295824"
---
# <a name="_com_errorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft 专用**

将32位 HRESULT 映射到16位 `wCode` 。

## <a name="syntax"></a>语法

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>parameters

*小时*<br/>
要映射到16位的32位 HRESULT `wCode` 。

## <a name="return-value"></a>返回值

`wCode`从32位 HRESULT 映射的16位。

## <a name="remarks"></a>备注

有关详细信息，请参阅 [_com_error：： WCode](../cpp/com-error-wcode.md) 。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error 类](../cpp/com-error-class.md)
