---
description: 详细了解如何开发您自己的延迟加载 helper 函数
title: 开发您自己的延迟加载 helper 函数
ms.date: 01/19/2021
helpviewer_keywords:
- helper functions
ms.openlocfilehash: 2845a426023ed8b5e2bcfb0056c9be6b829dd23a
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667432"
---
# <a name="develop-your-own-delay-load-helper-function"></a>开发您自己的延迟加载 helper 函数

你可能需要提供自己的延迟加载帮助程序例程的版本。 在您自己的例程中，您可以根据 DLL 的名称或导入执行特定的处理。 可以通过两种方式插入自己的代码：编写自己的 helper 函数代码，可能基于提供的代码。 或者，使用 [通知挂钩](notification-hooks.md)挂钩提供的帮助程序调用自己的函数。

## <a name="code-your-own-helper"></a>编写自己的帮助器

创建自己的帮助程序例程非常简单。 您可以使用现有代码作为新函数的指南。 函数必须使用与现有 helper 相同的调用约定。 而且，如果它返回到链接器生成的 thunk，则它必须返回适当的函数指针。 创建代码后，你可以根据需要满足调用或从调用中取出。

## <a name="use-the-start-processing-notification-hook"></a>使用启动处理通知挂钩

最简单的方法是提供一个新的指针，指向用户提供的通知挂钩函数，该函数采用与通知的默认 helper 相同的值 `dliStartProcessing` 。 此时，挂钩函数可能会成为新的 helper 函数，因为成功返回到默认帮助器会绕过默认帮助器中的所有进一步处理。

## <a name="see-also"></a>另请参阅

[链接器的延迟加载 DLL 支持](linker-support-for-delay-loaded-dlls.md)
