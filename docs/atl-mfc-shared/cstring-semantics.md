---
description: 了解详细信息： CString 语义
title: CString 语义
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: 7c6dde91e7f87908c0c6bc2d49ff455eb79f6eb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167040"
---
# <a name="cstring-semantics"></a>CString 语义

尽管 [CString](../atl-mfc-shared/reference/cstringt-class.md) 对象是可增长的动态对象，但它们的行为类似于内置的基元类型和简单的类。 每个 `CString` 对象都表示一个唯一值。 `CString` 对象应被视为实际的字符串，而不是指向字符串的指针。

可以将一个 `CString` 对象分配给另一个对象。 但是，当修改这两个 `CString` 对象中的一个对象时， `CString` 不会修改其他对象，如下面的示例所示：

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

请注意，在此示例中，两个 `CString` 对象都被视为 "等于"，因为它们表示相同的字符串。 `CString`类重载了相等运算符， (`==`) 根据两个 `CString` 对象的值 (内容来比较两个对象，而不是)  (地址) 的标识。

## <a name="see-also"></a>请参阅

[ATL/MFC (字符串) ](../atl-mfc-shared/strings-atl-mfc.md)
