---
description: 了解详细信息： CloakedIid 结构
title: CloakedIid 结构
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 06bddded27882ae1216064aafc311364a8d2fd9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338791"
---
# <a name="cloakediid-structure"></a>CloakedIid 结构

向 `RuntimeClass` `Implements` 和 `ChainInterfaces` 模板指示指定接口在 IID 列表中不可访问。

## <a name="syntax"></a>语法

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>parameters

*T*<br/>
被掩蔽)  (隐藏的接口。

## <a name="remarks"></a>备注

下面是如何使用 **CloakedIid** 的示例： `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`T`

`CloakedIid`

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
