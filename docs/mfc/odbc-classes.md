---
description: 了解更多： ODBC 类
title: ODBC 类
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
ms.openlocfilehash: ac03543a6dfd9cf85320f9ff051730c102f2e0bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318684"
---
# <a name="odbc-classes"></a>ODBC 类

这些类与其他应用程序框架类结合使用，使你可以轻松访问各种数据库， (ODBC) 驱动程序可以使用这些数据库连接。

使用 ODBC 数据库的程序将至少具有一个 `CDatabase` 对象和一个 `CRecordset` 对象。

[CDatabase](reference/cdatabase-class.md)<br/>
封装与数据源的连接，通过该连接可以对数据源执行操作。

[CRecordset](reference/crecordset-class.md)<br/>
封装从数据源中选择的一组记录。 记录集允许从记录滚动到记录，更新记录 (添加、编辑和删除记录) ，使用筛选器限定选定内容，排序所选内容，并使用在运行时获取或计算的信息参数化所选内容。

[CRecordView](reference/crecordview-class.md)<br/>
提供直接连接到 recordset 对象的窗体视图。 对话框数据交换 (DDX) 机制在记录视图的记录视图和控件之间交换数据。 与所有窗体视图一样，记录视图都基于对话框模板资源。 记录视图还支持从记录移到记录集中的记录，更新记录，并在记录视图关闭时关闭关联的记录集。

[CDBException](reference/cdbexception-class.md)<br/>
数据访问处理失败导致的异常。 此类与类库的异常处理机制中的其他异常类的作用相同。

[CFieldExchange](reference/cfieldexchange-class.md)<br/>
提供上下文信息以支持记录字段交换 (RFX) ，后者在记录集对象的字段数据成员和参数数据成员与数据源的相应表列之间交换数据。 类似于类 [CDataExchange](reference/cdataexchange-class.md)，用于对话框数据交换 (DDX) 。

## <a name="related-classes"></a>相关类

[CLongBinary](reference/clongbinary-class.md)<br/>
封装 (BLOB) （如位图）的二进制大型对象的存储句柄。 `CLongBinary` 对象用于管理存储在数据库表中的大型数据对象。

[CDBVariant](reference/cdbvariant-class.md)<br/>
允许您存储一个值，而无需担心值的数据类型。 `CDBVariant` 跟踪存储在联合中的当前值的数据类型。

## <a name="see-also"></a>请参阅

[类概述](class-library-overview.md)
