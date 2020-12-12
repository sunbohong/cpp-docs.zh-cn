---
description: 了解详细信息：使用书签
title: 使用书签
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: d0cf27a5f93b3e6b00fa6f8cbb69ae7414f4d819
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319152"
---
# <a name="using-bookmarks"></a>使用书签

在打开行集之前，必须告知提供程序要使用书签。 为此，请将属性设置为，并将属性 `DBPROP_BOOKMARKS` **`true`** 设置为。 提供程序将书签检索为列零，因此， `CBookmark` 如果使用的是静态访问器，则必须使用特殊的宏 BOOKMARK_ENTRY 和类。 `CBookmark` 一个模板类，其中的参数为书签缓冲区的长度（以字节为单位）。 书签所需的缓冲区长度取决于提供程序。 如果使用的是 ODBC OLE DB 提供程序，如下面的示例中所示，缓冲区必须为4字节。

```cpp
class CProducts
{
public:
   CBookmark<4> bookmark;

   BEGIN_COLUMN_MAP(CProducts)
      BOOKMARK_ENTRY(bookmark)
   END_COLUMN_MAP()
};
```

然后，使用以下代码：

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

如果使用 `CDynamicAccessor` ，则会在运行时动态设置缓冲区。 在这种情况下，您可以使用的专用版本， `CBookmark` 不会指定缓冲区长度。 使用函数 `GetBookmark` 从当前记录中检索书签，如以下代码示例所示：

```cpp
CTable<CDynamicAccessor> product;
CBookmark<> bookmark;
CDBPropSet propset(DBPROPSET_ROWSET);
CSession session;

propset.AddProperty(DBPROP_BOOKMARKS, true);
product.Open(session, "Products", &propset);
product.MoveNext();
product.GetBookmark(&bookmark);
```

有关在提供程序中支持书签的信息，请参阅 [提供程序支持书签](../../data/oledb/provider-support-for-bookmarks.md)。

## <a name="see-also"></a>请参阅

[使用访问器](../../data/oledb/using-accessors.md)
