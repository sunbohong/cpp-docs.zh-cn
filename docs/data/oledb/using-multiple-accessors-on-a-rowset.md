---
title: 在一个行集合上使用多个访问器
ms.date: 10/24/2018
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
ms.openlocfilehash: 48772539b4dda9262a244506a36932d1e752949e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509405"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>在一个行集合上使用多个访问器

有三种基本方案需要使用多个访问器：

- **多个读/写行集。** 在此方案中，您有一个具有主键的表。 您希望能够读取行中的所有列，包括主键。 您还希望能够将数据写入除主键 (之外的所有列，因为不能写入主键列) 。 在这种情况下，你设置了两个访问器：

  - 取值函数0包含所有列。

  - 取值函数1包含除主键之外的所有列。

- **性能。** 在此方案中，一个或多个列的数据量很大，如图形、声音或视频文件。 每次移动到行时，您可能不想检索包含大型数据文件的列，因为这样做会降低应用程序的性能。

  您可以设置单独的访问器，其中第一个访问器包含除包含大型数据的列以外的所有列，并自动从这些列检索数据;第一个访问器是自动访问器。 第二个访问器仅检索包含大型数据的列，但它不会自动检索此列中的数据。 可以使用其他方法根据需要更新或提取大数据。

  - 访问器0是一个自动访问器;它检索除包含大型数据的列之外的所有列。

  - 取值函数1不是自动访问器;它检索包含大型数据的列。

  使用 auto 参数可以指定访问器是否为自动访问器。

- **多个 ISequentialStream 列。** 在此方案中，有多个包含数据的列 `ISequentialStream` 。 但是，每个访问器限制为一个数据流 `ISequentialStream` 。 若要解决此问题，请设置多个访问器，每个访问器都有一个 `ISequentialStream` 指针。

通常使用 [BEGIN_ACCESSOR](./macros-and-global-functions-for-ole-db-consumer-templates.md#begin_accessor) 和 [END_ACCESSOR](./macros-and-global-functions-for-ole-db-consumer-templates.md#end_accessor) 宏创建访问器。 你还可以使用 [db_accessor](../../windows/attributes/db-accessor.md) 特性。  (访问器在 [用户记录](../../data/oledb/user-records.md)中进行了进一步说明。 ) 宏或特性指定访问器是自动访问器还是非自动访问器：

- 在自动访问器中，移动、、和等方法， `MoveFirst` `MoveLast` `MoveNext` `MovePrev` 自动为所有指定的列检索数据。 取值函数0应为自动访问器。

- 在非自动访问器中，除非您显式调用了、、或等方法，否则不会发生检索 `Update` `Insert` `Fetch` `Delete` 。 在上述方案中，您可能不希望在每次移动时检索所有列。 可以将一个或多个列置于单独的访问器中，并使其成为非自动访问器，如下所示。

下面的示例使用多个访问器通过多个访问器来读取和写入 SQL Server pubs 数据库的作业表。 此示例是多访问器最常见的用法;请参阅上面的 "多个读/写行集" 方案。

用户记录类如下所示。 它设置了两个访问器：访问器0只包含主键列 (ID) 并且取值函数1包含其他列。

```cpp
class CJobs
{
public:
    enum {
        sizeOfDescription = 51
    };

    short nID;
    char szDescription[ sizeOfDescription ];
    short nMinLvl;
    short nMaxLvl;

    DWORD dwID;
    DWORD dwDescription;
    DWORD dwMinLvl;
    DWORD dwMaxLvl;

BEGIN_ACCESSOR_MAP(CJobs, 2)
    // Accessor 0 is the automatic accessor
    BEGIN_ACCESSOR(0, true)
        COLUMN_ENTRY_STATUS(1, nID, dwID)
    END_ACCESSOR()
    // Accessor 1 is the non-automatic accessor
    BEGIN_ACCESSOR(1, true)
        COLUMN_ENTRY_STATUS(2, szDescription, dwDescription)
        COLUMN_ENTRY_STATUS(3, nMinLvl, dwMinLvl)
        COLUMN_ENTRY_STATUS(4, nMaxLvl, dwMaxLvl)
    END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

主要代码如下所示。 调用 `MoveNext` 会自动使用访问器0从主键列 ID 检索数据。 请注意， `Insert` 接近末尾的方法如何使用访问器1以避免写入主键列。

```cpp
int main(int argc, char* argv[])
{
    // Initialize COM
    ::CoInitialize(NULL);

    // Create instances of the data source and session
    CDataSource source;
    CSession session;
    HRESULT hr = S_OK;

    // Set initialization properties
    CDBPropSet dbinit(DBPROPSET_DBINIT);
    dbinit.AddProperty(DBPROP_AUTH_USERID, OLESTR("my_user_id"));
    dbinit.AddProperty(DBPROP_INIT_CATALOG, OLESTR("pubs"));
    dbinit.AddProperty(DBPROP_INIT_DATASOURCE, OLESTR("(local)"));

    hr = source.Open("SQLOLEDB.1", &dbinit);
    if (hr == S_OK)
    {
        hr = session.Open(source);
        if (hr == S_OK)
        {
            // Ready to fetch/access data
            CTable<CAccessor<CJobs>> jobs;

            // Set properties for making the rowset a read/write cursor
            CDBPropSet dbRowset(DBPROPSET_ROWSET);
            dbRowset.AddProperty(DBPROP_CANFETCHBACKWARDS, true);
            dbRowset.AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
            dbRowset.AddProperty(DBPROP_IRowsetChange, true);
            dbRowset.AddProperty(DBPROP_UPDATABILITY,
                DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE |
                DBPROPVAL_UP_DELETE);

            hr = jobs.Open(session, "jobs", &dbRowset);
            if (hr == S_OK)
            {
                // Calling MoveNext automatically retrieves ID
                // (using accessor 0)
                while(jobs.MoveNext() == S_OK)
                   printf_s("Description = %s\n", jobs.szDescription);

                hr = jobs.MoveFirst();
                if (hr == S_OK)
                {
                    jobs.nID = 25;
                    strcpy_s(&jobs.szDescription[0],
                             jobs.sizeOfDescription,
                             "Developer");
                    jobs.nMinLvl = 10;
                    jobs.nMaxLvl = 20;

                    jobs.dwDescription = DBSTATUS_S_OK;
                    jobs.dwID = DBSTATUS_S_OK;
                    jobs.dwMaxLvl = DBSTATUS_S_OK;
                    jobs.dwMinLvl = DBSTATUS_S_OK;

                    // Insert method uses accessor 1
                    // (to avoid writing to the primary key column)
                    hr = jobs.Insert(1);
                }
                jobs.Close();
            }
            session.Close();
        }
        source.Close();
    }

    // Uninitialize COM
    ::CoUninitialize();
    return 0;
}
```

## <a name="see-also"></a>请参阅

[使用访问器](../../data/oledb/using-accessors.md)<br/>
[用户记录](../../data/oledb/user-records.md)
