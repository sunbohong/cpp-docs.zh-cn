---
description: 了解详细信息：/LINKERMEMBER
title: /LINKERMEMBER
ms.date: 11/04/2016
f1_keywords:
- /linkermember
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
ms.openlocfilehash: 76c842bcc2299b4245847e7d4e9a64656e88d2d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199384"
---
# <a name="linkermember"></a>/LINKERMEMBER

```
/LINKERMEMBER[:{1|2}]
```

## <a name="remarks"></a>备注

此选项显示库中定义的公共符号。 指定1参数以按对象顺序显示符号及其偏移量。 指定2参数以显示对象的偏移量和索引编号，然后按字母顺序列出符号以及每个参数的对象索引。 若要获取两个输出，请指定不带 number 参数的/LINKERMEMBER。

只有 [/HEADERS](headers.md) DUMPBIN 选项可用于由 [/GL](gl-whole-program-optimization.md) 编译器选项产生的文件。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](dumpbin-options.md)
