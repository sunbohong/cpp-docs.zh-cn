---
description: 了解详细信息：数据源：以编程方式配置 ODBC 数据源
title: 数据源：以编程方式配置 ODBC 数据源
ms.date: 11/04/2016
f1_keywords:
- SQLConfigDataSource
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
ms.openlocfilehash: 4d3cab3de1a3b65bd8df9aee2b91bbaf243926d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155717"
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>数据源：以编程方式配置 ODBC 数据源

本主题说明如何以编程方式 (ODBC) 数据源名称配置开放式数据库连接。 这使你可以灵活地访问数据，而无需强制用户显式使用 ODBC 管理器或其他程序来指定数据源的名称。

通常，如果关联的数据库管理系统 (DBMS) 支持此操作，则用户可以运行 ODBC 管理器来创建数据源。

通过 ODBC 管理器创建 Microsoft Access ODBC 数据源时，有两种选择：可以选择现有的 .mdb 文件，也可以创建新的 .mdb 文件。 不能通过编程方式从 MFC ODBC 应用程序创建 .mdb 文件。 因此，如果您的应用程序需要将数据放入 Microsoft Access 数据源 ( .mdb 文件) ，您很可能希望拥有一个空的 .mdb 文件，您可以在需要时使用或复制它。

但是，很多 Dbms 允许以编程方式创建数据源。 某些数据源保留数据库的目录规范。 也就是说，目录是数据源，数据源中的每个表都存储在一个单独的文件中 (对于 dBASE，每个表都是一个 .dbf 文件) 。 其他 ODBC 数据库的驱动程序（如 Microsoft Access 和 SQL Server）需要满足某些特定条件，然后才能建立数据源。 例如，在使用 SQL Server ODBC 驱动程序时，您需要建立一个 SQL Server 计算机。

## <a name="sqlconfigdatasource-example"></a><a name="_core_sqlconfigdatasource_example"></a> SQLConfigDataSource 示例

下面的示例使用 `::SQLConfigDataSource` ODBC API 函数创建新的名为 New Excel 数据源的 excel 数据源：

```
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",
                   "DSN=New Excel Data Source\0"
                   "Description=New Excel Data Source\0"
                   "FileType=Excel\0"
                   "DataDirectory=C:\\EXCELDIR\0"
                   "MaxScanRows=20\0");
```

请注意，数据源实际上是 (C:\EXCELDIR) 的目录;此目录必须存在。 Excel 驱动程序使用目录作为其数据源和文件，因为单个表 (每个 .xls 文件) 一个表。

有关创建表的详细信息，请参阅 [数据源：以编程方式在 ODBC 数据源中创建表](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md)。

以下信息讨论了需要传递到 `::SQLConfigDataSource` ODBC API 函数的参数。 若要使用 `::SQLConfigDataSource` ，必须包含 odbcinst.ini 头文件并使用 odbcinst.ini 导入库。 此外，Odbccp32.dll 在运行时的路径中必须是 (或 Odbcinst.dll) 16 位。

您可以使用 ODBC 管理器或类似的实用程序创建 ODBC 数据源名称。 但是，有时最好直接从应用程序创建数据源名称以获取访问权限，而无需用户运行单独的实用程序。

ODBC 管理器 (通常安装在 "控制面板" 中) 通过将项放置在 Windows 注册表 (中，或将条目放入 Odbc.ini 文件) 来创建新的数据源。 ODBC 驱动程序管理器会查询此文件以获取有关数据源的所需信息。 必须知道需要在注册表中放置哪些信息，因为需要为其提供对的调用 `::SQLConfigDataSource` 。

尽管此信息可以在不使用的情况下直接写入注册表 `::SQLConfigDataSource` ，但执行此操作的任何应用程序都依赖于驱动程序管理器用来维护其数据的当前技术。 如果更高版本的 ODBC 驱动程序管理器以不同的方式实现记录，则使用此方法的任何应用程序都将中断。 通常建议使用 API 函数（如果提供）。 例如，如果使用函数，则可以将代码从16位移植到32位 `::SQLConfigDataSource` ，因为函数会正确写入 Odbc.ini 文件或注册表。

## <a name="sqlconfigdatasource-parameters"></a><a name="_core_sqlconfigdatasource_parameters"></a> SQLConfigDataSource 参数

下面说明了函数的参数 `::SQLConfigDataSource` 。 大多数信息是从 ODBC API *程序员参考* 中获取的，Visual C++ 版本1.5 及更高版本提供。

### <a name="function-prototype"></a><a name="_core_function_prototype"></a> 函数原型

```
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);
```

### <a name="remarks"></a>备注

#### <a name="parameters-and-usage"></a><a name="_core_parameters_and_usage"></a> 参数和用法

*hwndParent*<br/>
指定为 ODBC 驱动程序管理器或特定 ODBC 驱动程序所创建的任何对话框的所有者的窗口，用于从用户那里获取有关新数据源的附加信息。 如果 *lpszAttributes* 参数没有提供足够的信息，则会出现一个对话框。 *HwndParent* 参数可以为 NULL。

*lpszDriver*<br/>
驱动程序说明。 这是向用户显示的名称，而不是 DLL)  (物理驱动程序名称。

*lpszAttributes*<br/>
"Keyname = value" 形式的特性列表。 这些字符串通过空终止符分隔，列表末尾有两个连续的 null 终止符。 这些属性主要是默认的特定于驱动程序的条目，它们进入到新数据源的注册表中。 此函数的 ODBC API 参考中未提到的一个重要的关键是 "DSN" ( "数据源名称" ) ，它指定新数据源的名称。 其余条目特定于新数据源的驱动程序。 通常不需要提供所有条目，因为驱动程序可以提示用户提供新值的对话框。  (将 *HwndParent* 设置为 NULL 以引发此问题。 ) 你可能需要显式提供默认值，以便不会提示用户。

#### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>使用 ODBC 管理器为 lpszDriver 参数确定驱动程序的说明

1. 运行 ODBC 管理器。

1. 单击“添加”。

这将提供已安装驱动程序及其说明的列表。 使用此描述作为 *lpszDriver* 参数。 请注意，您可以使用整个说明，如 "Excel 文件 ( * .xls) "，其中包括文件扩展名和括号（如果它们存在于说明中）。

作为替代方法，你可以检查注册表 (或16位 Odbcinst.ini 的文件) ，其中包含注册表项 "ODBC 驱动程序" (中的所有驱动程序项和说明的列表，或者 Odbcinst.ini) 的 "ODBC 驱动程序" 部分。

查找 *lpszAttributes* 参数的名和值的一种方法是，检查已配置的数据源的 Odbc.ini 文件， (可能是由 ODBC 管理员) 配置的数据源。

#### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>查找 lpszAttributes 参数的名和值

1. 运行 Windows 注册表编辑器 (或者，对于16位，打开 Odbc.ini 文件) 。

1. 使用以下项之一查找 ODBC 数据源信息：

   - 对于32位，请在左窗格中找到 **\Odbc 数据源** 的密钥HKEY_CURRENT_USER\Software\ODBC\ODBC.INI。

      右窗格列出如下格式的条目： "pub： REG_SZ： *\<data source name>* "，其中， *\<data source name>* 是已配置为要使用的驱动程序所需的设置的数据源。 选择所需的数据源，例如 SQL Server。 字符串 "pub：" 后面的项依次是要在 *lpszAttributes* 参数中使用的键名和值。

   - 对于16位，查找 Odbc.ini 文件中由 [] 标记的部分 *\<data source name>* 。

      此行后面的行的格式为 "keyname = value"。 它们就是要在 *lpszAttributes* 参数中使用的条目。

你可能还想要查看要使用的特定驱动程序的文档。 你可以在驱动程序的联机帮助中查找有用信息，你可以通过运行 ODBC 管理器来访问该驱动程序。 这些帮助文件通常放置在 Windows NT、Windows 3.1 或 Windows 95 的 WINDOWS\SYSTEM 目录中。

#### <a name="to-obtain-online-help-for-your-odbc-driver"></a>获取 ODBC 驱动程序的联机帮助

1. 运行 ODBC 管理器。

1. 单击“添加”。

1. 选择驱动程序名称。

1. 单击 **“确定”** 。

当 ODBC 管理器显示为该特定驱动程序创建新的数据源的信息时，请单击 " **帮助**"。 这会打开该特定驱动程序的帮助文件，其中通常包含有关使用驱动程序的重要信息。

## <a name="see-also"></a>请参阅

[ODBC) 的数据源 (](../../data/odbc/data-source-odbc.md)
