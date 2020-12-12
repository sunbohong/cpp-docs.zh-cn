---
description: 了解详细信息：创建无模式对话框
title: 创建无模式对话框
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: c754391a0f1ab2713f3ce01b5d30ccc33be4aaa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309779"
---
# <a name="creating-modeless-dialog-boxes"></a>创建无模式对话框

对于无模式对话框，您必须在您的对话框类中提供自己的公共构造函数。 若要创建无模式对话框，请调用公共构造函数，然后调用对话框对象的 [create](reference/cdialog-class.md#create) 成员函数以加载对话框资源。 可以在构造函数调用期间或之后调用 **Create** 。 如果对话框资源的属性 **WS_VISIBLE**，则对话框将立即显示。 如果不是，则必须调用其 [ShowWindow](reference/cwnd-class.md#showwindow) 成员函数。

## <a name="see-also"></a>请参阅

[在 MFC 中使用对话框](life-cycle-of-a-dialog-box.md)
