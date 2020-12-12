---
description: 了解详细信息： fseek、_lseek 常量
title: fseek、_lseek 常量
ms.date: 11/04/2016
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
ms.openlocfilehash: be12597682074f610b0a69395146b400fed4d6b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319812"
---
# <a name="fseek-_lseek-constants"></a>fseek、_lseek 常量

## <a name="syntax"></a>语法

```
#include <stdio.h>
```

## <a name="remarks"></a>备注

origin 参数指定初始位置，可以是下列清单常量之一：

|返回的常量|含义|
|--------------|-------------|
|`SEEK_END`|文件结尾|
|`SEEK_CUR`|文件指针的当前位置|
|`SEEK_SET`|文件开头|

## <a name="see-also"></a>请参阅

[fseek、_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)<br/>
[_lseek、_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)<br/>
[全局常量](../c-runtime-library/global-constants.md)
