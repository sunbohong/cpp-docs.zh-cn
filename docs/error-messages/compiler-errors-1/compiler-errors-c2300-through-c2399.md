---
description: 了解有关以下内容的详细信息：编译器错误 C2300 到 C2399
title: 编译器错误 C2300 - C2399
ms.date: 04/21/2019
f1_keywords:
- C2303
- C2304
- C2305
- C2306
- C2314
- C2321
- C2323
- C2328
- C2329
- C2330
- C2331
- C2335
- C2336
- C2339
- C2340
- C2342
- C2343
- C2347
- C2354
- C2358
- C2359
- C2363
- C2366
- C2367
- C2398
- C2399
helpviewer_keywords:
- C2303
- C2304
- C2305
- C2306
- C2314
- C2321
- C2323
- C2328
- C2329
- C2330
- C2331
- C2335
- C2336
- C2339
- C2340
- C2342
- C2343
- C2347
- C2354
- C2358
- C2359
- C2363
- C2366
- C2367
- C2398
- C2399
ms.assetid: 07ca45b5-b2f0-4049-837b-40a7a3caed88
ms.openlocfilehash: 95763db7f8be0c0918d2f15f515f327325c386dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318944"
---
# <a name="compiler-errors-c2300-through-c2399"></a>编译器错误 C2300 - C2399

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|[编译器错误 C2300](compiler-error-c2300.md)|"*class*"：类不具有名为 "~*class*" 的析构函数|
|[编译器错误 C2301](compiler-error-c2301.md)|"->~*identifier*" 的左侧必须指向类/结构/联合|
|[编译器错误 C2302](compiler-error-c2302.md)|". ~*identifier*" 的左边必须有类/结构/联合类型|
|编译器错误 C2303|无法在协同程序中使用结构化异常处理|
|编译器错误 C2304|在 catch 块内不能使用 "*关键字*"|
|编译器错误 C2305|"*file*" 不包含此模块的调试信息|
|编译器错误 C2306|"*file*" 不包含此模块的最新调试信息|
|[编译器错误 C2307](compiler-error-c2307.md)|如果启用了增量编译，则必须将杂注 *指令* 移出函数之外|
|[编译器错误 C2308](compiler-error-c2308.md)|串联不匹配的字符串|
|[编译器错误 C2309](compiler-error-c2309.md)|catch 处理程序需要带括号的异常声明|
|[编译器错误 C2310](compiler-error-c2310.md)|catch 处理程序必须指定一种类型|
|[编译器错误 C2311](compiler-error-c2311.md)|"*type*"：由 "..." 捕获行 *号*|
|[编译器错误 C2312](compiler-error-c2312.md)|"*type1*"：由 "*type2*" 在行 *号* 上捕获|
|[编译器错误 C2313](compiler-error-c2313.md)|"*type1*"：由引用 ( "*type2*" 捕获行 *号* 上 ) |
|编译器错误 C2314|关键字 "*keyword1*" 已弃用：请改用 "*keyword2*"|
|[编译器错误 C2315](compiler-error-c2315.md)|"*type1*"：引用由 "*type2*" 在行 *号* 上捕获|
|[编译器错误 C2316](compiler-error-c2316.md)|"*type*"：无法捕获，因为析构函数和/或复制构造函数不可访问或已被删除|
|[编译器错误 C2317](compiler-error-c2317.md)|在行 "*number*" 上开始的 "try" 块没有 catch 处理程序|
|[编译器错误 C2318](compiler-error-c2318.md)|没有与该 catch 处理程序关联的 Try 块|
|[编译器错误 C2319](compiler-error-c2319.md)|“try/catch”后面必须有复合语句。 缺少“{”|
|[编译器错误 C2320](compiler-error-c2320.md)|应在访问说明符 "*说明符*" 后面输入 "："|
|编译器错误 C2321|"*identifier*" 是关键字，不能在此上下文中使用|
|[编译器错误 C2322](compiler-error-c2322.md)|"*identifier*"： dllimport "*identifier*" 的地址不是静态的|
|编译器错误 C2323|"*identifier*"：非成员运算符 new 或 delete 函数不能声明为静态或非全局命名空间中的命名空间|
|[编译器错误 C2324](compiler-error-c2324.md)|"*identifier*"： "：： ~" 的右边意外|
|[编译器错误 C2325](compiler-error-c2325.md)|"*type1*"： "->~" 的右侧意外类型：应为 "*type2*"|
|[编译器错误 C2326](compiler-error-c2326.md)|"*声明符*"：函数无法访问 "*identifier*"|
|[编译器错误 C2327](compiler-error-c2327.md)|"*identifier*"：不是类型名称、静态或枚举器|
|编译器错误 C2328|"*关键字*"：尚不支持关键字|
|编译器错误 C2329|"*identifier*"： __ptr64 不可用于指向函数的指针|
|编译器错误 C2330|"implementation_key ( ) " 仅在通过 #pragma start_map_region/stop_map_region 界定的区域中有效|
|编译器错误 C2331|对 "*identifier*" 的访问现定义为 "*accessibility1*"，以前它被定义为 "*accessibility2*"|
|[编译器错误 C2332](compiler-error-c2332.md)|"*typedef*"：缺少标记名称|
|[编译器错误 C2333](compiler-error-c2333.md)|"*function*"：函数声明中有错误;跳过函数体|
|[编译器错误 C2334](compiler-error-c2334.md)|) "*token*" 之前出现意外标记 (跳过明显的函数体|
|编译器错误 C2335|"*identifier*"：函数参数列表中不能引入类型|
|编译器错误 C2336|"*type*"：非法类型|
|[编译器错误 C2337](compiler-error-c2337.md)|"*attribute*"：找不到属性|
|[编译器错误 C2338](compiler-error-c2338.md)|*来自外部提供程序的 (错误消息)*|
|编译器错误 C2339|"*identifier*"：嵌入的 IDL 中的类型非法|
|编译器错误 C2340|"*identifier*"： "static" 只能在类定义中使用|
|[编译器错误 C2341](compiler-error-c2341.md)|"*section*"：必须使用 #pragma data_seg、code_seg 或部分定义段，然后才能使用|
|编译器错误 C2342|语法错误：类型限定符冲突|
|编译器错误 C2343|"*section*"：节特性冲突|
|[编译器错误 C2344](compiler-error-c2344.md)|对齐 (*号*) ：对齐必须是2的幂|
|[编译器错误 C2345](compiler-error-c2345.md)|对齐 (*号*) ：非法的对齐值|
|[编译器错误 C2346](compiler-error-c2346.md)|"*function*" 不能编译为本机： "*释义*"|
|编译器错误 C2347|已过时。|
|[编译器错误 C2348](compiler-error-c2348.md)|"*type*"：不是 C 样式聚合，无法在嵌入的 IDL 中导出|
|[编译器错误 C2349](compiler-error-c2349.md)|"*function*" 不能编译为托管： "*释义*";使用 #pragma 非托管|
|[编译器错误 C2350](compiler-error-c2350.md)|"*identifier*" 不是静态成员|
|[编译器错误 C2351](compiler-error-c2351.md)|过时的 c + + 构造函数初始化语法|
|[编译器错误 C2352](compiler-error-c2352.md)|"*identifier*"：非静态成员函数的非法调用|
|[编译器错误 C2353](compiler-error-c2353.md)|不允许使用异常规范|
|编译器错误 C2354|已过时。|
|[编译器错误 C2355](compiler-error-c2355.md)|"this"：只能在非静态成员函数或非静态数据成员初始值设定项内引用|
|[编译器错误 C2356](compiler-error-c2356.md)|初始化段在翻译单元期间不能更改|
|[编译器错误 C2357](compiler-error-c2357.md)|"*identifier*"：必须是 "*type*" 类型的函数|
|编译器错误 C2358|"*identifier*"：不能在类定义的外部定义静态属性|
|编译器错误 C2359|已过时。|
|[编译器错误 C2360](compiler-error-c2360.md)|"*identifier*" 的初始化被 "case" 标签跳过|
|[编译器错误 C2361](compiler-error-c2361.md)|"default" 标签跳过 "*identifier*" 的初始化|
|[编译器错误 C2362](compiler-error-c2362.md)|"goto *label*" 跳过了 "*identifier*" 的初始化|
|编译器错误 C2363|编译器内部数值限制函数需要字符串文本参数|
|[编译器错误 C2364](compiler-error-c2364.md)|"*type*"：自定义特性的非法类型|
|[编译器错误 C2365](compiler-error-c2365.md)|"*member1*"：重定义;上一个定义为 "*member2*"|
|编译器错误 C2366|"*identifier*"：重定义;不同 implementation_key 说明符|
|编译器错误 C2367|已过时。|
|[编译器错误 C2368](compiler-error-c2368.md)|"*identifier*"：重定义;不同的分配说明符|
|[编译器错误 C2369](compiler-error-c2369.md)|"*identifier*"：重定义;不同的下标|
|[编译器错误 C2370](compiler-error-c2370.md)|"*identifier*"：重定义;不同的存储类|
|[编译器错误 C2371](compiler-error-c2371.md)|"*identifier*"：重定义;不同的基本类型|
|[编译器错误 C2372](compiler-error-c2372.md)|"*identifier*"：重定义;不同类型的间接寻址|
|[编译器错误 C2373](compiler-error-c2373.md)|"*identifier*"：重定义;不同的类型修饰符|
|[编译器错误 C2374](compiler-error-c2374.md)|"*identifier*"：重定义;多次初始化|
|[编译器错误 C2375](compiler-error-c2375.md)|"*identifier*"：重定义;不同的链接|
|[编译器错误 C2376](compiler-error-c2376.md)|"*identifier*"：重定义;基于不同的分配|
|[编译器错误 C2377](compiler-error-c2377.md)|"*identifier*"：重定义;typedef 不能与任何其他符号重载|
|[编译器错误 C2378](compiler-error-c2378.md)|"*identifier*"：重定义;符号不能使用 typedef 重载|
|[编译器错误 C2379](compiler-error-c2379.md)|提升后，形参 *号* 具有不同的类型|
|[编译器错误 C2380](compiler-error-c2380.md)|键入 (s) 前面的 "*identifier*" (构造函数（具有返回类型）或当前类名称的非法重定义？ ) |
|[编译器错误 C2381](compiler-error-c2381.md)|"*identifier*"：重定义;"__declspec (noreturn) " 或 "[[noreturn]]" 不同|
|[编译器错误 C2382](compiler-error-c2382.md)|"*identifier*"：重定义;不同的异常规范|
|[编译器错误 C2383](compiler-error-c2383.md)|"*identifier*"：此符号上不允许使用默认参数|
|[编译器错误 C2384](compiler-error-c2384.md)|"*member*"：不能将 thread_local 或 __declspec (线程) 应用于托管的/WinRT 类的成员|
|[编译器错误 C2385](compiler-error-c2385.md)|对 "*member*" 的访问不明确|
|[编译器错误 C2386](compiler-error-c2386.md)|"*identifier*"：当前范围内已存在具有此名称的符号|
|[编译器错误 C2387](compiler-error-c2387.md)|"*identifier*"：不明确的基类|
|[编译器错误 C2388](compiler-error-c2388.md)|"*identifier*"：不能同时使用 __declspec (appdomain) 和 __declspec (进程声明符号) |
|[编译器错误 C2389](compiler-error-c2389.md)|"*operator*"：非法的操作数 "nullptr"|
|[编译器错误 C2390](compiler-error-c2390.md)|"*identifier*"：不正确的存储类 "*说明符*"|
|[编译器错误 C2391](compiler-error-c2391.md)|"*identifier*"： "friend" 不能在类型定义过程中使用|
|[编译器错误 C2392](compiler-error-c2392.md)|"*member1*"：托管/WinRT 类型中不支持协变返回类型，否则将重写 "*member2*"|
|[编译器错误 C2393](compiler-error-c2393.md)|"*symbol*"：不能在段 "*segment*" 中分配每个 appdomain 的符号|
|[编译器错误 C2394](compiler-error-c2394.md)|"*type*：： operator *Operator*"： CLR/WinRT 运算符无效。 至少一个参数必须是以下类型： "t ^"、"t ^%"、"t ^&"，其中 T = "*type*"|
|[编译器错误 C2395](compiler-error-c2395.md)|"*type*：： operator *Operator*"： CLR/WinRT 运算符无效。 至少一个参数必须是以下类型： "t"、"t%"、"& t"、"t ^"、"t ^%"、"t ^&"，其中 T = "*type*"|
|[编译器错误 C2396](compiler-error-c2396.md)|"*type1*：： operator *Type2*"： CLR/WinRT 用户定义的转换函数无效。 必须转换为： t ^ "，不是 ^%"，不是 ^& "，其中 T ="*type1*"|
|[编译器错误 C2397](compiler-error-c2397.md)|从 "*type1*" 转换到 "*type2*" 需要收缩转换|
|编译器错误 C2398|元素 "*number*"：从 "*type1*" 转换到 "*type2*" 需要收缩转换|
|编译器错误 C2399|已过时。|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
