---
description: 了解详细信息： TN003：将 Windows 句柄映射到对象
title: TN003：将 Windows 句柄映射到对象
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: e4a0bfa2315ec2b9d67d884d4fdebe314599f454
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216036"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003：将 Windows 句柄映射到对象

此注释介绍了支持将 Windows 对象句柄映射到 c + + 对象的 MFC 例程。

## <a name="the-problem"></a>问题

Windows 对象通常由各种 [句柄](/windows/win32/WinProg/windows-data-types) 对象表示，MFC 类使用 c + + 对象包装 windows 对象句柄。 MFC 类库的句柄包装函数允许您查找 c + + 对象，该对象包装有特定句柄的 Windows 对象。 但是，有时对象没有 c + + 包装对象，在这种情况下，系统将创建一个临时对象作为 c + + 包装。

使用句柄映射的 Windows 对象如下所示：

- HWND ([CWnd](../mfc/reference/cwnd-class.md) 和 `CWnd` 派生类) 

- HDC ([CDC](../mfc/reference/cdc-class.md) `CDC` 派生类和派生类) 

- HMENU ([CMenu](../mfc/reference/cmenu-class.md)) 

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md)) 

- HBRUSH (`CGdiObject`) 

- HFONT (`CGdiObject`) 

- HBITMAP (`CGdiObject`) 

- HPALETTE (`CGdiObject`) 

- HRGN (`CGdiObject`) 

- HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md)) 

- 套接字 ([CSocket](../mfc/reference/csocket-class.md)) 

给定这些对象的一个句柄，可以通过调用静态方法查找包装句柄的 MFC 对象 `FromHandle` 。 例如，假设有一个名为 *hwnd* 的 hwnd，以下行将返回一个指向 `CWnd` 包装 *HWND* 的的指针：

```
CWnd::FromHandle(hWnd)
```

如果 *hWnd* 没有特定的包装器对象， `CWnd` 则会创建一个临时对象来包装 *hwnd*。 这样就可以从任何句柄获取有效的 c + + 对象。

具有包装器对象后，可以从包装类的公共成员变量中检索其句柄。 对于 `CWnd` ， *m_hWnd* 包含该对象的 hWnd。

## <a name="attaching-handles-to-mfc-objects"></a>将句柄附加到 MFC 对象

给定新创建的句柄包装器对象和 Windows 对象的句柄时，可以通过调用函数来关联两者， `Attach` 如以下示例中所示：

```
CWnd myWnd;
myWnd.Attach(hWnd);
```

这会使永久映射中的条目关联 *myWnd* 和 *hWnd*。 调用 `CWnd::FromHandle(hWnd)` 现在将返回指向 *myWnd* 的指针。 删除 *myWnd* 后，析构函数将通过调用 Windows [DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow)函数自动销毁 *hWnd* 。 如果不需要这种情况，则必须先从 *myWnd* 中分离 *hWnd* ，然后才能在离开定义 *myWnd*) 的作用域的情况下 (销毁 *myWnd* 。 `Detach`方法执行此。

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>有关临时对象的详细信息

当 `FromHandle` 给定的句柄尚无包装对象时，将创建临时对象。 这些临时对象与它们的句柄分离，并由 `DeleteTempMap` 函数删除。 默认情况下， [CWinThread：： OnIdle](../mfc/reference/cwinthread-class.md#onidle) 会自动 `DeleteTempMap` 为支持临时句柄映射的每个类调用。 这意味着，不能假定指向临时对象的指针将在从其获取指针的函数中退出时有效。

## <a name="wrapper-objects-and-multiple-threads"></a>包装对象和多个线程

临时和永久对象均按线程进行维护。 也就是说，一个线程不能访问另一个线程的 c + + 包装对象，无论该对象是临时的还是永久的。

若要将这些对象从一个线程传递到另一个线程，请始终将它们作为其本机 `HANDLE` 类型发送。 将 c + + 包装对象从一个线程传递到另一个线程通常会导致意外的结果。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
