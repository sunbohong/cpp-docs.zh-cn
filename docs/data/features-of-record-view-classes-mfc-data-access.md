---
description: '了解详细信息：记录视图类的功能 (MFC 数据访问) '
title: 记录视图类的功能（MFC 数据访问）
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: bf2a0bd1a609fcb29eb945f60ab22c4632addf1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116530"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>记录视图类的功能（MFC 数据访问）

您可以使用类 [CFormView](../mfc/reference/cformview-class.md)执行基于窗体的数据访问编程，但 [CRecordView](../mfc/reference/crecordview-class.md) 通常是派生自的更好的类。 除了其功能外 `CFormView` ， `CRecordView` ：

- 提供窗体控件和关联记录集对象之间的对话框数据交换 (DDX) 。

- 句柄先移动、移到下一步、移动上一条命令，然后移动最后一个命令，以便在关联记录集对象中的记录间导航。

- 当用户移到另一记录时，更新对当前记录所做的更改。

有关导航的详细信息，请参阅 [记录视图：支持在记录视图中导航](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)。

## <a name="see-also"></a>请参阅

[记录视图 (MFC 数据访问) ](../data/record-views-mfc-data-access.md)<br/>
[ODBC 驱动程序列表](../data/odbc/odbc-driver-list.md)
