---
description: 了解有关以下方面的详细信息： TN047：放宽数据库事务需求
title: TN047：放宽数据库事务要求
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: 6f356db75df93466bc392e555246a363e6b52187
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215113"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047：放宽数据库事务要求

本技术说明讨论了 MFC ODBC 数据库类的事务需求，现已过时。 在 MFC 4.2 之前，数据库类需要在 **CommitTrans** 或 **回滚** 操作之后将游标保留在记录集中。 如果 ODBC 驱动程序和 DBMS 不支持此级别的游标保留，则数据库类不会启用事务。

从 MFC 4.2 开始，数据库类放宽了要求游标保存的限制。 如果驱动程序支持，将启用事务。 但是，你现在必须检查 **CommitTrans** 或 **回滚** 操作对打开的记录集的影响。 有关详细信息，请参阅成员函数 [CDatabase：： GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) 和 [CDatabase：： GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) 。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
