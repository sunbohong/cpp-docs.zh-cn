---
description: 了解详细信息： _com_ptr_t：： GetActiveObject
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: 96784e73d91d7be4b0674e09278183fc62e60af2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295466"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft 专用**

附加到给定或的对象的现有实例 `CLSID` `ProgID` 。

## <a name="syntax"></a>语法

```
HRESULT GetActiveObject(
   const CLSID& rclsid
) throw( );
HRESULT GetActiveObject(
   LPCWSTR clsidString
) throw( );
HRESULT GetActiveObject(
   LPCSTR clsidStringA
) throw( );
```

#### <a name="parameters"></a>parameters

*rclsid*<br/>
`CLSID`对象的。

*clsidString*<br/>
保留 `CLSID` 以 "**{**" 开头的 () 或的 Unicode 字符串 `ProgID` 。

*clsidStringA*<br/>
使用 ANSI 代码页的多字节字符串，其中包含 `CLSID` 以 "**{**" 开头的 () 或 `ProgID` 。

## <a name="remarks"></a>备注

这些成员函数调用 **GetActiveObject** 来检索指向已向 OLE 注册的正在运行的对象的指针，然后查询此智能指针的接口类型。 生成的指针随后将封装在此 `_com_ptr_t` 对象内。 `Release` 调用以减小先前封装的指针的引用计数。 此例程返回 HRESULT 以指示成功或失败。

- **GetActiveObject (** `rclsid`**)** 附加到给定的对象的现有实例 `CLSID` 。    

- **GetActiveObject (** `clsidString`**)** 根据给定的 Unicode 字符串，附加到一个对象的现有实例，该字符串包含 `CLSID` 以 "**{**" ) 或开头的 (`ProgID` 。    

- **GetActiveObject (** `clsidStringA`**)** 根据给定的多字节字符字符串附加到一个对象的现有实例，该字符串包含 `CLSID` 以 "**{**" 开头的 () 或 `ProgID` 。     调用 [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)，它假定字符串位于 ANSI 代码页而非 OEM 代码页中。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_ptr_t 类](../cpp/com-ptr-t-class.md)
