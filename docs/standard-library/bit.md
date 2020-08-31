---
title: '&lt;bit&gt;'
description: 用于访问、操作和处理单个位和位序列的函数。
ms.date: 08/28/2020
f1_keywords:
- <bit>
helpviewer_keywords:
- bit header
ms.openlocfilehash: 7a87071d30756714e19c971281f642ce16f09d61
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194754"
---
# <a name="ltbitgt"></a>&lt;bit&gt;

定义用于访问、操作和处理单个位和位序列的函数。

例如，有一些函数可以旋转位，查找连续设置或清除的位的数量，查看数字是否是二的整数幂，查找表示数字的最小位数，等等。

## <a name="requirements"></a>要求

**标头：**\<bit>

**命名空间:** std

`/std:c++latest` 是必需的

## <a name="members"></a>成员

### <a name="types"></a>类型

| 类型 | 描述 |
|--------|----------|
| [端](bit-enum.md) | 指定标量类型的字节排序。 |

### <a name="functions"></a>函数

| 函数 | 描述 |
|-----|-----|
|[bit_cast](bit-functions.md#bit_cast) | 重新解释从一种类型到另一种类型的对象表示形式。 |
|[bit_ceil](bit-functions.md#bit_ceil) | 查找两个大于或等于某个值的最小幂。 |
|[bit_floor](bit-functions.md#bit_floor) | 查找两个 not 大于值的最大整数幂。 |
|[bit_width](bit-functions.md#bit_width) | 查找表示一个值所需的最小位数。 |
|[countl_zero](bit-functions.md#countl_zero) | 计算从最高有效位开始，将连续位数设置为零。 |
|[countl_one](bit-functions.md#countl_one) | 从最高有效位开始，计算设置为1的连续位的数量。 |
|[countr_zero](bit-functions.md#countr_zero) | 计算从最小有效位开始，将连续位数设置为零。 |
|[countr_one](bit-functions.md#countl_one) | 从最小有效位开始，计算设置为1的连续位的数量。 |
|[has_single_bit](bit-functions.md#has_single_bit) | 检查某个值是否只有一位设置为1位。 这与测试值是否为2的幂相同。 |
|[popcount](bit-functions.md#popcount) | 计算设置为1的位数。 |
|[rotl](bit-functions.md#rotl) | 计算按位左旋转的结果。 |
|[rotr](bit-functions.md#rotr) | 计算按位右移位的结果。 |

## <a name="see-also"></a>另请参阅

[头文件引用](cpp-standard-library-header-files.md)