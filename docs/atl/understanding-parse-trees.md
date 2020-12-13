---
description: 了解详细信息：了解分析树
title: ATL 注册器和分析树
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: cae5256bf932478135db747f80816378e61429a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138237"
---
# <a name="understanding-parse-trees"></a>了解分析树

你可以在注册器脚本中定义一个或多个分析树，其中每个分析树具有以下形式：

> \<root key>{\<registry expression>}+

其中：

> \<root key> ：： = HKEY_CLASSES_ROOT \| HKEY_CURRENT_USER \|\
> &emsp;HKEY_LOCAL_MACHINE \| HKEY_USERS \|\
> &emsp;HKEY_PERFORMANCE_DATA \| HKEY_DYN_DATA \|\
> &emsp;HKEY_CURRENT_CONFIG \| HKCR \| HKCU \|\
> &emsp;HKLM \| HKU 开头 \| HKPD \| HKDD \| HKCC

> \<registry expression>::= \<Add Key> \|\<Delete Key>

> \<Add Key>：： = \[ **ForceRemove** \| **NoRemove** \| **val**] \<Key Name> [ \<Key Value> ] [{ \<Add Key> }]

> \<Delete Key> ：： = **Delete**\<Key Name>

> \<Key Name> ::= **'**\<AlphaNumeric>+**'**

> \<AlphaNumeric> ：： = *任意字符 NOT NULL，即 ASCII 0*

> \<Key Value> ::= \<Key Type>\<Key Name>

> \<Key Type> ：： = **s** \| **d**

> \<Key Value> ::= **'**\<AlphaNumeric>**'**

> [!NOTE]
> `HKEY_CLASSES_ROOT` 和 `HKCR` 等效; `HKEY_CURRENT_USER` 和 `HKCU` 等效; 依此类推。

分析树可以向中添加多个键和子项 \<root key> 。 在此过程中，它会使子项的句柄处于打开状态，直到分析器完成分析其所有子项。 此方法比每次对一个键进行操作更高效，如以下示例中所示：

```rgs
HKEY_CLASSES_ROOT
{
    'MyVeryOwnKey'
    {
        'HasASubKey'
        {
            'PrettyCool'
        }
    }
}
```

此时，注册机构最初会打开 (创建) `HKEY_CLASSES_ROOT\MyVeryOwnKey` 。 然后，它会发现 `MyVeryOwnKey` 具有子项。 注册器将 `MyVeryOwnKey` 保留句柄并打开 (`HasASubKey` 使用此父句柄创建) ，而不是将键关闭。 如果没有打开父句柄， (系统注册表的速度会较慢。 ) 因此，打开 `HKEY_CLASSES_ROOT\MyVeryOwnKey` 并 `HasASubKey` 打开 `MyVeryOwnKey` 作为父对象的速度比打开 `MyVeryOwnKey` 、关闭 `MyVeryOwnKey` 、然后打开 `MyVeryOwnKey\HasASubKey` 。

## <a name="see-also"></a>请参阅

[创建注册器脚本](../atl/creating-registrar-scripts.md)
