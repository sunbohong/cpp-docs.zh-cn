---
title: 'db_source (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_source
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
ms.openlocfilehash: f17a4ea183a24f7bf4e88137f4536ca082efdf85
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831380"
---
# <a name="db_source"></a>db_source

创建与数据源的连接。

## <a name="syntax"></a>语法

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>参数

*db_source*<br/>
用于连接到数据源的连接字符串。 有关连接字符串的格式，请参阅 Microsoft 数据访问组件中的 [连接字符串和数据链接](/previous-versions/windows/desktop/ms718376(v=vs.85)) (MDAC) SDK。

name <br/>
 (可选) 如果在类上使用 **db_source** ，则 *name* 是应用了 **db_source** 特性的数据源对象的实例 (参见示例 1) 。 在方法实现中使用 **db_source** 内联时， *name* 是可用于访问数据源的方法)  (本地变量 (参阅示例 2) 。 将此 *名称* 传递到的 *source_name* 参数 `db_command` ，以将数据源与命令相关联。

*hresult*<br/>
 (可选) 标识将接收此数据库命令的 HRESULT 的变量。 如果该变量不存在，属性将自动插入。

## <a name="remarks"></a>注解

**db_source** 创建一个 [CDataSource](../../data/oledb/cdatasource-class.md) 和一个 [CSession](../../data/oledb/csession-class.md) 对象，该对象共同表示与 OLE DB 使用者数据源的连接。

在类上使用 **db_source** 时， `CSession` 对象将成为类的成员。

在方法中使用 **db_source** 时，插入的代码将在方法范围内执行，并将该 `CSession` 对象创建为局部变量。

**db_source** 向类或方法中添加数据源属性。 它与 `db_command` (采用 *db_source* *name* 参数作为其 *source_name* 参数) 一起使用。

当使用者特性提供程序将此特性应用于类时，编译器会将类重命名为 \_ *YourClassName*访问器，其中*YourClassName*是您赋予类的名称，并且编译器还将创建一个名为*YourClassName*的类，该类派生自 \_ *YourClassName*访问器。  将在类视图中看到这两个类。

有关应用程序中使用的此属性的示例，请参阅 [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)。

## <a name="example"></a>示例

此示例对类调用 **db_source** ，以使用 Northwind 数据库创建到数据源的连接 `ds` 。 `ds` 数据源的句柄，可在内部用于 `CMyCommand` 类。

```cpp
// db_source_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[
  db_source(L"my_connection_string", name="ds"),
  db_command(L"select * from Products")
]
class CMyCommand {};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**`class`**、 **`struct`** 、成员、方法、本地|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[OLE DB 使用者属性](ole-db-consumer-attributes.md)
