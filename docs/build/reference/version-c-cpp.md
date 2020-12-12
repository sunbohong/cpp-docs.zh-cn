---
description: '了解详细信息：版本 (C/c + +) '
title: VERSION (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VERSION
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
ms.openlocfilehash: 1a63435c752220ab9fef54628ab101a14ef58582
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176387"
---
# <a name="version-cc"></a>VERSION (C/C++)

告诉链接，在 .exe 文件或 DLL 的标头中放置一个数字。

```
VERSION major[.minor]
```

## <a name="remarks"></a>备注

*主要* 和 *次要* 参数是介于0到65535之间的十进制数字。 默认值为0.0 版。

指定版本号的等效方法是使用 (/VERSION) 选项的 [版本信息](version-version-information.md) 。

## <a name="see-also"></a>请参阅

[Module-Definition 语句的规则](rules-for-module-definition-statements.md)
