---
description: 了解详细信息： CString 异常清理
title: CString 异常清理
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: 9c77c9bf5d3f123315c126ce2361be63230c173b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167144"
---
# <a name="cstring-exception-cleanup"></a>CString 异常清理

在以前版本的 MFC 中，需要在使用后清理 [CString](../atl-mfc-shared/reference/cstringt-class.md) 对象，这一点非常重要。 在 MFC 版本3.0 及更高版本中，不再需要显式清除。

在 MFC 现在使用的 c + + 异常处理机制下，无需担心在发生异常后进行清理。 有关 c + + 在捕获异常后如何 "展开" 堆栈的说明，请参阅 [try、catch 和 throw 语句](../cpp/try-throw-and-catch-statements-cpp.md)。 即使使用 mfc **TRY** / **CATCH** 宏而不是 c + + 关键字， **`try`** **`catch`** mfc 也使用下面的 c + + 异常机制，因此您仍然无需显式清除。

## <a name="see-also"></a>请参阅

[ATL/MFC (字符串) ](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[异常处理](../mfc/exception-handling-in-mfc.md)
