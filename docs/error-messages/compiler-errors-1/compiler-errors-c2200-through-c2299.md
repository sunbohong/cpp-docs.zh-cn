---
description: 了解有关以下内容的详细信息：编译器错误 C2200 到 C2299
title: 编译器错误 C2200 - C2299
ms.date: 04/21/2019
f1_keywords:
- C2202
- C2209
- C2210
- C2211
- C2214
- C2215
- C2221
- C2225
- C2230
- C2235
- C2237
- C2239
- C2240
- C2257
- C2260
- C2263
- C2265
- C2269
- C2278
- C2281
- C2282
- C2288
- C2291
- C2294
helpviewer_keywords:
- C2202
- C2209
- C2210
- C2211
- C2214
- C2215
- C2221
- C2225
- C2230
- C2235
- C2237
- C2239
- C2240
- C2257
- C2260
- C2263
- C2265
- C2269
- C2278
- C2281
- C2282
- C2288
- C2291
- C2294
ms.assetid: 9b36d11b-9510-4390-96f1-0c9235124d14
ms.openlocfilehash: 6853f9846477468a82fa4cc007d45eab2c1916b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318957"
---
# <a name="compiler-errors-c2200-through-c2299"></a>编译器错误 C2200 - C2299

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|[编译器错误 C2200](compiler-error-c2200.md)|"*function*"：函数已被定义|
|[编译器错误 C2201](compiler-error-c2201.md)|"*identifier*"：必须具有外部链接才能导出/导入|
|编译器错误 C2202|"*function*"：并非所有的控件路径都返回值|
|[编译器错误 C2203](compiler-error-c2203.md)|删除运算符不能指定数组的边界|
|[编译器错误 C2204](compiler-error-c2204.md)|"*type*"：括号中找到的类型定义|
|[编译器错误 C2205](compiler-error-c2205.md)|"*identifier*"：不能用块范围初始化 extern 变量|
|[编译器错误 C2206](compiler-error-c2206.md)|"*function*"： typedef 不能用于函数定义|
|[编译器错误 C2207](compiler-error-c2207.md)|"*member*"：类模板的成员无法获取函数类型|
|[编译器错误 C2208](compiler-error-c2208.md)|"*type*"：没有使用此类型定义的成员|
|编译器错误 C2209|"*identifier*"：不能在构造函数声明中使用别名|
|编译器错误 C2210|"*identifier*"：包扩展不能用作别名模板中非打包参数的自变量|
|编译器错误 C2211|使用公共析构函数从 ref 类派生的 ref 类中的非虚拟析构函数必须也是公共的|
|[编译器错误 C2212](compiler-error-c2212.md)|"*identifier*"： __based 不可用于指向函数的指针|
|[编译器错误 C2213](compiler-error-c2213.md)|"*identifier*"：非法的参数 __based|
|编译器错误 C2214|基于 "void" 的指针要求使用： >|
|编译器错误 C2215|"*关键字*" 不能与 "/ARCH： SSE" 一起使用|
|[编译器错误 C2216](compiler-error-c2216.md)|"*keyword1*" 不能与 "*keyword2*" 一起使用|
|[编译器错误 C2217](compiler-error-c2217.md)|"*attribute1*" 需要 "*attribute2*"|
|[编译器错误 C2218](compiler-error-c2218.md)|"*calltype*" 不能与 "/ARCH： IA32" 一起使用|
|[编译器错误 C2219](compiler-error-c2219.md)|语法错误：类型限定符必须位于 "*" 之后|
|[编译器错误 C2220](compiler-error-c2220.md)|警告被视为错误-没有生成 "文件 *类型*" 文件|
|编译器错误 C2221|已过时。|
|[编译器错误 C2222](compiler-error-c2222.md)|意外类型 "*type*"：应为基类或成员|
|[编译器错误 C2223](compiler-error-c2223.md)|"->*标识符*" 的左侧必须指向结构/联合|
|[编译器错误 C2224](compiler-error-c2224.md)|"。*标识符*"必须具有结构/联合类型|
|编译器错误 C2225|已过时。|
|[编译器错误 C2226](compiler-error-c2226.md)|语法错误：意外的类型 "*type*"|
|[编译器错误 C2227](compiler-error-c2227.md)|"->*标识符*" 的左侧必须指向类/结构/联合/泛型类型|
|[编译器错误 C2228](compiler-error-c2228.md)|"。*标识符*"必须有类/结构/联合|
|[编译器错误 C2229](compiler-error-c2229.md)|类/结构/联合 "*type*" 具有非法的零大小的数组|
|编译器错误 C2230|找不到模块 "*name*"|
|[编译器错误 C2231](compiler-error-c2231.md)|'.*标识符*"：左操作数指向" class/struct/union "，使用"-> "|
|[编译器错误 C2232](compiler-error-c2232.md)|"->*标识符*"：左操作数具有 "class/struct/union" 类型，请使用 "."|
|[编译器错误 C2233](compiler-error-c2233.md)|"*identifier*"：包含大小为零的数组的对象数组是非法的|
|[编译器错误 C2234](compiler-error-c2234.md)|*标识符*"：引用数组是非法的|
|编译器错误 C2235|已过时。|
|[编译器错误 C2236](compiler-error-c2236.md)|意外的标记 "*token*"。 你是否忘了“;”？|
|编译器错误 C2237|多个模块声明|
|[编译器错误 C2238](compiler-error-c2238.md)|) "*token*" 之前出现意外标记 (|
|编译器错误 C2239|"*function*"：尝试删除 __declspec (dllexport) 函数|
|编译器错误 C2240|已过时。|
|[编译器错误 C2241](compiler-error-c2241.md)|"*identifier*"：成员访问受限制|
|[编译器错误 C2242](compiler-error-c2242.md)|typedef 名不能位于类/结构/联合之后|
|[编译器错误 C2243](compiler-error-c2243.md)|"*conversion_type*"：从 "*type1*" 到 "*type2*" 的转换存在，但不可访问|
|[编译器错误 C2244](compiler-error-c2244.md)|"*identifier*"：无法将函数定义与现有的声明匹配|
|[编译器错误 C2245](compiler-error-c2245.md)|将不存在的成员函数 "*function*" 指定为 friend (成员函数签名与任何重载都不匹配) |
|[编译器错误 C2246](compiler-error-c2246.md)|"*identifier*"：本地定义的类中的非法静态数据成员|
|[编译器错误 C2247](compiler-error-c2247.md)|"*class1*" 使用 "*说明符*" 从 "*class2*" 继承，因此无法访问 "*identifier*"|
|[编译器错误 C2248](compiler-error-c2248.md)|"*identifier*"：无法访问类 "*class*" 中声明的 *可访问性**成员*|
|[编译器错误 C2249](compiler-error-c2249.md)|"*identifier*"：不能访问在虚拟基 "*class*" 中声明的 *可访问性**成员* 的路径|
|[编译器错误 C2250](compiler-error-c2250.md)|"*identifier*"：不明确的 *类*：：*member*"的继承|
|[编译器错误 C2251](compiler-error-c2251.md)|命名空间 "*namespace*" 不具有成员 "*identifier*"-您是否表示 "*member*"？|
|[编译器错误 C2252](compiler-error-c2252.md)|模板的显式实例化只能出现在命名空间范围内|
|[编译器错误 C2253](compiler-error-c2253.md)|"*function*"：纯说明符或抽象重写说明符只允许在虚函数上使用|
|[编译器错误 C2254](compiler-error-c2254.md)|"*function*"：友元函数上不允许使用纯说明符或抽象重写说明符|
|[编译器错误 C2255](compiler-error-c2255.md)|"*element*"：不允许位于类定义之外|
|[编译器错误 C2256](compiler-error-c2256.md)|在 "*function*" 上非法使用友元说明符|
|编译器错误 C2257|"*说明符*"：尾随返回类型中不允许使用说明符|
|[编译器错误 C2258](compiler-error-c2258.md)|非法的纯语法，必须为“= 0”|
|[编译器错误 C2259](compiler-error-c2259.md)|"*class*"：不能实例化抽象类|
|编译器错误 C2260|"*说明符*"：无效的 InternalsVisibleToAttribute 友元程序集说明符|
|[编译器错误 C2261](compiler-error-c2261.md)|"*string*"：程序集引用无效且无法解析|
|[编译器错误 C2262](compiler-error-c2262.md)|"*说明符*"：不能为 InternalsVisibleTo 声明指定版本、区域性或处理器体系结构|
|编译器错误 C2263|已过时。|
|[编译器错误 C2264](compiler-error-c2264.md)|"*function*"：函数定义或声明中有错误;未调用函数|
|编译器错误 C2265|已过时。|
|[编译器错误 C2266](compiler-error-c2266.md)|"*identifier*"：对非常量绑定数组的引用非法|
|[编译器错误 C2267](compiler-error-c2267.md)|"*function*"：具有块范围的静态函数是非法的|
|[编译器错误 C2268](compiler-error-c2268.md)|"*function*" 是编译器预定义的库帮助器。 /GL 不支持库帮助程序;在不/GL 的情况下编译对象文件 "*filename*"|
|编译器错误 C2269|无法创建指向限定函数类型的指针或引用 (需要指向成员的指针) |
|[编译器错误 C2270](compiler-error-c2270.md)|"*function*"：非成员函数上不允许使用修饰符|
|[编译器错误 C2271](compiler-error-c2271.md)|"*function*"： new/delete 不能有形式表修饰符|
|[编译器错误 C2272](compiler-error-c2272.md)|"*function*"：静态成员函数上不允许使用修饰符|
|[编译器错误 C2273](compiler-error-c2273.md)|"*type*"： "->" 运算符右侧的非法|
|[编译器错误 C2274](compiler-error-c2274.md)|"*type*"： "." 运算符右侧的非法|
|[编译器错误 C2275](compiler-error-c2275.md)|"*type*"：非法将此类型用作表达式|
|[编译器错误 C2276](compiler-error-c2276.md)|"*operator*"：绑定成员函数表达式上的非法操作|
|[编译器错误 C2277](compiler-error-c2277.md)|"*function*"：无法获取此成员函数的地址|
|编译器错误 C2278|已过时。|
|[编译器错误 C2279](compiler-error-c2279.md)|异常规范不能出现在 typedef 声明中|
|[编译器错误 C2280](compiler-error-c2280.md)|"*class*：：*function*"：正在尝试引用已删除的函数|
|编译器错误 C2281|"*class*：：*function*"：只能在第一个声明中删除函数|
|编译器错误 C2282|"*function1*" 不能重写 "*function2*"|
|[编译器错误 C2283](compiler-error-c2283.md)|"*标识符*"：未命名的类/结构上不允许使用纯说明符或抽象重写说明符|
|编译器错误 C2284|"*function*"：内部函数的非法参数，参数 *号*|
|[编译器错误 C2285](compiler-error-c2285.md)|指向成员表示形式的指针已确定-已忽略杂注|
|[编译器错误 C2286](compiler-error-c2286.md)|指向 "*identifier*" 表示形式成员的指针已设置为 *继承* -声明已忽略|
|[编译器错误 C2287](compiler-error-c2287.md)|"*identifier*"：继承表示形式： "*inheritiance*" 的一般不如必需的 "*继承*"|
|编译器错误 C2288|已过时。|
|[编译器错误 C2289](compiler-error-c2289.md)|多次使用同一类型限定符|
|[编译器错误 C2290](compiler-error-c2290.md)|C + + "asm" 语法被忽略。 使用__asm。|
|编译器错误 C2291|无法导出匿名命名空间。|
|[编译器错误 C2292](compiler-error-c2292.md)|"*identifier*"：最佳 case 继承表示形式： *inheritance1*"已声明，但需要"*inheritance2*"|
|[编译器错误 C2293](compiler-error-c2293.md)|"*identifier*"：将成员变量作为 __based 说明符是非法的|
|编译器错误 C2294|无法导出符号 "*identifier*"，因为它具有内部链接|
|[编译器错误 C2295](compiler-error-c2295.md)|转义的 "*character*"：在宏定义中非法|
|[编译器错误 C2296](compiler-error-c2296.md)|"*operator*"：非法，左操作数的类型为 "*type*"|
|[编译器错误 C2297](compiler-error-c2297.md)|"*operator*"：非法，右操作数的类型为 "*type*"|
|[编译器错误 C2298](compiler-error-c2298.md)|缺少对成员函数的界限指针的调用|
|[编译器错误 C2299](compiler-error-c2299.md)|"*function*"：行为更改：显式专用化不能是复制构造函数或复制赋值运算符|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
