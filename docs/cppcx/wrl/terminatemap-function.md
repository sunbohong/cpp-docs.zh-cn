---
description: 了解详细信息： TerminateMap 函数
title: TerminateMap 函数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 919759d0b4b7f67cf3aff83c3e83678860d0badc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135058"
---
# <a name="terminatemap-function"></a>TerminateMap 函数

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>parameters

*模块*<br/>
[模块](module-class.md)。

*serverName*<br/>
由 parameter *module* 指定的模块中的类工厂子集的名称。

*forceTerminate*<br/>
**`true`** 不管类工厂是否处于活动状态，都要终止类工厂; **`false`** 如果任何工厂处于活动状态，则不终止类工厂。

## <a name="return-value"></a>返回值

**`true`** 如果所有类工厂均已终止，则为;否则为 **`false`** 。

## <a name="remarks"></a>备注

关闭指定模块中的类工厂。

## <a name="requirements"></a>要求

**标头：** 模块。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="see-also"></a>请参阅

[Microsoft：： WRL：:D etails 命名空间](microsoft-wrl-details-namespace.md)
