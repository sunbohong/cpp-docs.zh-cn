---
title: 检索 BLOB
ms.date: 10/24/2018
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
ms.openlocfilehash: 352841595e8b197407ccb52a22c8b0502d314c98
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509511"
---
# <a name="retrieving-a-blob"></a>检索 BLOB

可以通过多种方式检索 (BLOB) 的二进制大型对象。 可以使用 `DBTYPE_BYTES` 以字节序列的形式检索 BLOB，也可以使用等接口 `ISequentialStream` 。 有关详细信息，请参阅**OLE DB 程序员参考**中的[Blob 和 OLE 对象](/previous-versions/windows/desktop/ms711511(v=vs.85))。

下面的代码演示如何使用检索 BLOB `ISequentialStream` 。 宏 [BLOB_ENTRY](./macros-and-global-functions-for-ole-db-consumer-templates.md#blob_entry) 允许您指定接口和用于接口的标志。 打开表后，代码将重复调用 `Read` `ISequentialStream` 以从 BLOB 读取字节。 在 `Release` 调用 `MoveNext` 获取下一条记录之前，代码将调用以释放接口指针。

```cpp
class CCategories
{
public:
   ISequentialStream* pPicture;

BEGIN_COLUMN_MAP(CCategories)
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)
END_COLUMN_MAP()
};
```

然后，使用以下代码：

```cpp
CTable<CAccessor<CCategories>> categories;
ULONG cb;
BYTE myBuffer[65536];

categories.Open(session, "Categories");

while (categories.MoveNext() == S_OK)
{
   do
   {
      categories.pPicture->Read(myBuffer, 65536, &cb);
      // Do something with the buffer
   } while (cb > 0);
   categories.pPicture->Release();
}
```

有关处理 BLOB 数据的宏的详细信息，请参阅[OLE DB 使用者模板的宏和全局函数中的](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)**列映射宏**。

## <a name="see-also"></a>请参阅

[使用访问器](../../data/oledb/using-accessors.md)<br/>
[OLE DB 使用者模板的宏和全局函数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
