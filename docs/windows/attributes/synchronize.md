---
description: 了解详细信息：同步
title: " (c + + COM 特性同步) "
ms.date: 10/02/2018
f1_keywords:
- vc-attr.synchronize
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
ms.openlocfilehash: bbee19406396e4041b4d7ca1e2acf2b8d7193494
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329548"
---
# <a name="synchronize"></a>synchronize

同步对目标方法的访问。

## <a name="syntax"></a>语法

```cpp
[synchronize]
```

## <a name="remarks"></a>备注

**同步** c + + 属性实现对同步对象的目标方法的支持。 同步允许多个对象使用公共资源 (例如类的方法) 通过控制目标方法的访问。

此属性插入的代码调用正确的 `Lock` 方法， (由目标方法开头的线程模型) 确定。 退出该方法时， `Unlock` 将自动调用。 有关这些函数的详细信息，请参阅 [CComAutoThreadModule：： Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)

此属性要求 [coclass](coclass.md)、 [progid](progid.md)或 [vi_progid](vi-progid.md) 属性（或隐含这些属性之一的其他属性）也应用于同一个元素。 如果使用任何单个属性，则会自动应用另外两个属性。 例如，如果 `progid` 应用了，则 `vi_progid` `coclass` 还会应用。

## <a name="example"></a>示例

下面的代码为对象的方法提供同步 `UpdateBalance` `CMyClass` 。

```cpp
// cpp_attr_ref_synchronize.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="SYNC")];

[coclass,
threading(both),
vi_progid("MyProject.MyClass"),
progid("MyProject.MyClass.1"),
uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")
]
class CMyClass {
   float m_nBalance;

   [synchronize]
   void UpdateBalance(float nAdjust) {
      m_nBalance += nAdjust;
   }
};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|类方法、方法|
|**且**|否|
|**必需属性**|以下一项或多项操作： `coclass` 、 `progid` 或 `vi_progid` 。|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[COM 特性](com-attributes.md)
