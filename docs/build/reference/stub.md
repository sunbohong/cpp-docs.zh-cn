---
description: 了解详细信息：存根
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 79a2002c119bf211652e2aab51d9656b36e3d159
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230284"
---
# <a name="stub"></a>STUB

当在 (VxD) 的虚拟设备驱动程序生成虚拟设备驱动程序的模块定义文件中使用时，允许您指定一个文件名，该文件包含在 WINNT 中定义 (IMAGE_DOS_HEADER 结构。H) 用于虚拟设备驱动程序 (VxD) ，而不是默认标头。

```
STUB:filename
```

## <a name="remarks"></a>备注

指定 *filename* 的等效方法是使用 [/STUB](stub-ms-dos-stub-file-name.md) 链接器选项。

存根仅在生成 VxD 时在模块定义文件中有效。

## <a name="see-also"></a>请参阅

[Module-Definition 语句的规则](rules-for-module-definition-statements.md)
