---
description: 了解有关以下内容的详细信息：编译器错误 C3000 到 C3099
title: 编译器错误 C3000 - C3099
ms.date: 04/21/2019
f1_keywords:
- C3051
- C3061
- C3064
- C3067
- C3074
- C3078
- C3079
- C3081
- C3082
- C3086
- C3088
- C3089
- C3090
- C3091
- C3092
- C3093
- C3098
helpviewer_keywords:
- C3051
- C3061
- C3064
- C3067
- C3074
- C3078
- C3079
- C3081
- C3082
- C3086
- C3088
- C3089
- C3090
- C3091
- C3092
- C3093
- C3098
ms.assetid: 01b7b9cb-b351-4b5a-8cb0-1fcddb08d2ab
ms.openlocfilehash: ce4e088a1d69da20cae87fd9b824ddef4769c8da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238695"
---
# <a name="compiler-errors-c3000-through-c3099"></a>编译器错误 C3000 - C3099

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|编译器错误 C3000|已过时。|
|[编译器错误 C3001](compiler-error-c3001.md)|"*message*"：应为 OpenMP 指令名称|
|[编译器错误 C3002](compiler-error-c3002.md)|"*name1* *name2*"：多个 OpenMP 指令名称|
|[编译器错误 C3003](compiler-error-c3003.md)|"*指令*"：在指令子句之后不允许使用 OpenMP 指令名称|
|[编译器错误 C3004](compiler-error-c3004.md)|"*子句*"： OpenMP "*指令*" 指令上的子句无效|
|[编译器错误 C3005](compiler-error-c3005.md)|"*message*"： OpenMP "*指令*" 指令上出现意外的标记|
|[编译器错误 C3006](compiler-error-c3006.md)|"*子句*"： OpenMP "*指令*" 指令上的子句缺少预期的参数|
|[编译器错误 C3007](compiler-error-c3007.md)|"*子句*"： OpenMP "*指令*" 指令上的子句没有采用参数|
|[编译器错误 C3008](compiler-error-c3008.md)|"*argument*"：在 OpenMP "*指令*" 指令上缺少关闭 ") " 的参数|
|[编译器错误 C3009](compiler-error-c3009.md)|"*label*"：不允许跳转到 OpenMP 结构化块中|
|[编译器错误 C3010](compiler-error-c3010.md)|"*label*"：不允许跳出 OpenMP 结构化块|
|[编译器错误 C3011](compiler-error-c3011.md)|并行区域内不允许直接使用内联程序集|
|[编译器错误 C3012](compiler-error-c3012.md)|"*function*"：并行区域内不允许直接使用内部函数|
|[编译器错误 C3013](compiler-error-c3013.md)|"*子句*"：子句在 OpenMP "*指令*" 指令上只能出现一次|
|[编译器错误 C3014](compiler-error-c3014.md)|OpenMP "*指令*" 指令后应为 for 循环|
|[编译器错误 C3015](compiler-error-c3015.md)|OpenMP“for”语句中的初始化格式不正确|
|[编译器错误 C3016](compiler-error-c3016.md)|"*identifier*"： OpenMP "for" 语句中的索引变量必须是有符号的整型|
|[编译器错误 C3017](compiler-error-c3017.md)|OpenMP“for”语句中的终止测试格式不正确|
|[编译器错误 C3018](compiler-error-c3018.md)|"*identifier*"： OpenMP "for" 测试或增量必须使用索引变量 "*variable*"|
|[编译器错误 C3019](compiler-error-c3019.md)|OpenMP "for" 语句中的增量格式不正确|
|[编译器错误 C3020](compiler-error-c3020.md)|"*variable*"： OpenMP "for" 循环的索引变量不能在循环体中修改|
|[编译器错误 C3021](compiler-error-c3021.md)|"*argument*"： OpenMP "*指令*" 指令上的参数为空|
|[编译器错误 C3022](compiler-error-c3022.md)|"*指令*"： OpenMP "*指令*" 指令上的 "*指令*" 的计划类型无效|
|[编译器错误 C3023](compiler-error-c3023.md)|"*argument*"：在 OpenMP "*指令*" 子句的参数中遇到意外的标记|
|[编译器错误 C3024](compiler-error-c3024.md)|"schedule (运行时) "：不允许 chunk_size 表达式|
|[编译器错误 C3025](compiler-error-c3025.md)|"*子句*"：应为整型表达式|
|[编译器错误 C3026](compiler-error-c3026.md)|"*子句*"：常量表达式必须为正|
|[编译器错误 C3027](compiler-error-c3027.md)|"*子句*"：应为算术表达式或指针表达式|
|[编译器错误 C3028](compiler-error-c3028.md)|"*member*"：只能在数据共享子句中使用变量或静态数据成员|
|[编译器错误 C3029](compiler-error-c3029.md)|"*symbol*"：只能在 OpenMP 指令中的数据共享子句中出现一次|
|[编译器错误 C3030](compiler-error-c3030.md)|"*identifier*"： "*指令*" 子句/指令中的变量不能是引用类型|
|[编译器错误 C3031](compiler-error-c3031.md)|"*identifier*"： "缩减" 子句中的变量必须是标量算术类型|
|[编译器错误 C3032](compiler-error-c3032.md)|"*identifier*"： "*子句*" 子句中的变量不能具有不完整的类型 "*type*"|
|[编译器错误 C3033](compiler-error-c3033.md)|"*identifier*"： "*子句*" 子句中的变量不能是常量限定的类型|
|[编译器错误 C3034](compiler-error-c3034.md)|OpenMP "*指令*" 指令不能直接嵌套在 "*指令*" 指令中|
|[编译器错误 C3035](compiler-error-c3035.md)|OpenMP“ordered”指令必须使用“ordered”子句直接绑定到“for”或“parallel for”指令|
|[编译器错误 C3036](compiler-error-c3036.md)|"*子句*"： OpenMP "减低" 子句中的运算符标记无效|
|[编译器错误 C3037](compiler-error-c3037.md)|"*identifier*"： "*子句*" 子句中的变量必须在封闭上下文中共享|
|[编译器错误 C3038](compiler-error-c3038.md)|"*identifier*"： "private" 子句中的变量不能是封闭上下文中的缩减变量|
|[编译器错误 C3039](compiler-error-c3039.md)|"*identifier*"： OpenMP "for" 语句中的索引变量不能是缩减变量|
|[编译器错误 C3040](compiler-error-c3040.md)|"*identifier*"： "缩减" 子句中的变量类型与缩减运算符 "*operator*" 不兼容|
|[编译器错误 C3041](compiler-error-c3041.md)|"*identifier*"： "copyprivate" 子句中的变量在封闭上下文中必须是私有的|
|[编译器错误 C3042](compiler-error-c3042.md)|"copyprivate" 和 "nowait" 子句不能同时出现在 OpenMP "*指令*" 指令上|
|[编译器错误 C3043](compiler-error-c3043.md)|OpenMP“critical”指令不能嵌套在同名的“critical”指令中|
|[编译器错误 C3044](compiler-error-c3044.md)|"section"：只允许直接嵌套在 OpenMP "sections" 指令下|
|[编译器错误 C3045](compiler-error-c3045.md)|OpenMP “sections”指令后应为一个复合语句。 缺少“{”|
|[编译器错误 C3046](compiler-error-c3046.md)|OpenMP“#pragma omp sections”区域中缺少结构化块|
|[编译器错误 C3047](compiler-error-c3047.md)|OpenMP“sections”区域中的结构化块的前面必须是“#pragma omp section”|
|[编译器错误 C3048](compiler-error-c3048.md)|“#pragma omp atomic”后面的表达式格式不正确|
|[编译器错误 C3049](compiler-error-c3049.md)|"*argument*"： OpenMP "default" 子句中的参数无效|
|[编译器错误 C3050](compiler-error-c3050.md)|"*class*"： ref 类不能从 "*identifier*" 继承|
|编译器错误 C3051|已过时。|
|[编译器错误 C3052](compiler-error-c3052.md)|"*identifier*"：变量没有出现在默认 (none) 子句下的数据共享子句中|
|[编译器错误 C3053](compiler-error-c3053.md)|"*identifier*"： "threadprivate" 只对全局或静态数据项有效|
|[编译器错误 C3054](compiler-error-c3054.md)|当前在泛型类或函数中不支持“#pragma omp parallel”|
|[编译器错误 C3055](compiler-error-c3055.md)|"*identifier*"：符号在用于 "threadprivate" 指令之前不能引用|
|[编译器错误 C3056](compiler-error-c3056.md)|"*identifier*"：符号与 "threadprivate" 指令位于同一范围内|
|[编译器错误 C3057](compiler-error-c3057.md)|"*identifier*"：当前不支持 "threadprivate" 符号的动态初始化|
|[编译器错误 C3058](compiler-error-c3058.md)|"*identifier*"：符号在用于 "copyin" 子句之前未声明为 "threadprivate"|
|[编译器错误 C3059](compiler-error-c3059.md)|"*identifier*"： "threadprivate" 符号不能用于 "*子句*" 子句中|
|[编译器错误 C3060](compiler-error-c3060.md)|"*identifier*"：友元函数不能使用限定名在类内定义 (只能声明它) |
|编译器错误 C3061|运算符 "*operator*"：不允许在基本类型为 "*type*" 的枚举 "*type*" 中使用|
|[编译器错误 C3062](compiler-error-c3062.md)|"*identifier*"：枚举器需要值，因为基础类型为 "*type*"|
|[编译器错误 C3063](compiler-error-c3063.md)|运算符 "*operator*"：所有操作数必须具有相同的枚举类型|
|编译器错误 C3064|"*identifier*"：必须是简单类型或解析为一个|
|[编译器错误 C3065](compiler-error-c3065.md)|不允许在非类范围上声明属性|
|[编译器错误 C3066](compiler-error-c3066.md)|有多种方法可使用这些参数调用此类型的对象|
|编译器错误 C3067|初始值设定项列表不能与内置运算符 [] 一起使用|
|[编译器错误 C3068](compiler-error-c3068.md)|"*identifier*"： "naked" 函数不能包含在出现 c + + 异常时需要展开的对象|
|[编译器错误 C3069](compiler-error-c3069.md)|运算符 "*operator*"：不允许用于枚举类型|
|[编译器错误 C3070](compiler-error-c3070.md)|"*identifier*"：属性没有 "set" 方法|
|[编译器错误 C3071](compiler-error-c3071.md)|运算符 "*operator*" 只能应用于 ref 类或值类型的实例|
|[编译器错误 C3072](compiler-error-c3072.md)|运算符 "*operator*" 不能应用于 ref 类的实例使用一元 "%" 运算符将 ref 类的实例转换为句柄类型|
|[编译器错误 C3073](compiler-error-c3073.md)|"*identifier*"： ref 类没有用户定义的复制构造函数|
|编译器错误 C3074|无法使用带括号的初始值设定项初始化数组|
|[编译器错误 C3075](compiler-error-c3075.md)|"*identifier*"：不能在值类型中嵌入引用类型 "*type*" 的实例|
|[编译器错误 C3076](compiler-error-c3076.md)|"*identifier*"：不能在本机类型中嵌入引用类型为 "*type*" 的实例|
|[编译器错误 C3077](compiler-error-c3077.md)|"*identifier*"：终结器只能是引用类型的成员|
|编译器错误 C3078|必须在新的表达式中指定数组大小|
|编译器错误 C3079|初始值设定项列表不能用作此赋值运算符的右操作数|
|[编译器错误 C3080](compiler-error-c3080.md)|"*finalizer*"：终结器不能具有存储类说明符|
|编译器错误 C3081|已过时。|
|编译器错误 C3082|已过时。|
|[编译器错误 C3083](compiler-error-c3083.md)|"*identifier*"： "：：" 左侧的符号必须是一种类型|
|[编译器错误 C3084](compiler-error-c3084.md)|"*identifier*"：析构函数/终结器不能是 "*关键字*"|
|[编译器错误 C3085](compiler-error-c3085.md)|"*identifier*"：构造函数不能是 "*关键字*"|
|编译器错误 C3086|找不到 "std：： initializer_list"：需要 #include \<initializer_list>|
|[编译器错误 C3087](compiler-error-c3087.md)|"*identifier*"： "*声明*" 的调用已经初始化了此成员|
|编译器错误 C3088|"*class*"：特性构造函数必须具有已命名的形参|
|编译器错误 C3089|"*identifier*"：参数名与任何数据成员的名称都不匹配|
|编译器错误 C3090|"*class*"：特性类不能是模板|
|编译器错误 C3091|"*class*"：特性类不能包含基类|
|编译器错误 C3092|"*class*"：属性类成员不能是位域，"static" 或 "const"|
|编译器错误 C3093|"*type*"：类型不允许用于特性类成员 "*member*"|
|[编译器错误 C3094](compiler-error-c3094.md)|"*attribute*"：不允许匿名使用|
|[编译器错误 C3095](compiler-error-c3095.md)|"*attribute*"：特性不能重复|
|[编译器错误 C3096](compiler-error-c3096.md)|"*attribute*"：特性只允许用于特性类的数据成员|
|[编译器错误 C3097](compiler-error-c3097.md)|"*attribute*"：特性必须具有 "assembly：" 或 "module：" 的范围|
|编译器错误 C3098|"*identifier*"：特性没有用户定义的构造函数|
|[编译器错误 C3099](compiler-error-c3099.md)|"*关键字*"：对托管/WinRT 特性使用 [System：： AttributeUsageAttribute]/[Windows：： Foundation：： Metadata：： AttributeUsageAttribute]|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
