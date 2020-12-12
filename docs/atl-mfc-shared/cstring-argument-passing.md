---
description: 了解详细信息： CString 参数传递
title: CString 自变量传递
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
ms.openlocfilehash: ee47898ffdfc5129b11b0f9480669fa142d12818
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167170"
---
# <a name="cstring-argument-passing"></a>CString 自变量传递

本文介绍如何向函数传递 [CString](../atl-mfc-shared/reference/cstringt-class.md) 对象，以及如何 `CString` 从函数返回对象。

## <a name="cstring-argument-passing-conventions"></a><a name="_core_cstring_argument.2d.passing_conventions"></a> CString Argument-Passing 约定

定义类接口时，必须为成员函数确定参数传递约定。 有一些标准规则用于传递和返回 `CString` 对象。 如果将字符串中所述的规则 [作为函数输入](#_core_strings_as_function_inputs) 和 [字符串作为函数输出](#_core_strings_as_function_outputs)，则会获得有效的、正确的代码。

## <a name="strings-as-function-inputs"></a><a name="_core_strings_as_function_inputs"></a> 作为函数输入的字符串

使用被调用函数中的对象的最有效、安全的方法 `CString` 是将 `CString` 对象传递给函数。 不管名称如何， `CString` 对象在内部都不会将字符串存储为具有 null 终止符的 C 样式字符串。 相反， `CString` 对象会仔细跟踪其具有的字符数。 `CString`如果你的代码必须经常执行该操作，则将提供一个 LPCTSTR 指针，该指针指向以 null 结尾的字符串就会变得很重要。 由于对内容所做的任何更改都会 `CString` 使旧的 LPCTSTR 指针副本失效，因此结果是暂时性的。

在某些情况下，有必要提供 C 样式字符串。 例如，在某些情况下，调用的函数是用 C 编写的，不支持对象。 在这种情况下， `CString` 将参数强制转换为 LPCTSTR，函数将获取 C 样式的以 null 结尾的字符串。 还可以 `CString` 通过使用 `CString` 接受 C 样式字符串参数的构造函数，以另一个方向来创建对象。

如果字符串内容要由函数更改，请将参数声明为)  (的非常量 `CString` 引用 `CString&` 。

## <a name="strings-as-function-outputs"></a><a name="_core_strings_as_function_outputs"></a> 作为函数输出的字符串

通常，你可以 `CString` 从函数返回对象，因为 `CString` 对象跟随值语义（如基元类型）。 若要返回只读字符串，请使用常量 `CString` 引用 (`const CString&`) 。 下面的示例阐释了 `CString` 参数和返回类型的用法：

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>请参阅

[ATL/MFC (字符串) ](../atl-mfc-shared/strings-atl-mfc.md)
