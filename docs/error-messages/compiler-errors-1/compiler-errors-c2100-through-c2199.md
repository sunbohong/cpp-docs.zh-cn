---
description: 了解有关以下内容的详细信息：编译器错误 S c2100 到 C2199
title: 编译器错误 C2100 - C2199
ms.date: 04/21/2019
f1_keywords:
- C2119
- C2123
- C2125
- C2126
- C2127
- C2136
- C2176
- C2187
- C2189
helpviewer_keywords:
- C2119
- C2123
- C2125
- C2126
- C2127
- C2131
- C2136
- C2176
- C2187
- C2189
ms.assetid: 1ccab076-0954-4386-b959-d3112a6793ae
ms.openlocfilehash: 5948ed2d41a5b20e9c599c6a4c2b27198f8b2d4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318970"
---
# <a name="compiler-errors-c2100-through-c2199"></a>编译器错误 C2100 - C2199

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|[编译器错误 C2100](compiler-error-c2100.md)|非法间接寻址|
|[编译器错误 C2101](compiler-error-c2101.md)|常量上的“&”|
|[编译器错误 C2102](compiler-error-c2102.md)|"&" 要求左值|
|[编译器错误 C2103](compiler-error-c2103.md)|寄存器变量上的“&”|
|[编译器错误 C2104](compiler-error-c2104.md)|已忽略位域上的 "&"|
|[编译器错误 C2105](compiler-error-c2105.md)|"*operator*" 需要左值|
|[编译器错误 C2106](compiler-error-c2106.md)|"*operator*"：左操作数必须为左值|
|[编译器错误 C2107](compiler-error-c2107.md)|非法索引，不允许间接寻址|
|[编译器错误 C2108](compiler-error-c2108.md)|下标不是整型|
|[编译器错误 C2109](compiler-error-c2109.md)|下标要求数组或指针类型|
|[编译器错误 C2110](compiler-error-c2110.md)|"+"：不能添加两个指针|
|[编译器错误 C2111](compiler-error-c2111.md)|"+"：指针加法要求整型操作数|
|[编译器错误 C2112](compiler-error-c2112.md)|"-"：指针减法要求整型或指针操作数|
|[编译器错误 C2113](compiler-error-c2113.md)|"-"：指针只能从另一个指针进行减法运算|
|[编译器错误 C2114](compiler-error-c2114.md)|"*operator*"：左侧指针;需要右侧的整数值|
|[编译器错误 C2115](compiler-error-c2115.md)|"*operator*"：不兼容的类型|
|[编译器错误 C2116](compiler-error-c2116.md)|函数参数列表有差异|
|[编译器错误 C2117](compiler-error-c2117.md)|"*identifier*"：数组界限溢出|
|[编译器错误 C2118](compiler-error-c2118.md)|负下标|
|编译器错误 C2119|"*identifier*"：无法从空的初始值设定项推导 "*type*" 的类型|
|[编译器错误 C2120](compiler-error-c2120.md)|"void" 对于所有类型都非法|
|[编译器错误 C2121](compiler-error-c2121.md)|"#"：无效字符：可能是宏扩展的结果|
|[编译器错误 C2122](compiler-error-c2122.md)|"*identifier*"：名称列表中的原型参数非法|
|编译器错误 C2123|"*identifier*"：别名模板无法显式或部分专用化|
|[编译器错误 C2124](compiler-error-c2124.md)|被零除或对零求模|
|编译器错误 C2125|"constexpr" 与 "*token*" 不兼容|
|编译器错误 C2126|"*identifier*" 不能用 "constexpr" 说明符声明|
|编译器错误 C2127|"*identifier*"：非法初始化了包含非常量表达式的 "constexpr" 实体|
|[编译器错误 C2128](compiler-error-c2128.md)|"*function*"： alloc_text/same_seg 仅适用于带 C 链接的函数|
|[编译器错误 C2129](compiler-error-c2129.md)|已声明但未定义静态函数 "*identifier*"|
|[编译器错误 C2130](compiler-error-c2130.md)|#line 应输入包含文件名的字符串，却找到 "*token*"|
|[编译器错误 C2131](compiler-error-c2131.md)|表达式的计算结果不是常数|
|[编译器错误 C2132](compiler-error-c2132.md)|语法错误：意外的标识符|
|[编译器错误 C2133](compiler-error-c2133.md)|"*identifier*"：未知的大小|
|[编译器错误 C2134](compiler-error-c2134.md)|"*function*"：调用不会生成常数表达式|
|[编译器错误 C2135](compiler-error-c2135.md)|"*operator*"：非法的位域操作|
|编译器错误 C2136|不允许创作 API 协定|
|[编译器错误 C2137](compiler-error-c2137.md)|空字符常量|
|[编译器错误 C2138](compiler-error-c2138.md)|定义没有任何成员的枚举是非法的|
|[编译器错误 C2139](compiler-error-c2139.md)|"*class*"：未定义的类不允许作为编译器内部类型特征 "*特征*" 的参数|
|[编译器错误 C2140](compiler-error-c2140.md)|"*type*"：依赖于泛型类型参数的类型不允许作为编译器内部类型特征 "*特征*" 的参数|
|[编译器错误 C2141](compiler-error-c2141.md)|数组大小溢出|
|[编译器错误 C2142](compiler-error-c2142.md)|函数声明不同，仅在其中一个中指定了变量参数|
|[编译器错误 C2143](compiler-error-c2143.md)|语法错误： "*token2*" 之前缺少 "*token1*"|
|[编译器错误 C2144](compiler-error-c2144.md)|语法错误： "*type*" 前面应是 "*token2*"|
|[编译器错误 C2145](compiler-error-c2145.md)|语法错误：标识符的前面缺少 "*token*"|
|[编译器错误 C2146](compiler-error-c2146.md)|语法错误：标识符 "*identifier*" 之前缺少 "*token*"|
|[编译器错误 C2147](compiler-error-c2147.md)|语法错误： "*token*" 是新的关键字|
|[编译器错误 C2148](compiler-error-c2148.md)|数组的总大小不得超过 0x *值* 字节|
|[编译器错误 C2149](compiler-error-c2149.md)|"*identifier*"：已命名位域不能具有零宽度|
|[编译器错误 C2150](compiler-error-c2150.md)|"*identifier*"：位域必须有 "int"、"带符号的 int" 或 "无符号 int" 类型|
|[编译器错误 C2151](compiler-error-c2151.md)|多语言特性|
|[编译器错误 C2152](compiler-error-c2152.md)|"*identifier*"：指向具有不同特性的函数的指针|
|[编译器错误 C2153](compiler-error-c2153.md)|整数文本必须至少有一个数字|
|[编译器错误 C2154](compiler-error-c2154.md)|"*type*"：只有枚举类型才允许作为编译器内部类型特征 "*特征*" 的参数|
|[编译器错误 C2155](compiler-error-c2155.md)|"？"：左操作数无效，应为算术类型或指针类型|
|[编译器错误 C2156](compiler-error-c2156.md)|杂注必须在函数的外部|
|[编译器错误 C2157](compiler-error-c2157.md)|"*identifier*"：必须在用于杂注列表之前声明|
|[编译器错误 C2158](compiler-error-c2158.md)|"*type*"：目前只有本机非模板类型才支持 #pragma make_public 指令|
|[编译器错误 C2159](compiler-error-c2159.md)|指定了一个以上的存储类|
|[编译器错误 C2160](compiler-error-c2160.md)|“##”不能在宏定义的开始处出现|
|[编译器错误 C2161](compiler-error-c2161.md)|“##”不能在宏定义的结尾处出现|
|[编译器错误 C2162](compiler-error-c2162.md)|应输入宏形参|
|[编译器错误 C2163](compiler-error-c2163.md)|"*function*"：不可用作内部函数|
|[编译器错误 C2164](compiler-error-c2164.md)|"*function*"：未声明的内部函数|
|[编译器错误 C2165](compiler-error-c2165.md)|"*修饰符*"：不能修改指向数据的指针|
|[编译器错误 C2166](compiler-error-c2166.md)|左值指定 const 对象|
|[编译器错误 C2167](compiler-error-c2167.md)|"*function*"：内部函数的实参太多|
|[编译器错误 C2168](compiler-error-c2168.md)|"*function*"：内部函数的实参太少|
|[编译器错误 C2169](compiler-error-c2169.md)|"*function*"：内部函数，不能定义|
|[编译器错误 C2170](compiler-error-c2170.md)|"*identifier*"：未声明为函数，不能是内部函数|
|[编译器错误 C2171](compiler-error-c2171.md)|"*operator*"： "*type*" 类型的操作数非法|
|[编译器错误 C2172](compiler-error-c2172.md)|"*function*"：实参不是指针：参数 *号*|
|[编译器错误 C2173](compiler-error-c2173.md)|"*function*"：实参不是指针：参数 *号*，参数列表 *号*|
|[编译器错误 C2174](compiler-error-c2174.md)|"*function*"：实参具有 "void" 类型：参数 *号*，参数列表 *号*|
|[编译器错误 C2175](compiler-error-c2175.md)|"*locale*"：无效的区域设置|
|编译器错误 C2176|返回语句不能出现在与构造函数关联的函数 try 块的处理程序中|
|[编译器错误 C2177](compiler-error-c2177.md)|常量太大|
|[编译器错误 C2178](compiler-error-c2178.md)|"*identifier*" 不能用 "*说明符*" 说明符进行声明|
|[编译器错误 C2179](compiler-error-c2179.md)|"*type*"：特性参数不能使用类型参数|
|[编译器错误 C2180](compiler-error-c2180.md)|控制表达式的类型为 "*type*"|
|[编译器错误 C2181](compiler-error-c2181.md)|没有匹配 if 的非法 else|
|[编译器错误 C2182](compiler-error-c2182.md)|"*identifier*"：非法使用 "void" 类型|
|[编译器错误 C2183](compiler-error-c2183.md)|语法错误：翻译单元为空|
|[编译器错误 C2184](compiler-error-c2184.md)|"*type*"： __except 表达式的非法类型|
|[编译器错误 C2185](compiler-error-c2185.md)|"*identifier*"：非法的分配|
|[编译器错误 C2186](compiler-error-c2186.md)|"*operator*"： "void" 类型的操作数非法|
|编译器错误 C2187|语法错误：此处意外出现 "*token*"|
|[编译器错误 C2188](compiler-error-c2188.md)|"*number*"：对于宽字符来说太大|
|编译器错误 C2189|"alignas" 特性不能应用于位域、函数参数、异常声明或用 "register" 存储类声明的变量|
|[编译器错误 C2190](compiler-error-c2190.md)|第一个参数列表比第二个长|
|[编译器错误 C2191](compiler-error-c2191.md)|第二个参数列表比第一个长|
|[编译器错误 C2192](compiler-error-c2192.md)|参数 "*number*" 声明不同|
|[编译器错误 C2193](compiler-error-c2193.md)|"*identifier*"：已在段中|
|[编译器错误 C2194](compiler-error-c2194.md)|"*identifier*"：是一个文本段|
|[编译器错误 C2195](compiler-error-c2195.md)|"*identifier*"：是一个数据段|
|[编译器错误 C2196](compiler-error-c2196.md)|case 值 "*value*" 已使用|
|[编译器错误 C2197](compiler-error-c2197.md)|"*function*"：用于调用的参数太多|
|[编译器错误 C2198](compiler-error-c2198.md)|"*function*"：用于调用的参数太少|
|[编译器错误 C2199](compiler-error-c2199.md)|语法错误：在全局范围内找到 "*标识符* (" (是否打算使用声明？ ) |

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
