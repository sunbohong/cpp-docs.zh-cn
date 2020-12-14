---
description: 了解有关以下内容的详细信息：编译器错误 C2500 到 C2599
title: 编译器错误 C2500 - C2599
ms.date: 04/21/2019
f1_keywords:
- C2501
- C2508
- C2515
- C2519
- C2520
- C2522
- C2525
- C2527
- C2536
- C2538
- C2539
- C2546
- C2547
- C2559
- C2560
- C2564
- C2565
- C2576
- C2578
- C2580
- C2590
- C2591
- C2595
- C2596
helpviewer_keywords:
- C2501
- C2508
- C2515
- C2519
- C2520
- C2522
- C2525
- C2527
- C2536
- C2538
- C2539
- C2546
- C2547
- C2559
- C2560
- C2564
- C2565
- C2576
- C2578
- C2580
- C2590
- C2591
- C2595
- C2596
ms.assetid: a869aaed-e9f6-49e3-b273-00ea7f45bed7
ms.openlocfilehash: 36b0b1e0d1abbbd0b3752d275011eb12282aec18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238942"
---
# <a name="compiler-errors-c2500-through-c2599"></a>编译器错误 C2500 - C2599

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|[编译器错误 C2500](compiler-error-C2500.md)|"*identifier1*"： "*identifier2*" 已是直接基类|
|编译器错误 C2501|"*identifier*"： "__declspec (*说明符*) " 只能应用于结构、联合、类或无符号位域成员|
|[编译器错误 C2502](compiler-error-C2502.md)|"*identifier*"：基类上的访问修饰符太多|
|[编译器错误 C2503](compiler-error-C2503.md)|"*class*"：基类不能包含零大小的数组|
|[编译器错误 C2504](compiler-error-C2504.md)|"*class*"：未定义基类|
|[编译器错误 C2505](compiler-error-C2505.md)|"*symbol*"： "__declspec (*说明符*) " 只能应用于全局对象或静态数据成员的声明或定义|
|[编译器错误 C2506](compiler-error-C2506.md)|"*member*"： "__declspec (*说明符*) " 不能应用于此符号|
|[编译器错误 C2507](compiler-error-C2507.md)|"*identifier*"：基类上的虚拟修饰符太多|
|编译器错误 C2508|"*identifier*"： "__declspec (*1*) " 不能与 "__declspec (*specifier2*) " 组合|
|[编译器错误 C2509](compiler-error-C2509.md)|"*identifier*"：成员函数在 "*class*" 中未声明|
|[编译器错误 C2510](compiler-error-C2510.md)|"*identifier*"： "：：" 的左边必须是类/结构/联合|
|[编译器错误 C2511](compiler-error-C2511.md)|"*identifier*"：在 "*class*" 中找不到重载成员函数|
|[编译器错误 C2512](compiler-error-C2512.md)|"*identifier*"：没有合适的默认构造函数可用|
|[编译器错误 C2513](compiler-error-C2513.md)|"* type"：在 "=" 前没有声明变量|
|[编译器错误 C2514](compiler-error-C2514.md)|"*class*"：类没有构造函数|
|编译器错误 C2515|"*identifier*"： "vtguard" 只能应用于类声明或定义|
|[编译器错误 C2516](compiler-error-C2516.md)|"*class*"：不是合法基类|
|[编译器错误 C2517](compiler-error-C2517.md)|"*identifier*"： "：：" 的右边未定义|
|[编译器错误 C2518](compiler-error-C2518.md)|关键字 "*关键字*" 在基类列表中非法;掉|
|编译器错误 C2519|"*identifier*"： WinRT 特性可能只包含公共字段|
|编译器错误 C2520|"*class*"：没有可用于隐式转换的非显式构造函数|
|[编译器错误 C2521](compiler-error-C2521.md)|析构函数/终结器不采用任何参数|
|编译器错误 C2522|"*identifier*"：重载标识符不能在 "*identifier1*" 上使用，因为它已在 "*identifier2*" 上指定|
|[编译器错误 C2523](compiler-error-C2523.md)|"*class*：： ~*identifier*"：析构函数/终结器标记不匹配|
|[编译器错误 C2524](compiler-error-C2524.md)|"*identifier*"：析构函数/终结器必须具有 "void" 参数列表|
|编译器错误 C2525|"*identifier*"：在基函数上，参数 "*identifier1*" 的名称为 "*identifier2*"，并且必须在已发布的实现中匹配|
|[编译器错误 C2526](compiler-error-C2526.md)|"*identifier1*"： c 链接函数无法返回 c + + 类 "*identifier2*"|
|编译器错误 C2527|"*identifier*"：不能同时在 "*function1*" 和 "*function2*" 上指定 DefaultOverload。 在实现过程中删除一个规范或重命名该函数|
|[编译器错误 C2528](compiler-error-C2528.md)|"*identifier*"：指向引用的指针非法|
|[编译器错误 C2529](compiler-error-C2529.md)|"*identifier*"：引用引用是非法的|
|[编译器错误 C2530](compiler-error-C2530.md)|"*identifier*"：必须初始化引用|
|[编译器错误 C2531](compiler-error-C2531.md)|"*identifier*"：对位域的引用非法|
|[编译器错误 C2532](compiler-error-C2532.md)|"*identifier*"：引用的非法修饰符|
|[编译器错误 C2533](compiler-error-C2533.md)|"*identifier*"：构造函数不能有返回类型|
|[编译器错误 C2534](compiler-error-C2534.md)|"*identifier*"：构造函数无法返回值|
|[编译器错误 C2535](compiler-error-C2535.md)|"*identifier*"：已定义或声明成员函数|
|编译器错误 C2536|已过时。|
|[编译器错误 C2537](compiler-error-C2537.md)|"*说明符*"：非法的链接规范|
|编译器错误 C2538|已过时。|
|编译器错误 C2539|已过时。|
|[编译器错误 C2540](compiler-error-C2540.md)|作为数组界限的非常量表达式|
|[编译器错误 C2541](compiler-error-C2541.md)|"*identifier*"：不能删除不是指针的对象|
|[编译器错误 C2542](compiler-error-C2542.md)|"*identifier*"：类对象没有用于初始化的构造函数|
|[编译器错误 C2543](compiler-error-C2543.md)|应输入运算符 "[]" 的 "]"|
|[编译器错误 C2544](compiler-error-C2544.md)|运算符 " ( # A2" 应为 ") "|
|[编译器错误 C2545](compiler-error-C2545.md)|"*operator*"：找不到重载运算符|
|编译器错误 C2546|"*identifier*"：在 pia 和非 PIA 中都定义了类型时，必须先引用 pia|
|编译器错误 C2547|"*identifier*"：已发布方法的所有参数都必须在声明中显式命名|
|[编译器错误 C2548](compiler-error-C2548.md)|"*function*"：缺少参数 *参数* 的默认参数|
|[编译器错误 C2549](compiler-error-C2549.md)|用户定义的转换不能指定返回类型|
|[编译器错误 C2550](compiler-error-C2550.md)|"*identifier*"：构造函数初始值设定项列表只能在构造函数定义中使用|
|[编译器错误 C2551](compiler-error-C2551.md)|“void *”类型需要显式转换|
|[编译器错误 C2552](compiler-error-C2552.md)|"*identifier*"：不能使用初始值设定项列表初始化非聚合|
|[编译器错误 C2553](compiler-error-C2553.md)|"*type* *derived_class*：：*function*"：重写虚函数返回类型与 "*type* *base_class*：：*function*" 不同|
|[编译器错误 C2555](compiler-error-C2555.md)|"*derived_class*：：*function*"：重写虚函数返回类型不同，并且不是 "*base_class*：：*function*" 的协变|
|[编译器错误 C2556](compiler-error-C2556.md)|"*type1* *class*：：*function*"：重载函数仅在 "*type2* *class*：：*function*" 的返回类型上不同|
|[编译器错误 C2557](compiler-error-C2557.md)|"*identifier*"：无法在没有构造函数的情况下初始化私有和受保护成员|
|[编译器错误 C2558](compiler-error-C2558.md)|类 "*class*"：没有可用的复制构造函数或复制构造函数声明为 "explicit"|
|编译器错误 C2559|"*identifier*"：不能使用具有引用限定符的成员函数重载没有引用限定符的成员函数|
|编译器错误 C2560|"*identifier*"：不能重载具有带引用限定符的成员函数的带引用限定符的成员函数|
|[编译器错误 C2561](compiler-error-C2561.md)|"*function*"：函数必须返回值|
|[编译器错误 C2562](compiler-error-C2562.md)|"*function*"： "void" 函数返回值|
|[编译器错误 C2563](compiler-error-C2563.md)|形参表中不匹配|
|编译器错误 C2564|已过时。|
|编译器错误 C2565|"*identifier*"：引用限定符对于构造函数/析构函数是非法的|
|[编译器错误 C2566](compiler-error-C2566.md)|条件表达式中的重载函数|
|[编译器错误 C2567](compiler-error-C2567.md)|无法打开 "*filename*" 中的元数据， *possible_reason*|
|[编译器错误 C2568](compiler-error-C2568.md)|"*identifier*"：无法解析函数重载|
|[编译器错误 C2569](compiler-error-C2569.md)|"*identifier*"：枚举/联合不能用作基类|
|[编译器错误 C2570](compiler-error-C2570.md)|"*identifier*"：联合不能有基类|
|[编译器错误 C2571](compiler-error-C2571.md)|"*identifier*"：虚函数不能在联合 "*union*" 中|
|[编译器错误 C2572](compiler-error-C2572.md)|"*function*"：重定义默认参数：参数 *号*|
|[编译器错误 C2573](compiler-error-C2573.md)|"*class*"：不能删除指向此类型的对象的指针;该类没有 "operator delete" 的非位置重载。 使用：:d e) ，或将 "operator delete (void * ) " 添加到类|
|[编译器错误 C2574](compiler-error-C2574.md)|"*析构函数*"：不能声明为 static|
|[编译器错误 C2575](compiler-error-C2575.md)|"*identifier*"：只有成员函数和基可以是虚拟的|
|编译器错误 C2576|"*identifier*"：不能将新的虚方法引入为 "public"。 请考虑将方法设为非虚拟方法，或将可访问性更改为 "internal" 或 "protected private"|
|[编译器错误 C2577](compiler-error-C2577.md)|"*identifier*"：析构函数/终结器不能有返回类型|
|编译器错误 C2578|"*class*"：类型不能具有 "protected" 或 "protected public" 构造函数|
|[编译器错误 C2579](compiler-error-C2579.md)|无法解析类型 (*偏移*) *的类型。* *文件名* 中应有此项|
|编译器错误 C2580|"*identifier*"：不允许使用多个版本的默认特殊成员函数|
|[编译器错误 C2581](compiler-error-C2581.md)|"*type*"：静态 "operator =" 函数是非法的|
|[编译器错误 C2582](compiler-error-C2582.md)|"operator *operator*" 函数在 "*type*" 中不可用|
|[编译器错误 C2583](compiler-error-C2583.md)|"*identifier*"： "const/volatile" "this" 指针对于构造函数/析构函数是非法的|
|[编译器错误 C2584](compiler-error-C2584.md)|"*class*"：无法访问直接基 "*base_class2*";已是 "*base_class1*" 的基|
|[编译器错误 C2585](compiler-error-C2585.md)|到 "*type*" 的显式转换不明确|
|[编译器错误 C2586](compiler-error-C2586.md)|用户定义的转换语法不正确：非法的间接寻址|
|[编译器错误 C2587](compiler-error-C2587.md)|"*identifier*"：非法使用局部变量作为默认参数|
|[编译器错误 C2588](compiler-error-C2588.md)|"：： ~*identifier*"：非法的全局析构函数/终结器|
|[编译器错误 C2589](compiler-error-C2589.md)|"*identifier*"： "：：" 右边的非法标记|
|编译器错误 C2590|"*identifier*"：只有构造函数可以有基/成员初始值设定项列表|
|编译器错误 C2591|ExclusiveTo 不能使用 "*type*" 作为参数。 只有 "ref class" 是有效的参数|
|[编译器错误 C2592](compiler-error-C2592.md)|"*class*"： "*base_class2*" 是从 "*base_class1*" 继承的，无法重新指定|
|[编译器错误 C2593](compiler-error-C2593.md)|"operator *identifier*" 不明确|
|[编译器错误 C2594](compiler-error-C2594.md)|"*operator*"：从 "*type1*" 到 "*type2*" 的转换不明确|
|编译器错误 C2595|"*identifier*" WinRT 特性类型必须密封|
|编译器错误 C2596|"*identifier*" WinRT 特性字段只能为 "public enum class"、"int"、"无符号 int"、"bool"、"platform：： Type"、"platform：： String" 或 "Windows：： Foundation：： HResult"|
|[编译器错误 C2597](compiler-error-C2597.md)|对非静态成员 "*identifier*" 的非法引用|
|[编译器错误 C2598](compiler-error-C2598.md)|链接规范必须在全局范围内|
|[编译器错误 C2599](compiler-error-C2599.md)|"*identifier*"：不允许使用托管/WinRT 枚举的前向声明|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
