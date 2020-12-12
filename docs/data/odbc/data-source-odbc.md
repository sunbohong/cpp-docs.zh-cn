---
description: 了解详细信息： ODBC) 的数据源 (
title: 数据源 (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
ms.openlocfilehash: 655ba48414a733c6f2704d51c0e2bf1d4edf3ff4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255673"
---
# <a name="data-source-odbc"></a>数据源 (ODBC)

本主题适用于 MFC ODBC 类。

在数据库术语中，数据源是一组特定的数据、访问该数据所需的信息和数据源的位置，可以使用数据源名称进行描述。 若要使用类 [CDatabase](../../mfc/reference/cdatabase-class.md)，数据源必须是通过开放式数据库连接性 (ODBC) 管理员配置的数据源。 数据源的示例包括 Microsoft SQL Server 跨网络运行的远程数据库或本地目录中的 Microsoft Access 文件。 在应用程序中，可以访问具有 ODBC 驱动程序的任何数据源。

你可以在应用程序中一次激活一个或多个数据源，每个数据源都由一个 `CDatabase` 对象表示。 还可以同时连接到任何数据源。 可以连接到远程和本地数据源，具体取决于已安装的驱动程序和 ODBC 驱动程序的功能。 有关数据源和 ODBC 管理器的详细信息，请参阅 [odbc](../../data/odbc/odbc-basics.md) 和 [odbc 管理员](../../data/odbc/odbc-administrator.md)。

以下主题详细介绍了数据源：

- [数据源：管理 (ODBC) 的连接 ](../../data/odbc/data-source-managing-connections-odbc.md)

- [数据源：确定数据源的架构 (ODBC) ](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>请参阅

[ODBC)  (打开数据库连接 ](../../data/odbc/open-database-connectivity-odbc.md)
