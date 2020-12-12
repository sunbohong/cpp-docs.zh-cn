---
description: 了解详细信息：修改 RCustomRowset 的继承
title: 修改 RCustomRowset 的继承
ms.date: 10/26/2018
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
ms.openlocfilehash: c54533122083c526ad12ac6514efa3ad9ba47cf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287003"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>修改 RCustomRowset 的继承

若要将 `IRowsetLocate` 接口添加到简单的只读提供程序示例，请修改的继承 `CCustomRowset` 。 最初， `CCustomRowset` 从继承 `CRowsetImpl` 。 需要将其修改为从继承 `CRowsetBaseImpl` 。

为此，请 `CCustomRowsetImpl` 在 *自定义* RS：中创建新类：

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

现在，按如下所示编辑 *自定义* RS 中的 COM 接口映射：

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

此代码将创建一个 COM 接口映射，该映射告诉 `CMyRowsetImpl` 为 `QueryInterface` `IRowset` 和 `IRowsetLocate` 接口调用。 为了获取其他行集类的所有实现，地图会将 `CMyRowsetImpl` 该类链接回 `CRowsetBaseImpl` 由 OLE DB 模板定义的类; 该地图使用 COM_INTERFACE_ENTRY_CHAIN 宏，该宏告诉 OLE DB 模板在中扫描 COM 映射以 `CRowsetBaseImpl` 响应 `QueryInterface` 调用。

最后， `CCustomRowset` `CMyRowsetBaseImpl` 通过修改 `CCustomRowset` 将继承到， `CMyRowsetImpl` 如下所示：

```cpp
class CCustomRowset : public CMyRowsetImpl<CCustomRowset, CCustomWindowsFile, CCustomCommand>
```

`CCustomRowset` 现在可以使用 `IRowsetLocate` 接口，同时利用行集类实现的其余部分。

完成此操作后，可以 [动态确定返回给使用者的列](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)。

## <a name="see-also"></a>请参阅

[增强简单的 Read-Only 提供程序](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
