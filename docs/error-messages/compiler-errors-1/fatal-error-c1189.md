---
description: 了解详细信息：严重错误 C1189
title: 错误 C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 4e71903c6567aedf85de81db59b66e45684d8507
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123586"
---
# <a name="fatal-error-c1189"></a>错误 C1189

> **\# 错误：** *用户提供的错误消息*

## <a name="remarks"></a>备注

C1189 是由指令生成的 `#error` 。 编码指令的开发人员指定错误消息的文本。 有关详细信息，请参阅 [C/c + + (#error 指令) ](../../preprocessor/hash-error-directive-c-cpp.md)。

## <a name="example"></a>示例

下面的示例生成 C1189。 在此示例中，开发人员发出自定义错误消息，因为 `_WIN32` 未定义标识符：

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>请参阅

[ (C/c + + 的 #define 指令) ](../../preprocessor/hash-define-directive-c-cpp.md)
