---
title: OLE DB 提供程序模板体系结构
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
ms.openlocfilehash: 89e07f95853c3611b7cceaef3f247c220c630add
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509546"
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB 提供程序模板体系结构

## <a name="data-sources-and-sessions"></a>数据源和会话

OLE DB 提供程序体系结构包含一个数据源对象和一个或多个会话。 数据源对象是每个提供程序必须实例化的初始对象。 当使用者应用程序需要数据时，它将创建数据源对象以启动该提供程序。 数据源对象使用接口) 创建会话对象 (使用 `IDBCreateSession` 者连接到数据源对象。 ODBC 程序员可以将数据源对象视为等效于和与等效的 `HENV` 会话对象 `HDBC` 。

![提供程序体系结构](../../data/oledb/media/vc4twb1.gif "提供程序体系结构")

OLE DB 模板与 **OLE DB 提供程序向导**创建的源文件一起实现数据源对象。 会话是对应于 OLE DB 的对象 `TSession` 。

## <a name="mandatory-and-optional-interfaces"></a>强制和可选接口

OLE DB 提供程序模板为所有必需的接口提供了预打包的实现。 必需的和可选的接口由多个对象类型的 OLE DB 定义：

- [数据源](../../data/oledb/data-source-object-interfaces.md)

- [会话](../../data/oledb/session-object-interfaces.md)

- [行集](../../data/oledb/rowset-object-interfaces.md)

- [命令](../../data/oledb/command-object-interfaces.md)

- [事务](../../data/oledb/transaction-object-interfaces.md)

OLE DB 提供程序模板不实现行和存储对象。

下表根据 [OLE DB 2.6 SDK 文档](/previous-versions/windows/desktop/ms722784(v=vs.85))列出了上面列出的对象的必需和可选接口。

|组件|接口|评论|
|---------------|---------------|-------------|
|[数据源](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md)) |必需 `IDBCreateSession`<br /><br /> 必需 `IDBInitialize`<br /><br /> 必需 `IDBProperties`<br /><br /> 必需 `IPersist`<br /><br /> 可有可无 `IConnectionPointContainer`<br /><br /> 可有可无 `IDBAsynchStatus`<br /><br /> 可有可无 `IDBDataSourceAdmin`<br /><br /> 可有可无 `IDBInfo`<br /><br /> 可有可无 `IPersistFile`<br /><br /> 可有可无 `ISupportErrorInfo`|从使用者到提供程序的连接。 对象用于指定连接的属性，例如用户 ID、密码和数据源名称。 对象还可用于管理数据源 (创建、更新、删除、表等) 。|
|[会话](../../data/oledb/session-object-interfaces.md) ([CSession](./cdataconnection-class.md#op_csession_amp)) |必需 `IGetDataSource`<br /><br /> 必需 `IOpenRowset`<br /><br /> 必需 `ISessionProperties`<br /><br /> 可有可无 `IAlterIndex`<br /><br /> 可有可无 `IAlterTable`<br /><br /> 可有可无 `IBindResource`<br /><br /> 可有可无 `ICreateRow`<br /><br /> 可有可无 `IDBCreateCommand`<br /><br /> 可有可无 `IDBSchemaRowset`<br /><br /> 可有可无 `IIndexDefinition`<br /><br /> 可有可无 `ISupportErrorInfo`<br /><br /> 可有可无 `ITableCreation`<br /><br /> 可有可无 `ITableDefinition`<br /><br /> 可有可无 `ITableDefinitionWithConstraints`<br /><br /> 可有可无 `ITransaction`<br /><br /> 可有可无 `ITransactionJoin`<br /><br /> 可有可无 `ITransactionLocal`<br /><br /> 可有可无 `ITransactionObject`|Session 对象是使用者与提供者之间的单个对话。 它类似于 ODBC `HSTMT` ，因为可以有多个同时处于活动状态的会话。<br /><br /> Session 对象是要获取 OLE DB 功能的主链接。 若要访问命令、事务或行集对象，请完成会话对象。|
|[行集](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md)) |必需 `IAccessor`<br /><br /> 必需 `IColumnsInfo`<br /><br /> 必需 `IConvertType`<br /><br /> 必需 `IRowset`<br /><br /> 必需 `IRowsetInfo`<br /><br /> 可有可无 `IChapteredRowset`<br /><br /> 可有可无 `IColumnsInfo2`<br /><br /> 可有可无 `IColumnsRowset`<br /><br /> 可有可无 `IConnectionPointContainer`<br /><br /> 可有可无 `IDBAsynchStatus`<br /><br /> 可有可无 `IGetRow`<br /><br /> 可有可无 `IRowsetChange`<br /><br /> 可有可无 `IRowsetChapterMember`<br /><br /> 可有可无 `IRowsetCurrentIndex`<br /><br /> 可有可无 `IRowsetFind`<br /><br /> 可有可无 `IRowsetIdentity`<br /><br /> 可有可无 `IRowsetIndex`<br /><br /> 可有可无 `IRowsetLocate`<br /><br /> 可有可无 `IRowsetRefresh`<br /><br /> 可有可无 `IRowsetScroll`<br /><br /> 可有可无 `IRowsetUpdate`<br /><br /> 可有可无 `IRowsetView`<br /><br /> 可有可无 `ISupportErrorInfo`<br /><br /> 可有可无 `IRowsetBookmark`|行集对象是数据源中的数据。 对象用于该数据的绑定和任何基本操作 (更新、提取、移动以及其他对数据的) 。 始终有一个行集对象用于保存和处理数据。|
|[命令](../../data/oledb/command-object-interfaces.md) ([CCommand](ccommand-class.md)) |必需 `IAccessor`<br /><br /> 必需 `IColumnsInfo`<br /><br /> 必需 `ICommand`<br /><br /> 必需 `ICommandProperties`<br /><br /> 必需 `ICommandText`<br /><br /> 必需 `IConvertType`<br /><br /> 可有可无 `IColumnsRowset`<br /><br /> 可有可无 `ICommandPersist`<br /><br /> 可有可无 `ICommandPrepare`<br /><br /> 可有可无 `ICommandWithParameters`<br /><br /> 可有可无 `ISupportErrorInfo`<br /><br /> 可有可无 `ICommandStream`|命令对象处理对数据的操作（例如查询）。 它可以处理参数化或非参数化语句。<br /><br /> Command 对象还负责处理参数和输出列的绑定。 绑定是一个结构，它包含有关如何检索行集中的列的信息。 它包含序号、数据类型、长度和状态等信息。|
|[Transaction](../../data/oledb/transaction-object-interfaces.md) (可选) |必需 `IConnectionPointContainer`<br /><br /> 必需 `ITransaction`<br /><br /> 可有可无 `ISupportErrorInfo`|事务对象定义数据源的原子工作单元，并确定这些工作单元如何相互关联。 OLE DB 提供程序模板不直接支持此对象 (即，你) 创建自己的对象。|

有关详细信息，请参阅下列主题：

- [属性映射](../../data/oledb/property-maps.md)

- [用户记录](../../data/oledb/user-record.md)

## <a name="see-also"></a>请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 接口](/previous-versions/windows/desktop/ms709709(v=vs.85))<br/>
