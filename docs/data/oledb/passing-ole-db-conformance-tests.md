---
description: 了解详细信息：传递 OLE DB 的一致性测试
title: 通过 OLE DB 一致性测试
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
ms.openlocfilehash: d2a5b788b3a118293800b02a9383fbde9845cfa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286718"
---
# <a name="passing-ole-db-conformance-tests"></a>通过 OLE DB 一致性测试

为了使提供程序更一致，数据访问 SDK 提供了一组 OLE DB 的一致性测试。 测试会检查提供程序的各个方面，并为你提供提供程序正常运行所需的合理保障。 可以在 Microsoft 数据访问 SDK 中找到 OLE DB 一致性测试。 本部分重点介绍传递一致性测试应执行的操作。 有关运行 OLE DB 一致性测试的信息，请参阅 SDK。

## <a name="running-the-conformance-tests"></a>运行一致性测试

在 Visual C++ 6.0 中，OLE DB 提供程序模板添加了一些挂钩函数，使你可以检查值和属性。 其中的大多数函数是为了响应一致性测试而添加的。

> [!NOTE]
> 你需要为提供程序添加几个验证函数以传递 OLE DB 的一致性测试。

此提供程序需要两个验证例程。 第一个例程 `CRowsetImpl::ValidateCommandID` 是行集类的一部分。 它在按提供程序模板创建行集的过程中被调用。 该示例使用此例程告知使用者不支持索引。 第一次调用是 `CRowsetImpl::ValidateCommandID` (注意，提供程序使用在 `_RowsetBaseClass` 接口映射中添加的 Typedef 作为 `CCustomRowset` [提供程序支持的书签](../../data/oledb/provider-support-for-bookmarks.md)，因此您无需在) 中键入该长行模板参数。 接下来，如果 index 参数不为 NULL，则返回 DB_E_NOINDEX (这表示使用者想要使用我们) 的索引。 有关命令 Id 的详细信息，请参阅 OLE DB 规范，并查找 `IOpenRowset::OpenRowset` 。

以下代码是 `ValidateCommandID` 验证例程：

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H
// Class: CCustomRowset

HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)
{
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);
   if (hr != S_OK)
      return hr;

   if (pIndexID != NULL)
      return DB_E_NOINDEX;    // Doesn't support indexes

   return S_OK;
}
```

`OnPropertyChanged`每当用户更改 DBPROPSET_ROWSET 组上的属性时，提供程序模板都会调用方法。 如果要处理其他组的属性，请将它们添加到相应的对象， (也就是说，DBPROPSET_SESSION 类) 中的检查 `CCustomSession` 。

代码首先检查属性是否已链接到另一个。 如果该属性是链接属性，则会将 DBPROP_BOOKMARKS 属性设置为 `True` 。 OLE DB 规范的附录 C 包含有关属性的信息。 此信息还会告诉您该属性是否已链接到另一个属性。

你可能还需要将例程添加 `IsValidValue` 到你的代码中。 `IsValidValue`尝试设置属性时，模板会调用。 如果在设置属性值时需要其他处理，则应重写此方法。 您可以对每个属性集使用这些方法之一。

## <a name="see-also"></a>请参阅

[高级提供程序技术](../../data/oledb/advanced-provider-techniques.md)
