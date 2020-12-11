---
description: 了解详细信息：使用现有 ADO 记录集
title: 使用现有 ADO 记录集
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 4b5c3b5f621f3cbdba6f2d42fd95436495a5661e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160943"
---
# <a name="using-an-existing-ado-recordset"></a>使用现有 ADO 记录集

若要将 OLE DB 使用者模板和活动数据对象组合 (ADO) ，请使用 ADO 打开与 OLE DB 使用者模板) 中的行集相对应的记录 (集。 如果有记录集，请执行以下操作来连接到 OLE DB 行集：

1. 调用 `QueryInterface` `IRowset` 和 `IAccessor` 指针。

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *lpUnk* 指向 `IUnknown` ADO 记录集的对象。

1. 将访问器和行集附加到相应的 OLE DB 使用者模板类中。

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>请参阅

[使用访问器](../../data/oledb/using-accessors.md)
