---
description: 了解更多：销毁框架窗口
title: 销毁框架窗口
ms.date: 11/04/2016
f1_keywords:
- PostNcDestroy
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
ms.openlocfilehash: 192b1b21881f4a9f94a4fb1d6c7b18b4a91ac579
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327861"
---
# <a name="destroying-frame-windows"></a>销毁框架窗口

MFC 框架管理窗口析构，并为与框架文档和视图关联的窗口进行创建。 如果创建其他窗口，您将负责销毁它们。

在框架中，当用户关闭框架窗口时，窗口的默认 [OnClose](reference/cwnd-class.md#onclose) 处理程序将调用 [DestroyWindow](reference/cwnd-class.md#destroywindow)。 销毁 Windows 窗口时调用的最后一个成员函数是 [OnNcDestroy](reference/cwnd-class.md#onncdestroy)，它执行一些清理，调用 [默认](reference/cwnd-class.md#default) 成员函数来执行 Windows 清理，最后调用虚拟成员函数 [PostNcDestroy](reference/cwnd-class.md#postncdestroy)。 的 [CFrameWnd](reference/cframewnd-class.md) 实现将 `PostNcDestroy` 删除 c + + 窗口对象。 绝不应 **`delete`** 在框架窗口中使用 c + + 运算符。 请改用 `DestroyWindow`。

主窗口关闭时，应用程序将关闭。 如果已修改未保存的文档，框架将显示一个消息框，询问是否应保存文档，并确保在必要时保存适当的文档。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [创建文档框架窗口](creating-document-frame-windows.md)

## <a name="see-also"></a>请参阅

[使用框架窗口](using-frame-windows.md)
