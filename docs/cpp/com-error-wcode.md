---
description: 了解详细信息： _com_error：： WCode
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: e3a19e5ae6c98cb38445e5eaa822474b2a852135
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295726"
---
# <a name="_com_errorwcode"></a>_com_error::WCode

**Microsoft 专用**

检索映射到封装的 HRESULT 中的16位错误代码。

## <a name="syntax"></a>语法

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>返回值

如果 HRESULT 在0x80040200 到0x8004FFFF 范围内，则该 `WCode` 方法将返回 HRESULT 减 0x80040200; 否则，它将返回零。

## <a name="remarks"></a>备注

`WCode`方法用于撤消 COM 支持代码中发生的映射。 `dispinterface`属性或方法的包装器调用一个支持例程，该例程打包参数和调用 `IDispatch::Invoke` 。 返回时，如果返回失败的 HRESULT `DISP_E_EXCEPTION` ，则会从传递给的结构中检索错误信息 `EXCEPINFO` `IDispatch::Invoke` 。 错误代码可以是存储在结构的成员中的16位值，也可以是 `wCode` `EXCEPINFO` `scode` 结构成员的完整32位值 `EXCEPINFO` 。 如果返回了16位 `wCode` ，则必须先将其映射到32位的失败 HRESULT。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error 类](../cpp/com-error-class.md)
