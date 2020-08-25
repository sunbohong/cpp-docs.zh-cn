---
title: 异常处理宏
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 7fcd8221ba5f121749cf366a93cc8a6d8d00ed7c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833434"
---
# <a name="exception-handling-macros"></a>异常处理宏

这些宏为异常处理提供支持。

|名称|说明|
|-|-|
|[_ATLCATCH](#_atlcatch)|语句 (s) 来处理关联的中发生的错误 `_ATLTRY` 。|
|[_ATLCATCHALL](#_atlcatchall)|语句 (s) 来处理关联的中发生的错误 `_ATLTRY` 。|
|[_ATLTRY](#_atltry)|标记一个受保护的代码部分，其中可能出现错误。|

## <a name="requirements"></a>要求：

**标头：** atldef

## <a name="_atlcatch"></a><a name="_atlcatch"></a> _ATLCATCH

语句 (s) 来处理关联的中发生的错误 `_ATLTRY` 。

```
_ATLCATCH(e)
```

### <a name="parameters"></a>参数

*e*<br/>
要捕获的异常。

### <a name="remarks"></a>注解

与结合使用 `_ATLTRY` 。 解析为 c + + [catch (CAtlException e) ](../../cpp/try-throw-and-catch-statements-cpp.md) ，用于处理给定类型的 c + + 异常。

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a> _ATLCATCHALL

语句 (s) 来处理关联的中发生的错误 `_ATLTRY` 。

```
_ATLCATCHALL
```

### <a name="remarks"></a>注解

与结合使用 `_ATLTRY` 。 解析为 c + + [catch ( ... ) ](../../cpp/try-throw-and-catch-statements-cpp.md) ，用于处理所有类型的 c + + 异常。

## <a name="_atltry"></a><a name="_atltry"></a> _ATLTRY

标记一个受保护的代码部分，其中可能出现错误。

```
_ATLTRY
```

### <a name="remarks"></a>注解

与 [_ATLCATCH](#_atlcatch) 或 [_ATLCATCHALL](#_atlcatchall)结合使用。 解析为 c + + 符号 [try](../../cpp/try-throw-and-catch-statements-cpp.md)。

## <a name="see-also"></a>另请参阅

[宏](../../atl/reference/atl-macros.md)
