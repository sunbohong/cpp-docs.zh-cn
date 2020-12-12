---
description: '了解详细信息： uuid (c + +) '
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: c841bb1813769ab70e756fe4edb7fd351c1dbc49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116725"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft 专用**

编译器会将 GUID 附加到声明或定义的类或结构， (仅) 具有特性的完整 COM 对象定义 **`uuid`** 。

## <a name="syntax"></a>语法

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>备注

**`uuid`** 特性采用字符串作为其参数。 此字符串以带有或不带 **{}** 分隔符的普通注册表格式命名 GUID。 例如：

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

此特性可应用于重新声明。 这允许系统标头提供接口（如）的定义 `IUnknown` ，以及其他一些标头中的重新声明 (如 \<comdef.h>) 来提供 GUID。

可以应用关键字 [__uuidof](../cpp/uuidof-operator.md) 来检索附加到用户定义类型的常量 GUID。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__declspec](../cpp/declspec.md)<br/>
[关键字](../cpp/keywords-cpp.md)
