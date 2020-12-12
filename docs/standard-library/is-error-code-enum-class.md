---
description: 了解详细信息： is_error_code_enum 类
title: is_error_code_enum 类
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: 359f15c3d809435df81408a721a0c9ad11c1e7e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323750"
---
# <a name="is_error_code_enum-class"></a>is_error_code_enum 类

表示测试 [error_code](../standard-library/error-code-class.md) 枚举的类型谓词。

## <a name="syntax"></a>语法

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>备注

如果类型 `_Enum` 是一个适合存储在类型 `error_code` 的对象中的枚举值，则此[类型谓词](../standard-library/type-traits.md)的实例为 true。

允许将专用化添加到此类型，以获得用户定义类型。

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
