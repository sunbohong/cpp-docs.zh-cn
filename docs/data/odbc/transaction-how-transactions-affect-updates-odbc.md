---
description: '了解有关以下内容的详细信息：事务：事务如何影响更新 (ODBC) '
title: 事务：事务如何影响更新 (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 56435d477ab11fe057ec20610a35e75d84cf7340
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333898"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>事务：事务如何影响更新 (ODBC)

对 [数据源](../../data/odbc/data-source-odbc.md) 的更新是通过使用编辑缓冲区来管理的， (在事务之外使用的同一方法) 。 记录集的字段数据成员统称为包含当前记录的编辑缓冲区，记录集在或期间临时备份 `AddNew` `Edit` 。 在操作过程中 `Delete` ，不会在事务中备份当前记录。 有关编辑缓冲区和更新如何存储当前记录的详细信息，请参阅 [记录集：记录集如何更新记录 (ODBC) ](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)。

> [!NOTE]
> 如果已实现批量行提取，则不能调用 `AddNew` 、 `Edit` 或 `Delete` 。 您必须编写自己的函数来对数据源执行更新。 有关批量行提取的详细信息，请参阅 [记录集：批量提取记录 (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)。

在事务期间 `AddNew` ， `Edit` `Delete` 可以提交或回滚事务、、和操作。 和的影响 `CommitTrans` `Rollback` 可能会导致当前记录不还原到编辑缓冲区。 若要确保正确还原当前记录，必须了解的 `CommitTrans` 和 `Rollback` 成员函数如何 `CDatabase` 处理的更新函数 `CRecordset` 。

## <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a> CommitTrans 如何影响更新

下表说明了 `CommitTrans` 对事务的影响。

### <a name="how-committrans-affects-updates"></a>CommitTrans 如何影响更新

|操作|数据源的状态|
|---------------|---------------------------|
|`AddNew` 和 `Update` ，然后 `CommitTrans`|新记录被添加到数据源。|
|`AddNew` (没有 `Update`) ，然后 `CommitTrans`|新记录丢失。 未将记录添加到数据源。|
|`Edit` 和 `Update` ，然后 `CommitTrans`|已提交到数据源的编辑。|
|`Edit` (没有 `Update`) ，然后 `CommitTrans`|对记录的编辑将丢失。 记录在数据源上保持不变。|
|`Delete` 接着 `CommitTrans`|从数据源中删除的记录。|

## <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a> Rollback 如何影响事务

下表说明了 `Rollback` 对事务的影响。

### <a name="how-rollback-affects-transactions"></a>Rollback 如何影响事务

|操作|当前记录的状态|还必须|数据源的状态|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` 和 `Update` ，然后 `Rollback`|暂时存储当前记录的内容，为新记录腾出空间。 新记录将进入编辑缓冲区。 `Update`调用后，将当前记录还原到编辑缓冲区。||与所创建的数据源的补充 `Update` 相反。|
|`AddNew` (没有 `Update`) ，则 `Rollback`|暂时存储当前记录的内容，为新记录腾出空间。 编辑缓冲区包含新记录。|`AddNew`再次调用以将编辑缓冲区还原为空的新记录。 或调用 `Move` (0) 将旧值还原到编辑缓冲区。|由于 `Update` 未调用，因此没有对数据源所做的更改。|
|`Edit` 和 `Update` ，然后 `Rollback`|暂时存储当前记录的未编辑版本。 编辑缓冲区的内容。 `Update`调用后，仍会临时存储记录的未编辑版本。|*动态集*：向后滚动当前记录，然后返回以将未编辑的记录版本还原到编辑缓冲区。<br /><br /> *Snapshot*：调用 `Requery` 以刷新数据源中的记录集。|对所做的数据源所做的更改 `Update` 将反转。|
|`Edit` (没有 `Update`) ，则 `Rollback`|暂时存储当前记录的未编辑版本。 编辑缓冲区的内容。|再次调用以将未 `Edit` 编辑的记录版本还原到编辑缓冲区。|由于 `Update` 未调用，因此没有对数据源所做的更改。|
|`Delete` 接着 `Rollback`|删除当前记录的内容。|调用 `Requery` 以从数据源还原当前记录的内容。|删除数据源中的数据。|

## <a name="see-also"></a>请参阅

[事务 (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[事务：在记录集中执行事务 (ODBC) ](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[CDatabase 类](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset 类](../../mfc/reference/crecordset-class.md)
