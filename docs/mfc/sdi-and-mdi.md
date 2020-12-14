---
description: 了解详细信息： SDI 和 MDI
title: SDI 和 MDI
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
ms.openlocfilehash: bfa54db04a657507b4b491ada6e8f08d17c2d1c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217778"
---
# <a name="sdi-and-mdi"></a>SDI 和 MDI

MFC 使使用单文档界面 (SDI) 和多文档界面 (MDI) 应用程序更容易。

SDI 应用程序一次只允许一个打开的文档框架窗口。 MDI 应用程序允许在同一个应用程序实例中打开多个文档框架窗口。 MDI 应用程序中有一个窗口，在该窗口中可以打开多个 MDI 子窗口，其中每个窗口都包含一个单独的文档。 在某些应用程序中，子窗口可以是不同的类型，例如图表窗口和电子表格窗口。 在这种情况下，菜单栏可以更改为已激活不同类型的 MDI 子窗口。

> [!NOTE]
> 在 Windows 95 和更高版本中，应用程序通常是 SDI，因为操作系统采用了 "文档居中" 视图。

有关详细信息，请参阅 [文档、视图和框架](../mfc/documents-views-and-the-framework.md)。

## <a name="see-also"></a>请参阅

[使用类编写适用于 Windows 的应用程序](../mfc/using-the-classes-to-write-applications-for-windows.md)
