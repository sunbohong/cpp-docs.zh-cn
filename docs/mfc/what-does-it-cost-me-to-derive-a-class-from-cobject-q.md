---
description: 了解更多相关信息：从 CObject 派生类时，它的费用是什么？
title: 从 CObject 派生类所带来的开销
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: 3dcedb7c15c4e02c6dc8cbb7ce0f239838d8067c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305229"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>从 CObject 派生类所带来的开销

从 [CObject](../mfc/reference/cobject-class.md) 类派生的开销最小。 派生类仅继承四个虚拟函数和一个 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 对象。

## <a name="see-also"></a>请参阅

[CObject 类：常见问题](../mfc/cobject-class-frequently-asked-questions.md)
