---
description: 详细了解：DLL 中的自动化
title: DLL 中的自动化
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: e0d6d0beec71f3994f6e726c6946b2069d1b081b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163231"
---
# <a name="automation-in-a-dll"></a>DLL 中的自动化

当你在 MFC DLL 向导中选择“自动化”选项时，该向导提供以下内容：

- 一个初学者对象说明语言 (.ODL) 文件

- 一个用于 Afxole.h 的 STDAFX.h 文件中的 include 指令

- 一个 `DllGetClassObject` 函数的实现，其调用 AfxDllGetClassObject 函数 

- 一个 `DllCanUnloadNow` 函数的实现，其调用 AfxDllCanUnloadNow 函数 

- 一个 `DllRegisterServer` 函数的实现，其调用 [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) 函数

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

- [自动化服务器](../mfc/automation-servers.md)

## <a name="see-also"></a>请参阅

[在 Visual Studio 中创建 C/C++ DLL](dlls-in-visual-cpp.md)
