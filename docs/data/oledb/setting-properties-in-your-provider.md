---
title: 在提供程序中设置属性
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
ms.openlocfilehash: 3717282d284990b1b8038f6954ee971938cf7921
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509486"
---
# <a name="setting-properties-in-your-provider"></a>在提供程序中设置属性

查找所需属性的属性组和属性 ID。 有关详细信息，请参阅**OLE DB 程序员参考**中的[OLE DB 属性](/previous-versions/windows/desktop/ms722734(v=vs.85))。

在向导生成的提供程序代码中，找到与属性组相对应的属性映射。 属性组的名称通常对应于对象的名称。 可以在命令或行集中找到命令和行集属性;数据源和初始化属性可以在数据源对象中找到。

在属性映射中，添加一个 [PROPERTY_INFO_ENTRY_EX](./macros-for-ole-db-provider-templates.md#property_info_entry_ex) 宏。 PROPERTY_INFO_ENTRY_EX 使用四个参数：

- 与属性相对应的属性 ID。 从属性名称的前面 ( "DBPROP_" ) 删除前七个字符。 例如，如果要添加 `DBPROP_MAXROWS` ，请将 `MAXROWS` 作为第一个元素传递。 如果这是自定义属性，请将完整的 GUID 名称传递 (例如 `DBMYPROP_MYPROPERTY`) 。

- **OLE DB 程序员参考**) 的[OLE DB 属性](/previous-versions/windows/desktop/ms722734(v=vs.85))中 (属性的变量类型。 输入 VT_ 类型 (例如，VT_BOOL 或与数据类型相对应的 VT_I2) 。

- 指示属性是否可读和可写以及它所属的组的标志。 例如，下面的代码指示属于行集组的读/写属性：

    ```cpp
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE
    ```

- 属性的基值。 `VARIANT_FALSE`例如，对于整数类型，这可能是布尔类型或零。 除非更改，否则属性具有此值。

    > [!NOTE]
    > 某些属性已连接或链接到其他属性，例如书签或更新。 当使用者将一个属性设置为 true 时，还可以设置另一个属性。 OLE DB 提供程序模板通过方法 [CUtlProps：： OnPropertyChanged](./cutlprops-class.md#onpropertychanged)支持这种情况。

## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB 提供程序忽略的属性

Microsoft OLE DB 提供程序忽略以下 OLE DB 属性：

- `DBPROP_MAXROWS` 仅适用于只读提供程序 (即，其中 `DBPROP_IRowsetChange` 和 `DBPROP_IRowsetUpdate` 是) 的， **`false`** 否则不支持此属性。

- `DBPROP_MAXPENDINGROWS` 被忽略;提供程序指定其自己的限制。

- `DBPROP_MAXOPENROWS` 被忽略;提供程序指定其自己的限制。

- `DBPROP_CANHOLDROWS` 被忽略;提供程序指定其自己的限制。

## <a name="see-also"></a>请参阅

[使用 OLE DB 提供程序模板](../../data/oledb/working-with-ole-db-provider-templates.md)
