---
description: 了解详细信息：使用包含的窗口
title: 使用包含的窗口
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 11beb998365a10a8126e37ecbf7388ec6177e659
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138211"
---
# <a name="using-contained-windows"></a>使用包含的窗口

ATL 用 [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)实现包含的窗口。 包含窗口表示一个窗口，该窗口将其消息委托给容器对象，而不是在自己的类中对其进行处理。

> [!NOTE]
> 若要使用包含的窗口，无需从派生类 `CContainedWindowT` 。

对于包含的窗口，可以将现有 Windows 类的超类或子类成为现有窗口。 若要创建使现有 Windows 类成为超类的窗口，请先在对象的构造函数中指定现有的类名 `CContainedWindowT` 。 然后调用 `CContainedWindowT::Create` 。 若要为现有窗口划分子类，无需指定 Windows 类名称 (将 NULL 传递给构造函数) 。 只需调用 `CContainedWindowT::SubclassWindow` 具有子类的窗口句柄的方法。

通常使用包含的 windows 作为容器类的数据成员。 容器不需要为窗口;但它必须派生自 [CMessageMap](../atl/reference/cmessagemap-class.md)。

包含的窗口可以使用替换消息映射来处理其消息。 如果有多个包含窗口，应声明多个备用消息映射，每个映射对应于单独的包含窗口。

## <a name="example"></a>示例

下面是包含两个包含 windows 的容器类的示例：

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

有关包含的 windows 的详细信息，请参阅 [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) 示例。

## <a name="see-also"></a>请参阅

[窗口类](../atl/atl-window-classes.md)
