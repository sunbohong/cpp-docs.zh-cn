---
description: 了解有关以下内容的详细信息： &lt; type_traits &gt; typedef
title: '&lt;type_traits&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::false_type
- xtr1common/std::false_type
- type_traits/std::true_type
- xtr1common/std::true_type
ms.assetid: 8ac040ca-ed2d-4570-adc9-cb5626530053
ms.openlocfilehash: ec5902ce21b3ca26e44acb66cc738a12b6478010
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253294"
---
# <a name="lttype_traitsgt-typedefs"></a>&lt;type_traits&gt; typedef

[false_type](#false_type)\
[true_type](#true_type)

## <a name="false_type-typedef"></a><a name="false_type"></a> false_type Typedef

保留包含值 false 的整数常量。

```cpp
typedef integral_constant<bool, false> false_type;
```

### <a name="remarks"></a>备注

该类型是模板 `integral_constant` 的专用化的同义词。

### <a name="example"></a>示例

```cpp
#include <type_traits>
#include <iostream>

int main() {
    std::cout << "false_type == " << std::boolalpha
        << std::false_type::value << std::endl;
    std::cout << "true_type == " << std::boolalpha
        << std::true_type::value << std::endl;

    return (0);
}
```

```Output
false_type == false
true_type == true
```

## <a name="true_type-typedef"></a><a name="true_type"></a> true_type Typedef

保留包含值 true 的整数常量。

```cpp
typedef integral_constant<bool, true> true_type;
```

### <a name="remarks"></a>备注

该类型是模板 `integral_constant` 的专用化的同义词。

### <a name="example"></a>示例

```cpp
// std__type_traits__true_type.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main() {
    std::cout << "false_type == " << std::boolalpha
        << std::false_type::value << std::endl;
    std::cout << "true_type == " << std::boolalpha
        << std::true_type::value << std::endl;

    return (0);
}
```

```Output
false_type == false
true_type == true
```

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
