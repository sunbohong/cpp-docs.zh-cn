---
description: 了解详细信息： AsyncResultType 枚举
title: AsyncResultType 枚举
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: 431c0cabf98b3636bbae02b2f05a14d11d122740
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175815"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 枚举

指定由方法返回的结果的类型 `GetResults()` 。

## <a name="syntax"></a>语法

```cpp
enum AsyncResultType;
```

## <a name="members"></a>成员

### <a name="values"></a>值

|“属性”|描述|
|----------|-----------------|
|`MultipleResults`|一组多个结果，这些结果在 `Start` 状态和之前的状态之间逐渐显示 `Close()` 。|
|`SingleResult`|事件发生后显示的单个结果 `Complete` 。|

## <a name="requirements"></a>要求

**标头：** async。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
