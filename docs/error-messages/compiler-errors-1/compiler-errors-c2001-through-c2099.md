---
description: 了解有关以下内容的详细信息：编译器错误 C2000 到 C2099
title: 编译器错误 C2000 - C2099
ms.date: 04/21/2019
f1_keywords:
- C2000
- C2016
- C2023
- C2024
- C2025
- C2029
- C2031
- C2035
- C2037
- C2038
- C2049
- C2068
- C2076
- C2080
- C2096
- C2098
helpviewer_keywords:
- C2000
- C2016
- C2023
- C2024
- C2025
- C2029
- C2031
- C2035
- C2037
- C2038
- C2049
- C2068
- C2076
- C2080
- C2096
- C2098
ms.assetid: d99a19eb-eeeb-4181-9b33-9cbe4459767b
ms.openlocfilehash: 4bdd76018c348e4d5f09c8a7a2e92395fd2faec8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319009"
---
# <a name="compiler-errors-c2000-through-c2099"></a>编译器错误 C2000 - C2099

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|编译器错误 C2000|未知错误，请选择 Visual C++ "帮助" 菜单上的 "技术支持" 命令，或打开技术支持帮助文件以获取详细信息|
|[编译器错误 C2001](compiler-error-c2001.md)|常量中有换行符|
|[编译器错误 C2002](compiler-error-c2002.md)|宽字符常量无效|
|[编译器错误 C2003](compiler-error-c2003.md)|应输入 "defined id"|
|[编译器错误 C2004](compiler-error-c2004.md)|应输入“defined(id)”|
|[编译器错误 C2005](compiler-error-c2005.md)|#line 应为行号，却找到 "*token*"|
|[编译器错误 C2006](compiler-error-c2006.md)|"*指令*"：应输入文件名，却找到 "*token*"|
|[编译器错误 C2007](compiler-error-c2007.md)|#define 语法|
|[编译器错误 C2008](compiler-error-c2008.md)|"*character*"：宏定义中的意外|
|[编译器错误 C2009](compiler-error-c2009.md)|宏形式 "*identifier*" 重复使用|
|[编译器错误 C2010](compiler-error-c2010.md)|"*character*"：宏形参表中的意外|
|[编译器错误 C2011](compiler-error-c2011.md)|"*identifier*"： "*type*" 类型重定义|
|[编译器错误 C2012](compiler-error-c2012.md)|"<" 后缺少名称|
|[编译器错误 C2013](compiler-error-c2013.md)|缺少“>”|
|[编译器错误 C2014](compiler-error-c2014.md)|预处理器命令必须作为第一个非空白空间启动|
|[编译器错误 C2015](compiler-error-c2015.md)|常量中的字符太多|
|编译器错误 C2016|C 要求一个结构或联合至少有一个成员|
|[编译器错误 C2017](compiler-error-c2017.md)|非法的转义序列|
|[编译器错误 C2018](compiler-error-c2018.md)|未知字符 "0x *value*"|
|[编译器错误 C2019](compiler-error-c2019.md)|应输入预处理器指令，却找到 "*character*"|
|[编译器错误 C2020](compiler-error-c2020.md)|"*member*"： "*class*" 成员重定义|
|[编译器错误 C2021](compiler-error-c2021.md)|应输入指数值而非 "*character*"|
|[编译器错误 C2022](compiler-error-c2022.md)|"*number*"：字符太大|
|编译器错误 C2023|"*identifier*"：对齐 (*数字 1*) 不同于以前的声明 (*数字 2*) |
|编译器错误 C2024|"alignas" 特性仅适用于变量、数据成员和标记类型|
|编译器错误 C2025|二进制模块接口文件无效或已损坏： "*filename*"|
|[编译器错误 C2026](compiler-error-c2026.md)|字符串太大，已截断尾部字符|
|[编译器错误 C2027](compiler-error-c2027.md)|使用了未定义的类型 "*type*"|
|[编译器错误 C2028](compiler-error-c2028.md)|结构/联合成员必须在结构/联合中|
|编译器错误 C2029|"*token*" 的左侧指定了未定义的类/结构/接口 "*identifier*"|
|[编译器错误 C2030](compiler-error-c2030.md)|具有“protected private”可访问性的析构函数不能是声明为“sealed”的类的成员|
|编译器错误 C2031|此类型不允许具有 "*可访问* 性" 可访问性的虚拟析构函数|
|[编译器错误 C2032](compiler-error-c2032.md)|"*identifier*"：函数不能是结构/联合 "*type*" 的成员|
|[编译器错误 C2033](compiler-error-c2033.md)|"*identifier*"：位域不能有间接寻址|
|[编译器错误 C2034](compiler-error-c2034.md)|"*identifier*"：位域的类型对于位数太小|
|编译器错误 C2035|此类型不允许具有 "*可访问* 性" 可访问性的非虚拟析构函数|
|[编译器错误 C2036](compiler-error-c2036.md)|"*identifier*"：未知的大小|
|编译器错误 C2037|"*identifier*" 的左侧指定了未定义的结构/联合 "*type*"|
|编译器错误 C2038|std 命名空间不能内联|
|[编译器错误 C2039](compiler-error-c2039.md)|"*identifier1*"：不是 "*identifier2*" 的成员|
|[编译器错误 C2040](compiler-error-c2040.md)|"*operator*"： "*identifier1*" 在 "*identifier2*" 的间接级别不同|
|[编译器错误 C2041](compiler-error-c2041.md)|基 "*number*" 的非法数字 "*character*"|
|[编译器错误 C2042](compiler-error-c2042.md)|signed/unsigned 关键字互相排斥|
|[编译器错误 C2043](compiler-error-c2043.md)|非法 break|
|[编译器错误 C2044](compiler-error-c2044.md)|非法 continue|
|[编译器错误 C2045](compiler-error-c2045.md)|"*identifier*"：标签重定义|
|[编译器错误 C2046](compiler-error-c2046.md)|非法的 case|
|[编译器错误 C2047](compiler-error-c2047.md)|非法的 default|
|[编译器错误 C2048](compiler-error-c2048.md)|default 多于一个|
|编译器错误 C2049|"*identifier*"：不能将非内联命名空间重新打开为内联|
|[编译器错误 C2050](compiler-error-c2050.md)|switch 表达式不是整型|
|[编译器错误 C2051](compiler-error-c2051.md)|case 表达式不是常量|
|[编译器错误 C2052](compiler-error-c2052.md)|"*type*"：非法的 case 表达式类型|
|[编译器错误 C2053](compiler-error-c2053.md)|"*identifier*"：宽字符串不匹配|
|[编译器错误 C2054](compiler-error-c2054.md)|应输入 " (" 跟踪 "*identifier*"|
|[编译器错误 C2055](compiler-error-c2055.md)|应输入形参表，而不是类型列表|
|[编译器错误 C2056](compiler-error-c2056.md)|非法表达式|
|[编译器错误 C2057](compiler-error-c2057.md)|应输入常量表达式|
|[编译器错误 C2058](compiler-error-c2058.md)|常量表达式不是整型|
|[编译器错误 C2059](compiler-error-c2059.md)|语法错误： "*token*"|
|[编译器错误 C2060](compiler-error-c2060.md)|语法错误：找到文件结尾|
|[编译器错误 C2061](compiler-error-c2061.md)|语法错误：标识符 "*identifier*"|
|[编译器错误 C2062](compiler-error-c2062.md)|意外的类型 "*type*"|
|[编译器错误 C2063](compiler-error-c2063.md)|"*identifier*"：不是函数|
|[编译器错误 C2064](compiler-error-c2064.md)|字词的计算结果不是采用 *number* 参数的函数|
|[编译器错误 C2065](compiler-error-c2065.md)|"*identifier*"：未声明的标识符|
|[编译器错误 C2066](compiler-error-c2066.md)|强制转换到函数类型是非法的|
|[编译器错误 C2067](compiler-error-c2067.md)|转换到数组类型是非法的|
|编译器错误 C2068|非法使用重载函数。 缺少参数列表？|
|[编译器错误 C2069](compiler-error-c2069.md)|“void”项到非“void”项的转换|
|[编译器错误 C2070](compiler-error-c2070.md)|"*type*"：非法的 sizeof 操作数|
|[编译器错误 C2071](compiler-error-c2071.md)|"*identifier*"：非法的存储类|
|[编译器错误 C2072](compiler-error-c2072.md)|"*identifier*"：函数的初始化|
|[编译器错误 C2073](compiler-error-c2073.md)|"*identifier*"：部分初始化数组的元素必须有默认构造函数|
|[编译器错误 C2074](compiler-error-c2074.md)|"*identifier*"： "*type*" 初始化需要带括号的初始值设定项列表|
|[编译器错误 C2075](compiler-error-c2075.md)|"*identifier*"：数组初始化需要带括号的初始值设定项列表|
|编译器错误 C2076|无法在类型包含 "*type*" 的新表达式中使用带括号的初始值设定项列表|
|[编译器错误 C2077](compiler-error-c2077.md)|非标量字段初始值设定项 "*identifier*"|
|[编译器错误 C2078](compiler-error-c2078.md)|初始值设定项太多|
|[编译器错误 C2079](compiler-error-c2079.md)|"*identifier*" 使用未定义的结构/类/联合 "*type*"|
|编译器错误 C2080|"*identifier*"： "*type*" 的类型只能从单个初始值设定项表达式推导出|
|[编译器错误 C2081](compiler-error-c2081.md)|"*identifier*"：形参表中的名称非法|
|[编译器错误 C2082](compiler-error-c2082.md)|形参 "*identifier*" 的重定义|
|[编译器错误 C2083](compiler-error-c2083.md)|结构/联合比较非法|
|[编译器错误 C2084](compiler-error-c2084.md)|函数 "*identifier*" 已经有一个主体|
|[编译器错误 C2085](compiler-error-c2085.md)|"*identifier*"：不在形参表中|
|[编译器错误 C2086](compiler-error-c2086.md)|"*identifier*"：重定义|
|[编译器错误 C2087](compiler-error-c2087.md)|"*identifier*"：缺少下标|
|[编译器错误 C2088](compiler-error-c2088.md)|"*operator*"：结构/类/联合非法|
|[编译器错误 C2089](compiler-error-c2089.md)|"*identifier*"： "*type*" 太大|
|[编译器错误 C2090](compiler-error-c2090.md)|函数返回数组|
|[编译器错误 C2091](compiler-error-c2091.md)|函数返回函数|
|[编译器错误 C2092](compiler-error-c2092.md)|"*identifier*" 数组元素类型不能为函数|
|[编译器错误 C2093](compiler-error-c2093.md)|"*identifier1*"：无法使用自动变量 "*identifier2*" 的地址初始化|
|[编译器错误 C2094](compiler-error-c2094.md)|标签 "*identifier*" 未定义|
|[编译器错误 C2095](compiler-error-c2095.md)|"*function*"：实参具有 "void" 类型：参数 *号*|
|编译器错误 C2096|"*identifier*"：不能使用带括号的初始值设定项初始化数据成员|
|[编译器错误 C2097](compiler-error-c2097.md)|非法初始化|
|编译器错误 C2098|数据成员 "*identifier*" 后的意外标记|
|[编译器错误 C2099](compiler-error-c2099.md)|初始值设定项不是常量|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
