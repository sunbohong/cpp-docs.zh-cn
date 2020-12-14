---
description: 了解详细信息：/RAWDATA
title: /RAWDATA
ms.date: 11/04/2016
f1_keywords:
- /rawdata
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
ms.openlocfilehash: efe2001c0170b8539b98902591849dedaf0fb819
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225370"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>备注

此选项显示文件中每个部分的原始内容。 参数控制显示器的格式，如下所示：

|参数|结果|
|--------------|------------|
|1|默认值。 内容以十六进制字节显示，并且在具有打印表示形式的情况下显示为 ASCII 字符。|
|2|内容显示为十六进制的2字节值。|
|4|内容显示为十六进制的4字节值。|
|8|内容显示为十六进制的8字节值。|
|无|取消原始数据。 此参数可用于控制/ALL。的输出|
|*数字*|显示的线条设置为 `number` 每行包含值的宽度。|

只有 [/HEADERS](headers.md) DUMPBIN 选项可用于由 [/GL](gl-whole-program-optimization.md) 编译器选项产生的文件。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](dumpbin-options.md)
