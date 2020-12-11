---
description: 了解详细信息：有关在 ATL 和 MFC 之间进行选择的建议
title: 在 ATL 和 MFC 之间进行选择的建议
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: 506df04ebbd3bc9079e1d40cf14773d9d9a6bd1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159149"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>在 ATL 和 MFC 之间进行选择的建议

开发组件和应用程序时，可以选择两种方法： ATL 和 MFC (Microsoft 基础类库) 。

## <a name="using-atl"></a>使用 ATL

ATL 是在 c + + 中创建 COM 组件并保持较小的占用空间的一种快速、简单的方式。 如果不需要 MFC 自动提供的所有内置功能，请使用 ATL 创建控件。

## <a name="using-mfc"></a>使用 MFC

MFC 允许您创建完整的应用程序、ActiveX 控件和活动文档。 如果已使用 MFC 创建了一个控件，则可能需要继续在 MFC 中进行开发。 创建新的控件时，如果不需要 MFC 的所有内置功能，请考虑使用 ATL。

## <a name="using-atl-in-an-mfc-project"></a>在 MFC 项目中使用 ATL

您可以通过运行向导来添加对在现有 MFC 项目中使用 ATL 的支持。 有关详细信息，请参阅向 [MFC 项目添加 ATL 支持](../mfc/reference/adding-atl-support-to-your-mfc-project.md)。

## <a name="see-also"></a>请参阅

[ATL 简介](../atl/introduction-to-atl.md)
