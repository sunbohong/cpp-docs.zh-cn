---
description: 了解详细信息：使用存储过程
title: 使用存储过程
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
ms.openlocfilehash: 6bd7dbd3980eb4bfe0fbca71d86af080128d3309
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319100"
---
# <a name="using-stored-procedures"></a>使用存储过程

存储过程是存储在数据库中的可执行对象。 调用存储过程类似于调用 SQL 命令。 使用数据源中的存储过程 (，而不是在客户端应用程序中执行或准备语句) 可以提供多种优势，包括更高的性能、减少网络开销，并改善一致性和准确性。

存储过程可以有任意数量的 (包括零) 输入参数或输出参数，并可以传递返回值。 您可以将参数值硬编码为特定的数据值，或者使用参数标记 (问号 "？") 。

> [!NOTE]
> 使用 Visual C++ 创建的 CLR SQL Server 用编译器选项编译的存储过程 `/clr:safe` 。

SQL Server (SQLOLEDB) 的 OLE DB 提供程序支持存储过程用于返回数据的下列机制：

- 过程中的每个 **SELECT** 语句都会生成一个结果集。

- 过程可以通过输出参数返回数据。

- 过程可以具有整数返回代码。

> [!NOTE]
> 不能将存储过程用于 Jet 的 OLE DB 提供程序，因为该提供程序不支持存储过程;仅允许在查询字符串中使用常量。

## <a name="see-also"></a>请参阅

[使用 OLE DB 使用者模板](../../data/oledb/working-with-ole-db-consumer-templates.md)
