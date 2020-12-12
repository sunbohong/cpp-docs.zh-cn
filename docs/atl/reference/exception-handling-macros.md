---
description: 了解详细信息：异常处理宏
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
ms.openlocfilehash: 8d5e6564dec5769fb172c66b3102677e58cbd788
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139823"
---
# <a name="exception-handling-macros"></a>异常处理宏

这些宏为异常处理提供支持。

|名称|描述|
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

### <a name="parameters"></a>parameters

*e*<br/>
要捕获的异常。

### <a name="remarks"></a>备注

与结合使用 `_ATLTRY` 。 解析为 c + + [catch (CAtlException e) ](../../cpp/try-throw-and-catch-statements-cpp.md) ，用于处理给定类型的 c + + 异常。

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a> _ATLCATCHALL

语句 (s) 来处理关联的中发生的错误 `_ATLTRY` 。

```
_ATLCATCHALL
```

### <a name="remarks"></a>备注

与结合使用 `_ATLTRY` 。 解析为 c + + [catch ( ... ) ](../../cpp/try-throw-and-catch-statements-cpp.md) ，用于处理所有类型的 c + + 异常。

## <a name="_atltry"></a><a name="_atltry"></a> _ATLTRY

标记一个受保护的代码部分，其中可能出现错误。

```
_ATLTRY
```

### <a name="remarks"></a>备注

与 [_ATLCATCH](#_atlcatch) 或 [_ATLCATCHALL](#_atlcatchall)结合使用。 解析为 c + + 符号 [try](../../cpp/try-throw-and-catch-statements-cpp.md)。

## <a name="see-also"></a>请参阅

[宏](../../atl/reference/atl-macros.md)
