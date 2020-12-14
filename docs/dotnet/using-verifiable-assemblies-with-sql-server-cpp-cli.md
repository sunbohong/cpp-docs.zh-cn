---
description: '了解更多相关信息：结合使用可验证程序集和 SQL Server (c + +/CLI) '
title: 结合使用 SQL Server 和可验证的程序集 (C++/CLI)
ms.date: 10/17/2018
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
ms.openlocfilehash: b155fb0360fb373f5931f51de3af557d06858a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204194"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>结合使用 SQL Server 和可验证的程序集 (C++/CLI)

作为动态链接库打包 (Dll) 的扩展存储过程提供了一种通过 Visual C++ 开发的函数来扩展 SQL Server 功能的方法。 扩展存储过程在 Dll 内实现为函数。 除了函数外，扩展存储过程还可以定义 [用户定义类型](../cpp/classes-and-structs-cpp.md) 和聚合函数 (例如 SUM 或 AVG) 。

当客户端执行扩展存储过程时，SQL Server 搜索与扩展存储过程关联的 DLL 并加载 DLL。 SQL Server 调用请求的扩展存储过程，并在指定的安全上下文中执行它。 然后，扩展存储过程将传递结果集并将参数返回给服务器。

SQL Server 提供 Transact-sql (T-sql) 的扩展，以允许您将可验证的程序集安装到 SQL Server 中。 SQL Server 权限集指定安全上下文，安全级别如下：

- 无限制模式：运行代码的风险由你自己承担;代码不必是可验证类型安全的。

- 安全模式：运行已验证的类型安全代码;用/clr： safe 编译的。

> [!IMPORTANT]
> Visual Studio 2015 已弃用，并且 Visual Studio 2017 不支持 **/clr： pure** 和 **/clr：** 可验证项目的安全创建。 如果需要可验证代码，建议将代码转换为 c #。

若要创建可验证的程序集并将其加载到 SQL Server，请使用 Transact-sql 命令 CREATE ASSEMBLY 和 DROP ASSEMBLY，如下所示：

```sql
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH
  PERMISSION_SET <permissions>
DROP ASSEMBLY <assemblyName>
```

PERMISSION_SET 命令指定安全上下文，并且值不受限制、安全或扩展。

此外，还可以使用 CREATE FUNCTION 命令绑定到类中的方法名称：

```sql
CREATE FUNCTION <FunctionName>(<FunctionParams>)
RETURNS returnType
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]
```

## <a name="example"></a>示例

下面的 SQL 脚本 (例如，名为 "MyScript" ) 将程序集加载到 SQL Server，并使类的方法可用：

```sql
-- Create assembly without external access
drop assembly stockNoEA
go
create assembly stockNoEA
from
'c:\stockNoEA.dll'
with permission_set safe

-- Create function on assembly with no external access
drop function GetQuoteNoEA
go
create function GetQuoteNoEA(@sym nvarchar(10))
returns real
external name stockNoEA:StockQuotes::GetQuote
go

-- To call the function
select dbo.GetQuoteNoEA('MSFT')
go
```

可以在 SQL 查询分析器中或在命令行中通过 sqlcmd.exe 实用程序以交互方式执行 SQL 脚本。 以下命令行连接到 MyServer，使用默认数据库，使用可信连接，输入 MyScript，然后 MyResult.txt 输出。

```cmd
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt
```

## <a name="see-also"></a>请参阅

[类和结构](../cpp/classes-and-structs-cpp.md)
