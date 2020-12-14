---
description: 了解详细信息： _CRT_DISABLE_PERFCRIT_LOCKS
title: _CRT_DISABLE_PERFCRIT_LOCKS
ms.date: 11/04/2016
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
ms.openlocfilehash: b96e29fad635ac9e7f3d622ace3c43bb26c8805a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195679"
---
# <a name="_crt_disable_perfcrit_locks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

在 I/O 操作中禁用性能关键锁定。

## <a name="syntax"></a>语法

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>备注

定义此符号可通过强制所有 I/O 操作采用单线程 I/O 模型，来提高单线程 I/O 绑定程序的性能。 有关详细信息，请参阅[多线程库性能](../c-runtime-library/multithreaded-libraries-performance.md)。

## <a name="see-also"></a>请参阅

[全局常量](../c-runtime-library/global-constants.md)
