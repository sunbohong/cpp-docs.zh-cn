---
description: 了解详细信息： TN032： MFC 异常机制
title: TN032：MFC 异常机制
ms.date: 11/04/2016
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
ms.openlocfilehash: 847d78762aaf5e04c8a0c1eb2170e951d0b867bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215529"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032：MFC 异常机制

以前版本的 Visual C++ 不支持标准 c + + 异常机制，而 MFC 提供的宏 **TRY/CATCH/THROW** 将改为使用。 此版本的 Visual C++ 完全支持 C++ 异常。 本说明包含以前的宏的高级实现详细信息，包括如何自动清理基于堆栈的对象。 由于 C++ 异常默认支持堆栈展开，此技术说明不再是必需的。

请参阅 [异常：使用 Mfc 宏和 c + + 异常](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) 获取有关 MFC 宏与新 c + + 关键字之间的差异的详细信息。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
