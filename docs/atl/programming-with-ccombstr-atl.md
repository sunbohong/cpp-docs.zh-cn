---
description: '了解更多相关信息：用 CComBSTR 编程 (ATL) '
title: 使用 CComBSTR 进行编程 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 6c348d703aeaeba40f1f47b8f6fd0ee858b7babd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159214"
---
# <a name="programming-with-ccombstr-atl"></a>使用 CComBSTR 进行编程 (ATL)

ATL 类 [CComBSTR](../atl/reference/ccombstr-class.md) 提供了围绕 BSTR 数据类型的包装。 虽然这 `CComBSTR` 是一个有用的工具，但有几种情况需要小心。

- [转换问题](#programmingwithccombstr_conversionissues)

- [范围问题](#programmingwithccombstr_scopeissues)

- [显式释放 CComBSTR 对象](#programmingwithccombstr_explicitlyfreeing)

- [在循环中使用 CComBSTR 对象](#programmingwithccombstr_usingloops)

- [内存泄漏问题](#programmingwithccombstr_memoryleaks)

## <a name="conversion-issues"></a><a name="programmingwithccombstr_conversionissues"></a> 转换问题

尽管若干 `CComBSTR` 方法会将 ANSI 字符串参数自动转换为 unicode，但方法将始终返回 unicode 格式字符串。 若要将输出字符串转换回 ANSI，请使用 ATL 转换类。 有关 ATL 转换类的详细信息，请参阅 [atl 和 MFC 字符串转换宏](reference/string-conversion-macros.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

如果使用字符串来修改 `CComBSTR` 对象，请使用宽字符字符串。 这会减少不必要的转换。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

## <a name="scope-issues"></a><a name="programmingwithccombstr_scopeissues"></a> 范围问题

与任何行为良好的类一样， `CComBSTR` 在超出范围时将释放其资源。 如果函数返回指向字符串的指针 `CComBSTR` ，这可能会导致问题，因为指针将引用已释放的内存。 在这些情况下，请使用 `Copy` 方法，如下所示。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

## <a name="explicitly-freeing-the-ccombstr-object"></a><a name="programmingwithccombstr_explicitlyfreeing"></a> 显式释放 CComBSTR 对象

在对象进入范围之前，可以显式释放对象中包含的字符串 `CComBSTR` 。 如果释放该字符串，则该 `CComBSTR` 对象无效。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

## <a name="using-ccombstr-objects-in-loops"></a><a name="programmingwithccombstr_usingloops"></a> 在循环中使用 CComBSTR 对象

由于 `CComBSTR` 类分配一个缓冲区来执行某些操作（如 `+=` 运算符或 `Append` 方法），因此，不建议在紧密循环内执行字符串操作。 在这些情况下， `CStringT` 提供更好的性能。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

## <a name="memory-leak-issues"></a><a name="programmingwithccombstr_memoryleaks"></a> 内存泄漏问题

将初始化为函数的的地址 `CComBSTR` 作为 **[out]** 参数传递将导致内存泄露。

在下面的示例中， `"Initialized"` 当函数替换字符串时，分配给保存字符串的字符串将泄漏 `MyGoodFunction` 。

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

若要避免泄漏，请 `Empty` 在将 `CComBSTR` 地址作为 **[out]** 参数传递之前对现有对象调用方法。

请注意，如果函数的参数为 **[in，out]，** 则相同的代码不会导致泄漏。

## <a name="see-also"></a>请参阅

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[CStringT 类](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[字符串转换宏](../atl/reference/string-conversion-macros.md)
