---
description: 了解更多：可重写 CWinApp 成员函数
title: 可重写 CWinApp 成员函数
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 3958ad0edc1fbdb77e1f6ce3252fd03d7595344a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330101"
---
# <a name="overridable-cwinapp-member-functions"></a>可重写 CWinApp 成员函数

[CWinApp](reference/cwinapp-class.md) 提供几个关键可重写成员函数 (从 `CWinApp` 类 [CWinThread](reference/cwinthread-class.md)重写这些成员， `CWinApp` 派生) ：

- [InitInstance](initinstance-member-function.md)

- [运行](run-member-function.md)

- [ExitInstance](exitinstance-member-function.md)

- [OnIdle](onidle-member-function.md)

唯一一个必须重写的 `CWinApp` 成员函数是 `InitInstance`。

## <a name="see-also"></a>请参阅

[CWinApp：应用程序类](cwinapp-the-application-class.md)
