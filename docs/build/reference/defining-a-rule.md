---
description: 了解详细信息：定义规则
title: 定义规则
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: 89a5db90162ede02743aa469ac4f9e3d75c5e147
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201672"
---
# <a name="defining-a-rule"></a>定义规则

*Fromext* 表示依赖文件的扩展名， *toext* 表示目标文件的扩展名。

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>备注

扩展名不区分大小写。 可以调用宏来表示 *fromext* 和 *toext*;在预处理过程中将展开宏。 句点 )  ( 前面的 *fromext* 必须出现在行的开头。 冒号 (： ) 前面有零个或多个空格或制表符。 只能跟随空格或制表符，使用分号 (; ) 指定命令、数字符号 ( # ) 指定注释或换行字符。 不允许使用其他空格。 在说明块中将命令指定为。

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

[规则中的搜索路径](search-paths-in-rules.md)

## <a name="see-also"></a>请参阅

[推理规则](inference-rules.md)
