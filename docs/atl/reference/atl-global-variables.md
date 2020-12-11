---
description: 了解更多： ATL 全局变量
title: ATL 全局变量
ms.date: 12/06/2017
f1_keywords:
- ATLBASE/_pAtlModule
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
ms.openlocfilehash: 8d0544651e32f5e569973466af8ce04af1433766
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158772"
---
# <a name="atl-global-variables"></a>ATL 全局变量

## <a name="_patlmodule"></a>_pAtlModule

存储指向当前模块的指针的全局变量。

```cpp
__declspec(selectany) CAtlModule * _pAtlModule
```

### <a name="remarks"></a>备注

此全局变量上的方法可用于提供 (现已过时的功能) 在 Visual C++ 6.0 中提供的类 CComModule。

### <a name="example"></a>示例

```cpp
LONG lLocks = _pAtlModule->GetLockCount();
```

### <a name="requirements"></a>要求

**标头：** atlbase。h
