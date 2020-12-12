---
description: '了解有关详细信息，请参阅 C/c + + (名称) '
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: 7444aa20539b47b1f04d17a266a0b65a552af3f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137769"
---
# <a name="name-cc"></a>NAME (C/C++)

指定主输出文件的名称。

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>备注

指定输出文件名的等效方法是使用 [/out](out-output-file-name.md) 链接器选项，使用 [/base](base-base-address.md) 链接器选项设置基址的等效方法。 如果同时指定两者，则/OUT 会重写 **名称**。

如果生成一个 DLL，则 NAME 仅会影响 DLL 名称。

## <a name="see-also"></a>请参阅

[Module-Definition 语句的规则](rules-for-module-definition-statements.md)
