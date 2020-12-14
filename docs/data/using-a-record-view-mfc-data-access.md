---
description: '了解详细信息：使用记录视图 (MFC 数据访问) '
title: 使用记录视图（MFC 数据访问）
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
ms.openlocfilehash: f79e5df4c967b89b02245fb03a3e4e269894b835
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239657"
---
# <a name="using-a-record-view--mfc-data-access"></a>使用记录视图（MFC 数据访问）

本主题介绍了自定义向导为你编写的记录视图的默认代码的常用方式。 通常，您需要使用 [筛选器](../data/odbc/recordset-filtering-records-odbc.md) 或 [参数](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)约束记录选择，可能会 [对记录进行排序](../data/odbc/recordset-sorting-records-odbc.md) ，自定义 SQL 语句。

使用与 `CRecordView` 使用 [CFormView](../mfc/reference/cformview-class.md)大致相同。 基本的方法是使用记录视图显示或更新单个记录集的记录。 除此之外，你可能还希望使用其他记录集，如 [记录视图：从另一个记录集填充列表框](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)中所述。

## <a name="see-also"></a>请参阅

[记录视图 (MFC 数据访问) ](../data/record-views-mfc-data-access.md)<br/>
[ODBC 驱动程序列表](../data/odbc/odbc-driver-list.md)
