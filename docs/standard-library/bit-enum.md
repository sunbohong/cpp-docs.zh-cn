---
title: endian 枚举
description: 用于指定标量类型的字节排序的枚举
ms.date: 08/27/2020
f1_keywords:
- bit/std::endian
helpviewer_keywords:
- std::endian
ms.openlocfilehash: 78df181e20d0e5d72508bd0fc86118528a312d6b
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194753"
---
# <a name="endian-enum"></a>endian 枚举

指示所有标量类型的 endian 类型。

## <a name="syntax"></a>语法

```cpp
enum class endian {
    little = 0,
    big = 1,
    native = little
 };
```

### <a name="members"></a>成员

|元素|描述|
|-|-|
| `little` | 指示标量类型为小字节序。 也就是说，最小有效字节存储在最小地址中。 例如， `0x1234` 存储 `0x34` `0x12` 。  |
| `big` | 指示标量类型为大字节序，也就是说，最高有效字节存储在最小地址中。 例如， `0x1234` 存储 `0x12` `0x34` 。  |

## <a name="remarks"></a>备注

对于 (x86、x64、ARM、ARM64) Microsoft Visual C++ 目标的平台，所有本机标量类型都是小字节序。

## <a name="requirements"></a>要求

**标头：**\<bit>

**命名空间:** std

`/std:c++latest` 是必需的

## <a name="see-also"></a>另请参阅

[\<bit>](../standard-library/bit.md)  
