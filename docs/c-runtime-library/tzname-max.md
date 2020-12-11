---
description: 了解详细信息： TZNAME_MAX
title: TZNAME_MAX
ms.date: 10/22/2018
f1_keywords:
- TZNAME_MAX
helpviewer_keywords:
- TZNAME_MAX constant
ms.assetid: e2286cb8-751d-4557-9650-5c4b98a8f7be
ms.openlocfilehash: 1c426c82bd198998169c385366ae5188cabd02d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162087"
---
# <a name="tzname_max"></a>TZNAME_MAX

**过时**。 时区名称变量允许的最大字符串长度。 此宏是在 \<limits.h> Visual Studio 2012 及更早版本中定义的。 Visual Studio 2013 及更高版本中未定义它。 要获取保存当前时区名称所需的长度，请使用 [_get_tzname](../c-runtime-library/reference/get-tzname.md)。

## <a name="syntax"></a>语法

```
#include <limits.h>
```

## <a name="see-also"></a>请参阅

[环境常量](../c-runtime-library/environmental-constants.md)<br/>
[全局常量](../c-runtime-library/global-constants.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)
