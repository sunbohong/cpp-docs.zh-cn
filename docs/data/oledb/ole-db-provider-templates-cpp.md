---
description: '了解有关以下内容的详细信息： OLE DB 提供程序模板 (c + +) '
title: OLE DB 提供程序模板 (C++)
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
ms.openlocfilehash: 8706fcd9467e6d184633917d7c83ac81ad137b9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286912"
---
# <a name="ole-db-provider-templates-c"></a>OLE DB 提供程序模板 (C++)

OLE DB 是 Microsoft 通用数据访问策略的重要组成部分。 OLE DB 设计允许来自任何数据源的高性能数据访问。 不管是否来自数据库，都可通过 OLE DB 查看任何表格数据。 灵活性可提供大量的电量。

如 [OLE DB 使用者和提供](../../data/oledb/ole-db-consumers-and-providers.md)者中所述，OLE DB 使用使用者和提供者的概念。 使用者对数据发出请求;提供程序以表格格式将数据返回给使用者。 从编程的角度来看，此模型最重要的含义是提供程序必须实现使用者可以进行的任何调用。

## <a name="what-is-a-provider"></a>什么是提供程序？

OLE DB 提供程序是一组 COM 对象，这些对象提供来自使用者对象的接口调用，从名为的持久源 (将数据以表格格式传输) 到使用者。

提供程序可以简单或复杂。 提供程序可以通过实现更多接口，支持最小数量的功能或全面的生产质量提供程序。 提供程序可以返回表，允许客户端确定该表的格式，并对该数据执行操作。

每个提供程序都实现了一组标准的 COM 对象来处理来自客户端的请求，而标准意味着任何 OLE DB 使用者都可以从任何提供程序访问数据，而不考虑 c + + 和 Basic) 等语言 (。

每个 COM 对象都包含多个接口，其中一些是必需的，某些则是可选的。 通过实现必需接口，提供程序保证 (称为符合性) 的最低级别功能，任何客户端都应该能够使用。 提供程序可以实现可选接口以提供其他功能。 [OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)对这些接口进行了详细说明。 客户端应始终调用 `QueryInterface` 来确定提供程序是否支持给定的接口。

## <a name="ole-db-specification-level-support"></a>OLE DB 规范级别支持

OLE DB 提供程序模板支持 OLE DB 版本2.7 规范。 使用 OLE DB 提供程序模板，你可以实现级别0兼容的提供程序。 `Provider`例如，示例使用模板来实现一个非 SQL (MS-DOS) 命令服务器，该服务器执行 DOS DIR 命令来查询文件系统。 该 `Provider` 示例返回行集中的目录信息，这是用于返回表格数据的标准 OLE DB 机制。

OLE DB 模板支持的提供程序的最简单类型是只读提供程序，不包含任何命令。 还支持带有命令的提供程序，如书签和读/写功能。 可以通过编写其他代码来实现读取/写入提供程序。 当前版本不支持动态行集和事务，但你可以根据需要添加它们。

## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>何时需要创建 OLE DB 提供程序？

并非始终需要创建自己的提供程序;Microsoft 在 Visual C++ 的 " **数据链接属性** " 对话框中提供了多个预打包的标准提供程序。 创建 OLE DB 提供程序的主要原因是利用通用数据访问策略。 这样做的一些优点如下：

- 通过任何语言（例如 c + +、Basic 和 Visual Basic Scripting Edition）来访问数据。 它允许组织中的不同程序员以相同的方式访问相同的数据，而不管他们使用何种语言。

- 将数据打开到其他数据源，例如 SQL Server、Excel 和 Access。 如果要在不同的格式之间传输数据，这会很有用。

- 参与跨数据源 (异类) 操作。 这可能是数据仓库的一种有效方式。 通过使用 OLE DB 提供程序，你可以将数据保留为其本机格式，并且仍能够通过简单的操作进行访问。

- 向数据添加其他功能，如查询处理。

- 通过控制数据的操作方式，提高访问数据的性能。

- 提高可靠性。 如果你具有只有一个程序员可以访问的专有数据格式，则你有风险。 使用 OLE DB 提供程序，你可以将该专用格式公开给所有程序员。

## <a name="read-only-and-updatable-providers"></a>Read-Only 和可更新的提供程序

提供程序的复杂性和功能可能会有很大差异。 将提供程序分类为只读提供程序和可更新的提供程序很有用：

- Visual C++ 6.0 仅支持只读提供程序。 [创建 OLE DB 提供程序](../../data/oledb/creating-an-ole-db-provider.md) 讨论了如何创建只读提供程序。
- Visual C++ 支持可更新的提供程序，该提供程序可更新 (写入) 数据存储区。 有关可更新的提供程序的信息，请参阅 [创建可更新的提供程序](../../data/oledb/creating-an-updatable-provider.md); [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) 示例是可更新的提供程序的示例。

有关详细信息，请参阅：

- [OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)

- [创建 OLE DB 提供程序](../../data/oledb/creating-an-ole-db-provider.md)

- [OLE DB 编程](../../data/oledb/ole-db-programming.md)

## <a name="see-also"></a>请参阅

[数据访问](../data-access-in-cpp.md)<br/>
[OLE DB SDK 文档](/previous-versions/windows/desktop/ms722784(v=vs.85))<br/>
[OLE DB 程序员参考](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)<br/>
