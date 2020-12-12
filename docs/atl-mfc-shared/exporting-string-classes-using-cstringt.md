---
description: 了解详细信息：使用 CStringT 导出字符串类
title: 使用 CStringT 导出字符串类
ms.date: 11/04/2016
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
ms.openlocfilehash: 8876ea04f1252e4f5861a950b04dabcd99d6a804
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166988"
---
# <a name="exporting-string-classes-using-cstringt"></a>使用 CStringT 导出字符串类

在过去，MFC 开发人员派生自 `CString` 来专用化自己的字符串类。 在 Microsoft Visual C++ .NET (MFC 8.0) ， [CString](../atl-mfc-shared/using-cstring.md) 类被称为 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)的模板类取代。 这提供了几个优点：

- 它允许 MFC `CString` 类在 ATL 项目中使用，而无需链接到较大的 MFC 静态库或 DLL 中。

- 使用新的 `CStringT` 模板类，可以 `CString` 使用指定字符特征的模板参数自定义行为，类似于 c + + 标准库中的模板。

- 使用从 DLL 导出自己的字符串类时 `CStringT` ，编译器也会自动导出 `CString` 基类。 由于 `CString` 本身是一个模板类，因此，它可能会在使用时被编译器实例化，除非编译器知道 `CString` 是从 DLL 导入的。 如果已将项目从 Visual C++ 6.0 迁移到 Visual C++ .NET，则 `CString` 由于 `CString` 从 DLL 和本地实例化的版本中导入的冲突，你可能已针对乘法定义显示了链接器符号错误。 下面介绍了执行此操作的正确方法。

以下方案将导致链接器为定义的类相乘产生符号错误。 假设要 `CString` `CMyString` 从 MFC 扩展 DLL 中导出派生类 () ：

[!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]

使用者代码使用和的组合 `CString` `CMyString` 。 "MyString" 未包含在预编译标头中，某些用法 `CString` 不 `CMyString` 可见。

假设你在单独的 `CString` `CMyString` 源文件（Source1 和 Source2）中使用和类。 在 Source1 中，使用 `CMyString` 并 #include MyString。 在 Source2 中，使用 `CString` ，但不 #include MyString。 在这种情况下，链接器会抱怨 `CStringT` 定义了多次。 这是由 `CString` 编译器从导出的 DLL 导入的 `CMyString` ，并通过模板在本地实例化 `CStringT` 。

若要解决此问题，请执行以下操作：

导出 `CStringA` 和 `CStringW` (，以及从 MFC90.DLL 中) 所需的基类。 包含 MFC 的项目将始终使用导出的 MFC DLL `CStringA` 和 `CStringW` ，如以前的 mfc 实现中所述。

然后，使用模板创建可导出的派生类 `CStringT` ，如下所示 `CStringT_Exported` ：

[!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]

在 AfxStr 中，按如下所示替换前面的 `CString` 、 `CStringA` 和 `CStringW` typedef：

[!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]

需要注意以下几点：

- 不应导出 `CStringT` 自身，因为这会导致只使用 ATL 的项目导出专用 `CStringT` 类。

- 使用可导出的派生类 `CStringT` 来最大限度地减少需要重新实现 `CStringT` 功能的功能。 其他代码仅限于将构造函数转发到 `CStringT` 基类。

- `CString``CStringA` `CStringW` 仅 `__declspec(dllexport/dllimport)` 当使用 MFC 共享 DLL 进行生成时，才应标记、和。 如果链接到 MFC 静态库，则不应将这些类标记为已导出;否则， `CString` `CStringA` 在用户 dll 内部使用、和 `CStringW` 将标记 `CString` 为导出。

## <a name="related-topics"></a>相关主题

[CStringT 类](../atl-mfc-shared/reference/cstringt-class.md)

## <a name="see-also"></a>请参阅

[使用 CStringT](../atl-mfc-shared/using-cstringt.md)<br/>
[使用 CString](../atl-mfc-shared/using-cstring.md)
