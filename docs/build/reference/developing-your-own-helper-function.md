---
description: 了解详细信息：开发您自己的 Helper 函数
title: 开发您自己的 Helper 函数
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
ms.openlocfilehash: da536d13da9a596c5667c3fa84311b73e66d71ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201451"
---
# <a name="developing-your-own-helper-function"></a>开发您自己的 Helper 函数

你可能需要提供自己的例程版本，以根据 DLL 或导入的名称进行特定处理。 可通过两种方法执行此操作：编写自己的代码，可能基于提供的代码，或者仅使用之前详细的通知挂钩挂钩提供的版本。

## <a name="code-your-own"></a>自行编写代码

这相当简单，因为你实质上可以使用所提供的代码作为新代码的指导原则。 当然，它必须遵循调用约定，并且如果它返回到链接器生成的 thunk，则必须返回适当的函数指针。 在代码中，可以执行任何所需的操作，以便满足调用或跳出调用。

## <a name="use-the-start-processing-notification-hook"></a>使用启动处理通知挂钩

最简单的方法是，只需提供一个指向用户提供的通知挂钩函数的新指针，接收与通知 dliStartProcessing 上默认 helper 相同的值。 此时，挂钩函数可能会成为新的 helper 函数，因为成功返回到默认帮助程序将绕过默认帮助程序中的所有进一步处理。

## <a name="see-also"></a>请参阅

[Delay-Loaded Dll 的链接器支持](linker-support-for-delay-loaded-dlls.md)
