---
description: 了解有关以下内容的详细信息： ODBC 和数据库类
title: ODBC 和数据库类
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 146170ddd97dfc2797fd1f755459f370be638ded
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326765"
---
# <a name="odbc-and-the-database-classes"></a>ODBC 和数据库类

MFC ODBC 数据库类封装了通常在 [CDatabase](../../mfc/reference/cdatabase-class.md) 和 [CRecordset](../../mfc/reference/crecordset-class.md) 类的成员函数中执行的 ODBC API 函数调用。 例如，复杂的 ODBC 调用序列、将返回的记录绑定到存储位置、处理错误条件以及其他操作由数据库类管理。 因此，您可以使用一个相当简单的类接口通过 recordset 对象操作记录。

> [!NOTE]
> ODBC 数据源可通过 MFC ODBC 类（如本主题中所述）或通过 MFC 数据访问对象 (DAO) 类访问。

尽管数据库类封装了 ODBC 功能，但它们并不提供 ODBC API 函数的一对一映射。 数据库类提供了更高级别的抽象，它在 Microsoft Access 和 Microsoft Visual Basic 中找到的数据访问对象之后建模。 有关详细信息，请参阅 [ODBC 和 MFC](../../data/odbc/odbc-and-mfc.md)。

## <a name="see-also"></a>请参阅

[ODBC 基础知识](../../data/odbc/odbc-basics.md)
