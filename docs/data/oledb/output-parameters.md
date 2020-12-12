---
description: 了解详细信息：输出参数
title: 输出参数
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
ms.openlocfilehash: c52877483d40d7de1a8313eb806769ce92af7337
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316929"
---
# <a name="output-parameters"></a>输出参数

调用存储过程类似于运行 SQL 命令。 主要区别在于，存储过程使用输出参数 (或 "outparameters" ) 并返回值。

在下面的存储过程中，第一个 "？" 是 (phone) 的返回值，第二个 "？" 是输入参数 (名称) ：

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }"))
```

在参数映射中指定 in 和 out 参数：

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()
```

应用程序必须处理从存储过程返回的输出。 在结果处理期间，不同的 OLE DB 访问接口返回输出参数和返回值的时间不同。 例如，在使用者检索或取消了存储过程返回的结果集之前，用于 SQL Server 的 Microsoft OLE DB 提供程序 (SQLOLEDB) 不会提供输出参数和返回代码。 输出将从服务器的最后一个 TDS 数据包中返回。

## <a name="row-count"></a>行计数

如果使用 OLE DB 使用者模板执行具有 outparameters 的存储过程，则在关闭行集之前，不会设置行计数。

例如，假设有一个包含行集和 outparameter 的存储过程：

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```

`@_rowcount`Outparameter 报告从测试表中返回的行数。 但是，此存储过程将行数限制为50。 例如，如果测试中有100行，则行计数将是 50 (因为此代码仅检索) 的最前面的50行。 如果表中只有30行，则行计数将为30。 在 `Close` 提取 outparameter 值之前，请务必调用或 `CloseAll` 来填充它。

## <a name="see-also"></a>请参阅

[使用存储过程](../../data/oledb/using-stored-procedures.md)
