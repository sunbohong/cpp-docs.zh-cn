---
description: 了解详细信息：连接到数据源
title: 连接数据源
ms.date: 11/04/2016
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
ms.openlocfilehash: 3bc5436a678d39682b89d82dd7f3ab90eb6f5bb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295115"
---
# <a name="connecting-to-a-data-source"></a>连接数据源

ODBC 数据源是一组特定的数据、访问该数据所需的信息和数据源的位置，可以使用数据源名称进行描述。 从程序的角度来看，数据源包括数据、DBMS、网络 (如有任何) 和 ODBC。

若要访问数据源所提供的数据，您的程序必须首先建立与数据源的连接。 所有数据访问都通过该连接进行管理。

数据源连接由类 [CDatabase](../../mfc/reference/cdatabase-class.md)封装。 当 `CDatabase` 对象连接到数据源时，可以执行以下操作：

- 构造 [记录集](../../mfc/reference/crecordset-class.md)，它从表或查询中选择记录。

- 管理 [事务](../../data/odbc/transaction-odbc.md)，对更新进行批处理，以便将所有更新一次提交到数据源 (或整个事务都将回滚，因此，如果数据源支持所需的事务级别，则) 的数据源。

- 直接执行 [SQL](../../data/odbc/sql.md) 语句。

完成数据源连接的处理后，关闭该对象，并将 `CDatabase` 其销毁或重复用于新连接。 有关数据源连接的详细信息，请参阅 [Data source (ODBC) ](../../data/odbc/data-source-odbc.md)。

## <a name="see-also"></a>请参阅

[ODBC 和 MFC](../../data/odbc/odbc-and-mfc.md)
