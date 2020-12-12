---
description: 了解详细信息：从 DHTML 调用 c + + 代码
title: 从 DHTML 调用 c + + 代码
ms.date: 11/04/2016
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
ms.openlocfilehash: d880b0e9cb2f0b9d5228df7da4fc96fceeb87943
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148481"
---
# <a name="calling-c-code-from-dhtml"></a>从 DHTML 调用 c + + 代码

DHTML 控件可以托管在容器中，如测试容器或 Internet Explorer。 请参阅 [使用测试容器测试属性和事件](../mfc/testing-properties-and-events-with-test-container.md) 了解有关如何访问测试容器的信息。

承载该控件的容器使用普通控件接口与控件进行通信。 DHTML 使用以 "UI" 结尾的调度接口，与 c + + 代码和 HTML 资源通信。 在 [修改 ATL DHTML 控件](../atl/modifying-the-atl-dhtml-control.md)时，可以练习添加这些不同接口要调用的方法。

若要查看从 DHTML 调用 c + + 代码的示例，请使用 ATL 控件向导 [创建 DHTML 控件](../atl/creating-an-atl-dhtml-control.md) ，并检查标头文件和 HTML 文件中的代码。

## <a name="declaring-webbrowser-methods-in-the-header-file"></a>在标头文件中声明 WebBrowser 方法

若要从 DHTML UI 调用 c + + 方法，必须将方法添加到控件的 UI 接口。 例如，ATL 控件向导创建的头文件包含 c + + 方法，该方法 `OnClick` 是向导生成的控件的 UI 接口的成员。

`OnClick`在控件的 .h 文件中检查：

[!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]

第一个参数 *pdispBody* 是指向主体对象的调度接口的指针。 第二个参数 *varColor* 标识要应用于控件的颜色。

## <a name="calling-c-code-in-the-html-file"></a>在 HTML 文件中调用 c + + 代码

在标头文件中声明了 WebBrowser 方法后，可以从 HTML 文件调用方法。 请注意，在 HTML 文件中 ATL 控件向导插入三个 Windows 调度方法：三个 `OnClick` 用于调度消息以更改控件的背景颜色的方法。

检查 HTML 文件中的方法之一：

`<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`

在上述 HTML 代码中，窗口外部方法 `OnClick` 作为按钮标记的一部分进行调用。 此方法具有两个参数： `theBody` ，它们引用 HTML 文档的正文， `"red"` 后者指示在单击按钮时，控件的背景色将更改为红色。 `Red`标记后面是按钮的标签。

有关提供您自己的方法的详细信息，请参阅 [修改 ATL DHTML 控件](../atl/modifying-the-atl-dhtml-control.md) 。 有关 HTML 文件的详细信息，请参阅 [标识 DHTML 控件项目的元素](../atl/identifying-the-elements-of-the-dhtml-control-project.md) 。

## <a name="see-also"></a>请参阅

[支持 DHTML 控件](../atl/atl-support-for-dhtml-controls.md)
