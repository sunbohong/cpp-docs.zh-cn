---
description: 了解详细信息：控件：常规支持类
title: ATL 控件：常规支持类
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: a5b147ef2b30f0cc209fdfdabd52b59d7112c475
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148208"
---
# <a name="controls-general-support-classes"></a>控件：常规支持类

以下类提供对 ATL 控件的一般支持：

- [CComControl](../atl/reference/ccomcontrol-class.md) 包含 ATL 控件所必需的 helper 函数和数据成员。

- [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) 提供控件所需的方法。

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) 提供容器与控件进行通信时使用的主要方法。 管理就地控件的激活和停用。

- [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) 将初始化组合为单一调用，帮助容器避免加载控件时出现延迟。

- [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) 为非活动控件提供最少的鼠标交互。

## <a name="sample-program"></a>示例程序

[ATLFire](../overview/visual-cpp-samples.md)

## <a name="related-articles"></a>相关文章

[ATL 教程](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>请参阅

[类概述](../atl/atl-class-overview.md)
