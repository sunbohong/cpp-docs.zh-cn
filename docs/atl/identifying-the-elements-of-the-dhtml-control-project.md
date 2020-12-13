---
description: 了解详细信息：标识 DHTML 控件项目的元素
title: 标识 DHTML 控件项目的元素
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: 7f04857378564a86fc875e9874b79f6ae6c6a625
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148013"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>标识 DHTML 控件项目的元素

大多数 DHTML 控制代码与为任何 ATL 控件创建的代码完全相同。 有关一般代码的基本了解，请通过 [atl 教程](../atl/active-template-library-atl-tutorial.md)，并阅读 [创建 ATL 项目](../atl/reference/creating-an-atl-project.md) 和 [atl COM 对象基础的](../atl/fundamentals-of-atl-com-objects.md)部分。

DHTML 控件类似于任何 ATL 控件，只不过：

- 除了控件实现的常规接口外，它还实现了一个附加接口，该接口用于在 c + + 代码和 HTML 用户界面之间 (UI) 之间进行通信。 HTML UI 使用此接口调用 c + + 代码。

- 它创建控件 UI 的 HTML 资源。

- 它允许通过成员变量访问 DHTML 对象模型，该成员变量 `m_spBrowser` 是 [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))类型的智能指针。 使用此指针可访问 DHTML 对象模型的任何部分。

下图说明了 DLL、DHTML 控件、Web 浏览器和 HTML 资源之间的关系。

![DHTML 控件项目的元素](../atl/media/vc52en1.gif "DHTML 控件项目的元素")

> [!NOTE]
> 此图形上的名称是占位符。 您的 HTML 资源的名称以及在控件上公开的接口将基于您在 ATL 控件向导中为其分配的名称。

在此图中，元素为：

- **我的 DLL** 使用 ATL 项目向导创建的 DLL。

- **Dhtml** 控件 (`m_spBrowser`) 使用 ATL 对象向导创建的 dhtml 控件。 此控件通过 Web 浏览器对象的接口访问 Web 浏览器对象及其方法 `IWebBrowser2` 。 除了控件所需的其他标准接口，控件本身还公开以下两个接口。

  - `IDHCTL1` 控件公开的接口，仅供容器使用。

  - `IDHCTLUI1` 用于在 c + + 代码和 HTML 用户界面之间进行通信的调度接口。 Web 浏览器使用控件的调度接口显示控件。 您可以通过调用 `window.external` ，然后调用此调度接口上要调用的方法名称，从控件的用户界面调用此调度接口的各种方法。 你将 `window.external` 从组成此控件的 UI 的 HTML 内的脚本标记访问。 有关调用资源文件中的外部方法的详细信息，请参阅 [从 DHTML 调用 c + + 代码](../atl/calling-cpp-code-from-dhtml.md)。

- **IDR_CTL1** HTML 资源的资源 ID。 在此示例中，其文件名为 DHCTL1UI.htm。 DHTML 控件使用包含标准 HTML 标记和可使用文本编辑器进行编辑的外部窗口调度命令的 HTML 资源。

- **Web 浏览器** Web 浏览器将基于 HTML 资源中的 HTML 显示控件的 UI。 DHTML 控件中提供了指向 Web 浏览器的接口的指针 `IWebBrowser2` ，以允许访问 dhtml 对象模型。

ATL 控件向导使用 HTML 资源和 .cpp 文件中的默认代码生成控件。 您可以编译并运行向导生成的控件，然后在 Web 浏览器或 ActiveX 控件测试容器中查看控件。 下图显示了 "测试容器" 中显示了三个按钮的默认 ATL DHTML 控件：

![ATL DHTML 控件](../atl/media/vc52en2.gif "ATL DHTML 控件")

请参阅 [创建 ATL DHTML 控件](../atl/creating-an-atl-dhtml-control.md) 开始生成 DHTML 控件。 请参阅 [使用测试容器测试属性和事件](../mfc/testing-properties-and-events-with-test-container.md) 了解有关如何访问测试容器的信息。

## <a name="see-also"></a>请参阅

[支持 DHTML 控件](../atl/atl-support-for-dhtml-controls.md)
