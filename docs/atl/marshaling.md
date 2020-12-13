---
description: 了解更多：封送处理
title: 封送
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 2931bd9ab5e2fb8376ced44dd519a6de107be88e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152628"
---
# <a name="marshaling"></a>封送

封送的 COM 方法允许在一个进程中使用对象公开的接口，以便在另一个进程中使用。 在封送处理中，COM 提供代码 (或使用接口实现器提供的代码) 将方法的参数打包为一种格式，该格式可跨跨进程 (，以及跨网络移动到其他计算机上运行的进程) 并将这些参数解包。 同样，COM 必须在从调用返回时执行相同的步骤。

> [!NOTE]
> 当对象提供的接口与对象在同一进程中使用时，通常不需要封送处理。 但是，线程之间可能需要封送处理。

## <a name="see-also"></a>请参阅

[COM 简介](../atl/introduction-to-com.md)<br/>
[封送详细信息](/windows/win32/com/marshaling-details)
