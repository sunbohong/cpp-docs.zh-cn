---
description: 了解详细信息： ActivatableClass 宏
title: ActivatableClass 宏
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
ms.openlocfilehash: 2b59101373de72ca88338750bb7fe9169376ac65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287939"
---
# <a name="activatableclass-macros"></a>ActivatableClass 宏

填充内部缓存，其中包含可创建指定类的实例的工厂。

## <a name="syntax"></a>语法

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>parameters

*className*<br/>
要创建的类的名称。

*工厂*<br/>
将创建指定类的实例的工厂。

*serverName*<br/>
指定模块中工厂子集的名称。

## <a name="remarks"></a>备注

不要将这些宏与经典 COM 一起使用，除非使用 `#undef` 指令确保 `__WRL_WINRT_STRICT__` 删除了宏定义。

## <a name="requirements"></a>要求

**标头：** 模块。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Module 类](module-class.md)
