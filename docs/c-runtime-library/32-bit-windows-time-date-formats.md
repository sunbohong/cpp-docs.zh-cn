---
description: 了解详细信息：32位 Windows 时间/日期格式
title: 32 位 Windows 时间-日期格式
ms.date: 11/04/2016
f1_keywords:
- vc.time
helpviewer_keywords:
- 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
ms.openlocfilehash: 3893a2abc5d00cfba7ec83209470e907f87d3e94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135780"
---
# <a name="32-bit-windows-timedate-formats"></a>32 位 Windows 时间/日期格式

将无符号整数用作位域，单独存储文件时间和日期。 文件的时间和日期打包如下：

### <a name="time"></a>时间

|位位置：|0   1   2   3   4|5   6   7   8   9   A|B   C   D   E   F|
|-------------------|-----------------------|---------------------------|-----------------------|
|长度：|5|6|5|
|内容:|小时|分钟数|2 秒的增量|
|取值范围：|0-23|0-59|2 秒间隔中的 0-29|

### <a name="date"></a>日期

|位位置：|0   1   2   3   4   5   6|7   8   9   A|B   C   D   E   F|
|-------------------|-------------------------------|-------------------|-----------------------|
|长度：|7|4|5|
|内容:|year|月份|day|
|取值范围：|0-119|1-12|1-31|
||（相对于 1980）|||

## <a name="see-also"></a>请参阅

[全局常量](../c-runtime-library/global-constants.md)
