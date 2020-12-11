---
description: 了解更多相关信息： ATL Module 类
title: ATL Module 类
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 16c38a6a38f4179e5846a445bd9573e7dc4500f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163296"
---
# <a name="atl-module-classes"></a>ATL Module 类

本主题讨论 ATL 7.0 中新增的模块类。

## <a name="ccommodule-replacement-classes"></a>CComModule 替换类

使用的早期版本的 ATL `CComModule` 。 在 ATL 7.0 中， `CComModule` 功能已由多个类替换：

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) 包含大多数使用 ATL 的应用程序所需的信息。 包含模块和资源实例的 HINSTANCE。

- [CAtlComModule](../atl/reference/catlcommodule-class.md) 包含 ATL 中 COM 类所需的信息。

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) 包含 ATL 中的窗口化类所需的信息。

- [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) 包含对接口调试的支持。

- [CAtlModule](../atl/reference/catlmodule-class.md) 以下 `CAtlModule` 派生类自定义为包含特定应用程序类型中所需的信息。 可以重写这些类中的大多数成员：

  - [Catldllmodulet 用作基类](../atl/reference/catldllmodulet-class.md) 在 DLL 应用程序中使用。 为标准导出提供代码。

  - [Catlexemodulet 用作](../atl/reference/catlexemodulet-class.md) 在 EXE 应用程序中使用。 提供 EXE 中所需的代码。

  - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) 为创建 Windows NT 和 Windows 2000 服务提供支持。

`CComModule` 仍可用于向后兼容。

## <a name="reasons-for-distributing-ccommodule-functionality"></a>分发 CComModule 功能的原因

的功能 `CComModule` 被分发到几个新类中，原因如下：

- 使功能更 `CComModule` 精细。

   对于 COM、窗口化、接口调试和特定于应用程序的 (DLL 或 EXE) 功能的支持现在位于单独的类中。

- 自动声明每个模块的全局实例。

   所需模块类的全局实例链接到项目。

- 消除调用 Init 和 Term 方法的必要性。

   Init 和 Term 方法已移入模块类的构造函数和析构函数;不再需要调用 Init 和字词。

## <a name="see-also"></a>请参阅

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[类概述](../atl/atl-class-overview.md)
