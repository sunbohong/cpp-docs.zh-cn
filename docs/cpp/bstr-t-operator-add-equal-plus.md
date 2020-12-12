---
description: 了解详细信息： _bstr_t：： operator + =、+
title: _bstr_t::operator +=, +
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: e3ae71a3a43e189251ac0ddaf77572656a031aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308804"
---
# <a name="_bstr_toperator--"></a>_bstr_t::operator +=, +

**Microsoft 专用**

将字符追加到 `_bstr_t` 对象的结尾或串联两个字符串。

## <a name="syntax"></a>语法

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>parameters

s1<br/>
`_bstr_t` 对象。

*s2*<br/>
多字节字符串。

*s3*<br/>
一个 Unicode 字符串。

## <a name="remarks"></a>备注

以下运算符将执行字符串串联：

- **operator + = (** *s1* **)** 将封装的 s1 中的字符追加 `BSTR` 到该对象的封装末尾 `BSTR` 。    

- **operator + (** *s1* **)** 返回一个新 `_bstr_t` 的，它通过将此对象 `BSTR` 与 *s1* 的连接来形成。    

- **operator + (** *s2* **&#124;** *s1* **)** 返回一个新 `_bstr_t` 的，它通过将多字节字符串 *s2*（转换为 Unicode）连接到 `BSTR` *s1* 中封装的来形成。        

- **operator + (** *s3* **，***s1* **)** 返回一个新 `_bstr_t` 的，它通过将 Unicode 字符串 *s3* 与 `BSTR` *s1* 中封装的连接在一起形成。      

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_bstr_t 类](../cpp/bstr-t-class.md)
