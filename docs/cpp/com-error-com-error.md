---
description: 了解详细信息： _com_error：： _com_error
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 2c5b912f5d532e9aed5b8e84a3fe7e2fcd7d4100
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332564"
---
# <a name="_com_error_com_error"></a>_com_error::_com_error

**Microsoft 专用**

构造一个 **_com_error** 对象。

## <a name="syntax"></a>语法

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>parameters

*小时*<br/>
HRESULT 信息。

*perrinfo*<br/>
`IErrorInfo` 对象。

*fAddRef*<br/>
默认情况下，构造函数在非 null 接口上调用 AddRef `IErrorInfo` 。 这会在将接口所有权传递到 **_com_error** 对象的常见情况下提供正确的引用计数，例如：

```cpp
throw _com_error(hr, perrinfo);
```

如果你不希望代码将所有权转移到 **_com_error** 对象，并且 `AddRef` 需要 `Release` 在 **_com_error** 析构函数中偏移，则按如下方式构造对象：

```cpp
_com_error err(hr, perrinfo, true);
```

*that*<br/>
现有的 **_com_error** 对象。

## <a name="remarks"></a>备注

第一个构造函数将创建一个具有 HRESULT 和可选对象的新对象 `IErrorInfo` 。 第二个创建现有 **_com_error** 对象的副本。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
