---
description: 了解详细信息： MFC 公共控件库的隔离
title: 隔离 MFC 公共控件库
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
ms.openlocfilehash: f3e0f6ad981a690f6212455b8af891eaa97f2642
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335828"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>隔离 MFC 公共控件库

公用控件库现在在 MFC 中处于隔离状态，通过在其清单中指定版本，允许不同模块（如用户 DLL）使用不同版本的公用控件库。

Mfc 应用程序 (或由 MFC 调用的用户代码) 通过名为 FunctionName 的包装函数调用公共控件库 Api `Afx` ，其中 *FUNCTIONNAME* 是公共控件 API 的名称。 这些包装器函数是在 afxcomctl32.h 和 afxcomctl32.inl 中定义的。

您可以使用 afxcomctl32.h) 中定义的 [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) 和 [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) 宏 (来确定公共控件库是否实现某个 API，而不是调用 [GetProcAddress](../build/getprocaddress.md)。

从技术上说，您可以通过包装器类 `CComCtlWrapper`（在 afxcomctl32.h 中定义）调用公共控件库 API。 `CComCtlWrapper` 还负责加载和卸载 comctl32.dll。 MFC 模块状态包含指向 `CComCtlWrapper` 实例的指针。 您可以使用 `afxComCtlWrapper` 宏来访问包装器类。

请注意，直接（不使用 MFC 包装器函数）从 MFC 应用程序或用户 DLL 调用公共控件 API 在大多数情况下有用，因为 MFC 应用程序或用户 DLL 将绑定到其在清单中请求的公共控件库。 但是，MFC 代码本身必须使用包装器，因为 MFC 代码可能是从使用不同公共控件库版本的用户 DLL 调用的。
