---
description: 了解详细信息： _WAIT_CHILD、_WAIT_GRANDCHILD
title: _WAIT_CHILD、_WAIT_GRANDCHILD
ms.date: 11/04/2016
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
ms.openlocfilehash: b14586232258f635b428b6c197213782591c8af1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181652"
---
# <a name="_wait_child-_wait_grandchild"></a>_WAIT_CHILD、_WAIT_GRANDCHILD

## <a name="syntax"></a>语法

```
#include <process.h>
```

## <a name="remarks"></a>备注

`_cwait` 函数可以由任何进程用来等待任何其他进程（如果进程 ID 是已知的）。 操作参数可以是以下值之一：

|返回的常量|含义|
|--------------|-------------|
|`_WAIT_CHILD`|调用进程一直等到指定的新进程终止。|
|`_WAIT_GRANDCHILD`|调用进程一直等到指定的新进程以及由该新进程创建的所有进程终止。|

## <a name="see-also"></a>请参阅

[_cwait](../c-runtime-library/reference/cwait.md)<br/>
[全局常量](../c-runtime-library/global-constants.md)
