---
description: 了解详细信息： tlbid import 特性
title: tlbid 导入属性
ms.date: 08/29/2019
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 9bbf15f64c1813013fcd839a2d4f0a34c9872aff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339048"
---
# <a name="tlbid-import-attribute"></a>tlbid 导入属性

**C++ 专用**

允许加载主类型库之外的库。

## <a name="syntax"></a>语法

> **#import** *类型库-dll* **tlbid (** *编号* **)**

### <a name="parameters"></a>parameters

*多种*\
类型库中的类型库的编号 *（dll）*。

## <a name="remarks"></a>备注

如果有多个类型库内置于一个 DLL 中，则可以使用 **tlbid** 加载主类型库以外的库。

例如：

```cpp
#import <MyResource.dll> tlbid(2)
```

等效于：

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
