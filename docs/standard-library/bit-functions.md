---
title: '&lt;位 &gt; 函数'
description: 用于访问、操作和处理单个位和位序列的函数
ms.date: 08/28/2020
f1_keywords:
- bit/std::bit_cast
- bit/std::has_single_bit
- bit/std::bit_ceil
- bit/std::bit_floor
- bit/std::bit_width
- bit/std::rotl
- bit/std::rotr
- bit/std::countl_zero
- bit/std::countl_one
- bit/std::countr_zero
- bit/std::countr_one
- bit/std::popcount
helpviewer_keywords:
- std::bit [C++], bit_cast
- std::bit [C++], has_single_bit
- std::bit [C++], bit_ceil
- std::bit [C++], bit_floor
- std::bit [C++], bit_width
- std::bit [C++], rotl
- std::bit [C++], rotr
- std::bit [C++], countl_zero
- std::bit [C++], countl_one
- std::bit [C++], countr_zero
- std::bit [C++], countr_one
- std::bit [C++], popcount
ms.openlocfilehash: 94e44493b9356b3a0717c42aa1bed510ebe460dd
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509978"
---
# <a name="ltbitgt-functions"></a>&lt;位 &gt; 函数

\<bit>标头包括下列非成员模板函数：

| **非成员函数** | **说明** |
|--------|---------|
|[bit_cast](#bit_cast) | 重新解释从一种类型到另一种类型的对象表示形式。 |
|[bit_ceil](#bit_ceil) | 查找两个大于或等于某个值的最小幂。 |
|[bit_floor](#bit_floor) | 查找两个 not 大于值的最大幂。 |
|[bit_width](#bit_width) | 查找表示一个值所需的最小位数。 |
|[countl_zero](#countl_zero) | 计算从最高有效位开始，将连续位数设置为零。 |
|[countl_one](#countl_one) | 从最高有效位开始，计算设置为1的连续位的数量。 |
|[countr_zero](#countr_zero) | 计算从最小有效位开始，将连续位数设置为零。 |
|[countr_one](#countl_one) | 从最小有效位开始，计算设置为1的连续位的数量。 |
|[has_single_bit](#has_single_bit) | 检查某个值是否只有一位设置为1位。 这与测试值是否为2的幂相同。 |
|[popcount](#popcount) | 计算设置为1的位数。 |
|[rotl](#rotl) | 计算按位左旋转的结果。 |
|[rotr](#rotr) | 计算按位右旋转的结果。 |

## <a name="bit_cast"></a>`bit_cast`

将位模式从类型的对象复制 `From` 到类型的新对象 `To` 。

```cpp
template <class To, class From>
[[nodiscard]] constexpr To bit_cast(const From& from) noexcept;
```

### <a name="parameters"></a>参数

*自*\
输出的类型。

*从*\
要转换的值的类型。

*从*\
要转换的值。

### <a name="return-value"></a>返回值

一个 `To` 类型的对象。

结果中的每个位都与中的相应位匹配 `from` ，除非中有填充位 `To` ，在这种情况下，结果中的位是未指定的。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <iostream>

int main()
{
    float f = std::numeric_limits<float>::infinity();
    int i = std::bit_cast<int>(f);
    std::cout << "float f = " << std::hex << f
              << "\nstd::bit_cat<int>(f) = " << std::hex << i << '\n';
    return 0;
}
```

```Output
float f = inf
std::bit_cat<int>(f) = 7f800000
```

### <a name="remarks"></a>注解

低级别代码通常需要将一种类型的对象解释为另一种类型。 重新解释对象与原始对象具有相同的位表示形式，但它是不同的类型。

不使用 `reinterpret_cast` 或 `memcpy()` ， `bit_cast()` 是进行这些转换的更好方法。 更好的原因是：

- `bit_cast()` 是 `constexpr`
- `bit_cast()` 要求完全复制和大小相同的类型。 这会阻止你使用和可能遇到的潜在问题， `reinterpret_cast` `memcpy` 因为这些问题可能会被错误地用于转换非完全复制类型。 此外，还可 `memcpy()` 用于在不相同大小的类型之间进行意外复制。 例如，double (8 字节) 为无符号 int (4 个字节) ，或其他方法。

此重载仅在以下情况下参与重载决策：

- `sizeof(To) == sizeof(From)`
- `To` 和 `From` 是 [is_trivially_copyable](is-trivially-copyable-class.md)。

`constexpr`当且仅当 `To` 、和子其子 `From` 类型的类型为时，此函数模板为：

- 不是联合或指针类型
- 不是指向成员类型的指针
- 非易失性
- 不具有作为引用类型的非静态数据成员

## <a name="bit_ceil"></a>`bit_ceil`

查找两个大于或等于某个值的最小幂。 例如，给定 `3` ，返回 `4` 。

```cpp
template<class T>
[[nodiscard]] constexpr T bit_ceil(T value);
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

 两个大于或等于的最小幂 `value` 。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (auto i = 0u; i < 6u; ++i) // bit_ceil() takes an unsigned integer type
    {
        auto nextClosestPowerOf2 = std::bit_ceil(i);
        std::cout << "\nbit_ceil(0b" << std::bitset<4>(i) << ") = "
                  << "0b" << std::bitset<4>(nextClosestPowerOf2);
    }
    return 0;
}
```

```Output
bit_ceil(0b0000) = 0b0001
bit_ceil(0b0001) = 0b0001
bit_ceil(0b0010) = 0b0010
bit_ceil(0b0011) = 0b0100
bit_ceil(0b0100) = 0b0100
bit_ceil(0b0101) = 0b1000
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="bit_floor"></a>`bit_floor`

查找两个 not 大于值的最大幂。 例如，给定 `5` ，返回 `4` 。

```cpp
template< class T >
[[nodiscard]] constexpr T bit_floor(T value) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

2的最大幂，不大于 `value` 。 \
如果 `value` 为零，则返回零。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (auto i = 0u; i < 6u; ++i) // bit_floor() takes an unsigned integer type
    {
        auto previousPowerOf2 = std::bit_floor(i);
        std::cout << "\nbit_floor(0b" << std::bitset<4>(i) << ") = 0b"
                  << std::bitset<4>(previousPowerOf2);
    }
    return 0;
}
```

```Output
bit_floor(0b0000) = 0b0000
bit_floor(0b0001) = 0b0001
bit_floor(0b0010) = 0b0010
bit_floor(0b0011) = 0b0010
bit_floor(0b0100) = 0b0100
bit_floor(0b0101) = 0b0100
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="bit_width"></a>`bit_width`

查找表示一个值所需的最小位数。

例如，给定 5 (0b101) ，返回3，因为它使用3个二进制位表示值5。

```cpp
template<class T>
[[nodiscard]] constexpr T bit_width(T value) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

要表示的所需的位数 `value` 。
如果 `value` 为零，则返回零。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <iostream>

int main()
{
    for (unsigned i=0u; i <= 8u; ++i)
    {
        std::cout << "\nbit_width(" << i << ") = "
                  << std::bit_width(i);
    }
    return 0;
}
```

```Output
bit_width(0) = 0
bit_width(1) = 1
bit_width(2) = 2
bit_width(3) = 2
bit_width(4) = 3
bit_width(5) = 3
bit_width(6) = 3
bit_width(7) = 3
bit_width(8) = 4
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="countl_zero"></a>`countl_zero`

计算从最高有效位开始，将连续位数设置为零。

```cpp
template<class T>
[[nodiscard]] constexpr int countl_zero(T value) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

从最高有效位开始的连续零位位数。
如果 `value` 为零，则为类型中的位数 `value` 。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (unsigned char result = 0, i = 0; i < 9; i++)
    {
        std::cout << "\ncountl_zero(0b" << std::bitset<8>(result) << ") = " << std::countl_zero(result);
        result = result == 0 ? 1 : result * 2;
    }
    return 0;
}
```

```Output
countl_zero(0b00000000) = 8
countl_zero(0b00000001) = 7
countl_zero(0b00000010) = 6
countl_zero(0b00000100) = 5
countl_zero(0b00001000) = 4
countl_zero(0b00010000) = 3
countl_zero(0b00100000) = 2
countl_zero(0b01000000) = 1
countl_zero(0b10000000) = 0
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="countl_one"></a>`countl_one`

从最高有效位开始，计算设置为1的连续位的数量。

```cpp
template<class T>
[[nodiscard]] constexpr int countl_one(T value) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

从最高有效位开始，设置为1的连续位的数目。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char value = 0;
    for (unsigned char bit = 128; bit > 0; bit /= 2)
    {
        value |= bit;
        std::cout << "\ncountl_one(0b" << std::bitset<8>(value) << ") = "
                  << std::countl_one(value);
    }
    return 0;
}
```

```Output
countl_one(0b10000000) = 1
countl_one(0b11000000) = 2
countl_one(0b11100000) = 3
countl_one(0b11110000) = 4
countl_one(0b11111000) = 5
countl_one(0b11111100) = 6
countl_one(0b11111110) = 7
countl_one(0b11111111) = 8
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="countr_zero"></a>`countr_zero`

计算从最小有效位开始，将连续位数设置为零。

```cpp
template<class T>
[[nodiscard]] constexpr int countr_zero(T value) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

从最小有效位开始的连续零位的数量。
如果 `value` 为零，则为类型中的位数 `value` 。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (unsigned char result = 0, i = 0; i < 9; i++)
    {
        std::cout << "\ncountr_zero(0b" << std::bitset<8>(result) << ") = "
                  << std::countr_zero(result);
        result = result == 0 ? 1 : result * 2;
    }
    return 0;
}
```

```Output
countr_zero(0b00000000) = 8
countr_zero(0b00000001) = 0
countr_zero(0b00000010) = 1
countr_zero(0b00000100) = 2
countr_zero(0b00001000) = 3
countr_zero(0b00010000) = 4
countr_zero(0b00100000) = 5
countr_zero(0b01000000) = 6
countr_zero(0b10000000) = 7
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="countr_one"></a>`countr_one`

从最小有效位开始，计算设置为1的连续位的数量。

```cpp
template<class T>
[[nodiscard]] constexpr int countr_one(T value) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

从最小有效位开始，设置为1的连续位的数量。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char value = 0;
    for (int bit = 1; bit <= 128; bit *= 2)
    {
        value |= bit;
        std::cout << "\ncountr_one(0b" << std::bitset<8>(value) << ") = "
                  << std::countr_one(value);
    }
    return 0;
}
```

```Output
countr_one(0b00000001) = 1
countr_one(0b00000011) = 2
countr_one(0b00000111) = 3
countr_one(0b00001111) = 4
countr_one(0b00011111) = 5
countr_one(0b00111111) = 6
countr_one(0b01111111) = 7
countr_one(0b11111111) = 8
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="has_single_bit"></a>`has_single_bit`

检查某个值是否仅设置了一个位。这与测试值是否为2的幂相同。

```cpp
template <class T>
[[nodiscard]] constexpr bool has_single_bit(T value) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

`true` 如果 `value` 只有一个位集，这也意味着 `value` 是2的幂。 否则为 `false`。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>
#include <iomanip>

int main()
{
    for (auto i = 0u; i < 10u; ++i)
    {
        std::cout << "has_single_bit(0b" << std::bitset<4>(i) << ") = "
                  << std::boolalpha << std::has_single_bit(i) << '\n';
    }
    return 0;
}
```

```Output
has_single_bit(0b0000) = false
has_single_bit(0b0001) = true
has_single_bit(0b0010) = true
has_single_bit(0b0011) = false
has_single_bit(0b0100) = true
has_single_bit(0b0101) = false
has_single_bit(0b0110) = false
has_single_bit(0b0111) = false
has_single_bit(0b1000) = true
has_single_bit(0b1001) = false
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="popcount"></a>`popcount`

计算在无符号整数值中设置为1的位的数目。

```cpp
template<class T>
[[nodiscard]] constexpr int popcount(T value) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要测试的无符号整数值。

### <a name="return-value"></a>返回值

在中设置为1的位数 `value` 。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
   for (unsigned char value = 0; value < 16; value++)
    {
        std::cout << "\npopcount(0b" << std::bitset<4>(value) << ") = "
                  << std::popcount(value);
    }
    return 0;
}
```

```Output
popcount(0b0000) = 0
popcount(0b0001) = 1
popcount(0b0010) = 1
popcount(0b0011) = 2
popcount(0b0100) = 1
popcount(0b0101) = 2
popcount(0b0110) = 2
popcount(0b0111) = 3
popcount(0b1000) = 1
popcount(0b1001) = 2
popcount(0b1010) = 2
popcount(0b1011) = 3
popcount(0b1100) = 2
popcount(0b1101) = 3
popcount(0b1110) = 3
popcount(0b1111) = 4
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="rotl"></a>`rotl`

将无符号整数值的位数向左旋转指定的次数。 最左侧的位的 "过时" 位会旋转到最右侧。

```cpp
template<class T>
[[nodiscard]] constexpr T rotl(T value, int s) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要旋转的无符号整数值。

*些*\
要执行的左旋转的数目。

### <a name="return-value"></a>返回值

`value`左转、时间的结果 `s` 。 \
如果 `s` 为零，则返回 `value` 。 \
如果 `s` 为负，则为 `rotr(value, -s)` 。 最右边的位的 "过时" 位会旋转到最左边的位。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char bits = 1;
    for (int i = 0; i < 8; ++i)
    {
        std::cout << "rotl(0b" << std::bitset<8>(bits) << ", 1) = ";
        bits = std::rotl(bits, 1);
        std::cout << "0b" << std::bitset<8>(bits) << '\n';
    }
    std::cout << "rotl(0b" << std::bitset<8>(bits) << ",-1) = ";
    bits = std::rotl(bits, -1);
    std::cout << "0b" << std::bitset<8>(bits);
    return 0;
}
```

```Output
rotl(0b00000001, 1) = 0b00000010
rotl(0b00000010, 1) = 0b00000100
rotl(0b00000100, 1) = 0b00001000
rotl(0b00001000, 1) = 0b00010000
rotl(0b00010000, 1) = 0b00100000
rotl(0b00100000, 1) = 0b01000000
rotl(0b01000000, 1) = 0b10000000
rotl(0b10000000, 1) = 0b00000001
rotl(0b00000001,-1) = 0b10000000
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="rotr"></a>`rotr`

将右侧的位数旋转 `value` 指定的次数。 最右边的位的 "过时" 位会旋转回最左端的位。

```cpp
template<class T>
[[nodiscard]] constexpr T rotr(T value, int s) noexcept;
```

### <a name="parameters"></a>参数

*负值*\
要旋转的无符号整数值。

*些*\
要执行的右旋转的数目。

### <a name="return-value"></a>返回值

向右旋转的结果 `value` ， `s`
如果 `s` 为零，则返回 `value` 。 \
如果 `s` 为负，则为 `rotl(value, -s)` 。 最左侧的位的 "过时" 位会旋转回最右端。

### <a name="example"></a>示例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char bits = 128;
    for (int i = 0; i < 8; ++i)
    {
        std::cout << "rotr(0b" << std::bitset<8>(bits) << ", 1) = ";
        bits = std::rotr(bits, 1);
        std::cout << "0b" << std::bitset<8>(bits) << '\n';
    }
    std::cout << "rotr(0b" << std::bitset<8>(bits) << ",-1) = ";
    bits = std::rotr(bits, -1);
    std::cout << "0b" << std::bitset<8>(bits);
    return 0;
}
```

```Output
rotr(0b10000000, 1) = 0b01000000
rotr(0b01000000, 1) = 0b00100000
rotr(0b00100000, 1) = 0b00010000
rotr(0b00010000, 1) = 0b00001000
rotr(0b00001000, 1) = 0b00000100
rotr(0b00000100, 1) = 0b00000010
rotr(0b00000010, 1) = 0b00000001
rotr(0b00000001, 1) = 0b10000000
rotr(0b10000000,-1) = 0b00000001
```

### <a name="remarks"></a>注解

如果 `T` 是无符号整数类型，则此模板函数仅参与重载决策。 例如： `unsigned int` 、、 `unsigned long` 、 `unsigned short` 等 `unsigned char` 。

## <a name="requirements"></a>要求

**标头：**\<bit>

**命名空间:** std

[/std：需要 c + + 最新版本](../build/reference/std-specify-language-standard-version.md) 。

## <a name="see-also"></a>请参阅

[\<bit>](bit.md)
