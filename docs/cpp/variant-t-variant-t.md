---
description: 了解详细信息： _variant_t：： _variant_t
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: e49f2cf42ce1d73cb18d280d335ed267cb11df3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161359"
---
# <a name="_variant_t_variant_t"></a>_variant_t::_variant_t

**Microsoft 专用**

构造 `_variant_t` 对象。

## <a name="syntax"></a>语法

```
_variant_t( ) throw( );

_variant_t(
   const VARIANT& varSrc
);

_variant_t(
   const VARIANT* pVarSrc
);

_variant_t(
   const _variant_t& var_t_Src
);

_variant_t(
   VARIANT& varSrc,
   bool fCopy
);

_variant_t(
   short sSrc,
   VARTYPE vtSrc = VT_I2
);

_variant_t(
   long lSrc,
   VARTYPE vtSrc = VT_I4
);

_variant_t(
   float fltSrc
) throw( );

_variant_t(
   double dblSrc,
   VARTYPE vtSrc = VT_R8
);

_variant_t(
   const CY& cySrc
) throw( );

_variant_t(
   const _bstr_t& bstrSrc
);

_variant_t(
   const wchar_t *wstrSrc
);

_variant_t(
   const char* strSrc
);

_variant_t(
   IDispatch* pDispSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   bool bSrc
) throw( );

_variant_t(
   IUnknown* pIUknownSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   const DECIMAL& decSrc
) throw( );

_variant_t(
   BYTE bSrc
) throw( );

variant_t(
   char cSrc
) throw();

_variant_t(
   unsigned short usSrc
) throw();

_variant_t(
   unsigned long ulSrc
) throw();

_variant_t(
   int iSrc
) throw();

_variant_t(
   unsigned int uiSrc
) throw();

_variant_t(
   __int64 i8Src
) throw();

_variant_t(
   unsigned __int64 ui8Src
) throw();
```

#### <a name="parameters"></a>parameters

*varSrc*<br/>
要复制到新的 `VARIANT` 对象中的 `_variant_t` 对象。

*pVarSrc*<br/>
指向 `VARIANT` 要复制到新对象中的对象的指针 `_variant_t` 。

*var_t_Src*<br/>
要复制到新的 `_variant_t` 对象中的 `_variant_t` 对象。

*fCopy*<br/>
如果 **`false`** 为，则将提供的 `VARIANT` 对象附加到新的 `_variant_t` 对象，而不生成新的副本 `VariantCopy` 。

*ISrc, sSrc*<br/>
要复制到新的 `_variant_t` 对象中的整数值。

*vtSrc*<br/>
`VARTYPE`新 `_variant_t` 对象的。

*fltSrc, dblSrc*<br/>
要复制到新的 `_variant_t` 对象中的数值。

*cySrc*<br/>
要复制到新的 `CY` 对象中的 `_variant_t` 对象。

*bstrSrc*<br/>
要复制到新的 `_bstr_t` 对象中的 `_variant_t` 对象。

*strSrc, wstrSrc*<br/>
要复制到新的 `_variant_t` 对象中的字符串。

*bSrc*<br/>
**`bool`** 要复制到新对象中的值 `_variant_t` 。

*pIUknownSrc*<br/>
指向要封装到新对象中的 VT_UNKNOWN 对象的 COM 接口指针 `_variant_t` 。

*pDispSrc*<br/>
指向要封装到新对象中的 VT_DISPATCH 对象的 COM 接口指针 `_variant_t` 。

*decSrc*<br/>
要复制到新的 `DECIMAL` 对象中的 `_variant_t` 值。

*bSrc*<br/>
要复制到新的 `BYTE` 对象中的 `_variant_t` 值。

*cSrc*<br/>
**`char`** 要复制到新对象中的值 `_variant_t` 。

*usSrc*<br/>
**`unsigned short`** 要复制到新对象中的值 `_variant_t` 。

*ulSrc*<br/>
**`unsigned long`** 要复制到新对象中的值 `_variant_t` 。

*iSrc*<br/>
**`int`** 要复制到新对象中的值 `_variant_t` 。

*uiSrc*<br/>
**`unsigned int`** 要复制到新对象中的值 `_variant_t` 。

*i8Src*<br/>
**`__int64`** 要复制到新对象中的值 `_variant_t` 。

*ui8Src*<br/>
要复制到新对象中的 **未签名 __int64** 值 `_variant_t` 。

## <a name="remarks"></a>备注

- **_variant_t ( )** 构造空 `_variant_t` 的对象 `VT_EMPTY` 。

- **_variant_t ( 变体&** *varSrc* **)** `_variant_t` 从对象的副本构造对象 `VARIANT` 。     变体类型将保留。

- **_variant_t ( 变体** <strong>\*</strong>*pVarSrc* **)** `_variant_t` 从对象的副本构造对象 `VARIANT` 。     变体类型将保留。

- **_variant_t ( _variant_t&** *var_t_Src* **)** `_variant_t` 从另一个对象构造对象 `_variant_t` 。     变体类型将保留。

- **_variant_t ( 变体&** *varSrc* **，bool** `fCopy` **)** `_variant_t` 用现有对象构造对象 `VARIANT` 。       如果 *fCopy* 为 **`false`** ，则 **变量** 对象将附加到新的对象，而不进行复制。

- **_variant_t ( short***sSrc* **，VARTYPE** `vtSrc` **= VT_I2 )** `_variant_t` 从整数值构造一个类型 VT_I2 或 VT_BOOL 的对象 **`short`** 。       任何其他 `VARTYPE` 结果将导致 E_INVALIDARG 错误。

- **_variant_t ( 长** `lSrc`**，VARTYPE** `vtSrc`**= VT_I4 )** 构造 `_variant_t` 从整数值 VT_I4、VT_BOOL 或 VT_ERROR 类型的对象 **`long`** 。       任何其他 `VARTYPE` 结果将导致 E_INVALIDARG 错误。

- **_variant_t ( float** `fltSrc`**)**`_variant_t`从数值构造 VT_R4 类型的对象 **`float`** 。    

- **_variant_t ( 双精度** `dblSrc`**，VARTYPE** `vtSrc`**= VT_R8 )**`_variant_t`从数值构造 VT_R8 或 VT_DATE 类型的对象 **`double`** 。       任何其他 `VARTYPE` 结果将导致 E_INVALIDARG 错误。

- **_variant_t ( CY&** `cySrc`**)**`_variant_t`从对象构造 VT_CY 类型的对象 `CY` 。    

- **_variant_t ( _bstr_t&** `bstrSrc`**)**`_variant_t`从对象构造 VT_BSTR 类型的对象 `_bstr_t` 。     分配新的 `BSTR`。

- **_variant_t ( wchar_t** <strong>\*</strong>*wstrSrc* **)** `_variant_t` 从 Unicode 字符串构造 VT_BSTR 类型的对象。   分配新的 `BSTR`。

- **_variant_t ( 字符** <strong>\*</strong> `strSrc`**)** 构造 `_variant_t` 字符串类型 VT_BSTR 的对象。     分配新的 `BSTR`。

- **_variant_t ( bool** `bSrc`**)**`_variant_t`从值构造 VT_BOOL 类型的对象 **`bool`** 。    

- **( IUnknown _variant_t** <strong>\*</strong> `pIUknownSrc`**，bool** `fAddRef`**= true )**`_variant_t`从 COM 接口指针构造 VT_UNKNOWN 类型的对象。       如果 `fAddRef` 为 **`true`** ，则 `AddRef` 在提供的接口指针上调用，以匹配将在 `Release` 对象被销毁时进行的调用 `_variant_t` 。 你需要 `Release` 在提供的接口指针上调用。 如果 `fAddRef` 为 **`false`** ，则此构造函数将获得提供的接口指针的所有权; 不 `Release` 在提供的接口指针上调用。

- **_variant_t ( IDispatch** <strong>\*</strong> `pDispSrc`**，bool** `fAddRef`**= true )**`_variant_t`从 COM 接口指针构造 VT_DISPATCH 类型的对象。       如果 `fAddRef` 为 **`true`** ，则 `AddRef` 在提供的接口指针上调用，以匹配将在 `Release` 对象被销毁时进行的调用 `_variant_t` 。 你需要 `Release` 在提供的接口指针上调用。 如果 `fAddRef` 为 **`false`** ，则此构造函数将获得提供的接口指针的所有权; 不 `Release` 在提供的接口指针上调用。

- **_variant_t ( DECIMAL&** `decSrc`**)**`_variant_t`从值构造 VT_DECIMAL 类型的对象 `DECIMAL` 。    

- **_variant_t ( 字节** `bSrc`**)**`_variant_t`从值构造类型的对象 `VT_UI1` `BYTE` 。    

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_variant_t 类](../cpp/variant-t-class.md)
