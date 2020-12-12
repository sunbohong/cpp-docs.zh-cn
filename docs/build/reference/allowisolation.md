---
description: 了解详细信息：/ALLOWISOLATION
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION_EDITBIN
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 7d935bc122b5f32bb8f1193feae58b5fc61e7faa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179585"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

指定清单查找的行为。

## <a name="syntax"></a>语法

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>备注

**/ALLOWISOLATION** 导致操作系统进行清单查找和加载。

默认值为 **/ALLOWISOLATION** 。

**/ALLOWISOLATION： NO** 表示加载可执行文件，就像没有清单一样，并导致 [EDITBIN Reference](editbin-reference.md) 在 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` 可选标头的字段中设置位 `DllCharacteristics` 。

当对可执行文件禁用隔离时，Windows 加载程序不会尝试为新创建的进程查找应用程序清单。 新进程没有默认激活上下文，即使可执行文件本身中有清单或存在名为 *executable*. .manifest 的清单也是如此。

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)<br/>
[/ALLOWISOLATION (清单查找) ](allowisolation-manifest-lookup.md)<br/>
[清单文件引用](/windows/win32/SbsCs/manifest-files-reference)
