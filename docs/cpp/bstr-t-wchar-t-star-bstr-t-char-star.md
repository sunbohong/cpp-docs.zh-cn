---
description: 了解详细信息： _bstr_t：： wchar_t *、_bstr_t：： char*
title: _bstr_t::wchar_t *、_bstr_t::char*
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
ms.openlocfilehash: 278b122bbc208addab8e9a40e61300ce91a530cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278813"
---
# <a name="_bstr_twchar_t-_bstr_tchar"></a>_bstr_t::wchar_t\*、_bstr_t::char\*

**Microsoft 专用**

将 BSTR 字符作为一个窄字符数组或宽字符数组返回。

## <a name="syntax"></a>语法

```
operator const wchar_t*( ) const throw( );
operator wchar_t*( ) const throw( );
operator const char*( ) const;
operator char*( ) const;
```

## <a name="remarks"></a>备注

这些运算符可用于提取由 `BSTR` 对象封装的字符数据。 为返回的指针赋予新值不会修改原始 BSTR 数据。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_bstr_t 类](../cpp/bstr-t-class.md)
