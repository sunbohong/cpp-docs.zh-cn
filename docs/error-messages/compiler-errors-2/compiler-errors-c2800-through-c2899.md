---
description: 了解有关以下内容的详细信息：编译器错误 C2800 到 C2899
title: 编译器错误 C2800 - C2899
ms.date: 04/21/2019
f1_keywords:
- C2816
- C2820
- C2822
- C2826
- C2832
- C2836
- C2837
- C2840
- C2841
- C2848
- C2851
- C2852
- C2853
- C2866
- C2880
- C2887
- C2889
- C2895
- C2899
helpviewer_keywords:
- C2816
- C2820
- C2822
- C2826
- C2832
- C2836
- C2837
- C2840
- C2841
- C2848
- C2851
- C2852
- C2853
- C2866
- C2880
- C2887
- C2889
- C2895
- C2899
ms.assetid: e5de1e92-746a-4315-a331-c5d9efb76dbb
ms.openlocfilehash: 65455224744b4463bdb919e488b34530274fa547
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238786"
---
# <a name="compiler-errors-c2800-through-c2899"></a>编译器错误 C2800 - C2899

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|[编译器错误 C2800](compiler-error-c2800.md)|无法重载 "operator *operator*"|
|[编译器错误 C2801](compiler-error-c2801.md)|"*member*" 必须是非静态成员|
|[编译器错误 C2802](compiler-error-c2802.md)|静态成员 "operator *operator*" 没有形参|
|[编译器错误 C2803](compiler-error-c2803.md)|"operator *operator*" 必须至少有一个类类型的形参|
|[编译器错误 C2804](compiler-error-c2804.md)|二元运算符 "operator *operator*" 的参数太多|
|[编译器错误 C2805](compiler-error-c2805.md)|二元运算符 "operator *operator*" 的参数太少|
|[编译器错误 C2806](compiler-error-c2806.md)|"operator *operator*" 的形参太多|
|[编译器错误 C2807](compiler-error-c2807.md)|后缀 "operator *operator*" 的第二个形参必须为 "int"|
|[编译器错误 C2808](compiler-error-c2808.md)|一元运算符 "operator *operator*" 的形参太多|
|[编译器错误 C2809](compiler-error-c2809.md)|"operator *operator*" 没有形参|
|[编译器错误 C2810](compiler-error-c2810.md)|"*interface*"：接口只能从另一个接口继承|
|[编译器错误 C2811](compiler-error-c2811.md)|"*type1*"：不能从 "*type2*" 继承，ref 类只能从 ref 类或接口类继承|
|[编译器错误 C2812](compiler-error-c2812.md)|/clr： pure 和/clr： safe 不支持 #import|
|[编译器错误 C2813](compiler-error-c2813.md)|#import 不支持 /MP|
|[编译器错误 C2814](compiler-error-c2814.md)|"*member*"：本机类型不能嵌套在托管的/WinRT 类型 "*class*" 中|
|[编译器错误 C2815](compiler-error-c2815.md)|"operator delete"：第一个形参必须为 "void \* "，但使用的是 "*type*"|
|编译器错误 C2816|已过时。|
|[编译器错误 C2817](compiler-error-c2817.md)|"operator delete" 的返回类型必须为 "void"|
|[编译器错误 C2818](compiler-error-c2818.md)|重载 "operator->" 的应用程序是通过类型 "*class*" 递归的|
|[编译器错误 C2819](compiler-error-c2819.md)|类型 "*class*" 没有重载成员 "operator->"|
|编译器错误 C2820|已过时。|
|[编译器错误 C2821](compiler-error-c2821.md)|"operator new" 的第一个形参必须是 "size_t"|
|编译器错误 C2822|此平台不支持本地展开|
|[编译器错误 C2823](compiler-error-c2823.md)|typedef 模板/泛型是非法的|
|[编译器错误 C2824](compiler-error-c2824.md)|"operator new" 的返回类型必须为 "void \* "|
|[编译器错误 C2825](compiler-error-c2825.md)|"*identifier*"：在后跟 "：：" 时必须为类或命名空间|
|编译器错误 C2826|已过时。|
|[编译器错误 C2827](compiler-error-c2827.md)|不能用一元形式全局重写 "operator *operator*"|
|[编译器错误 C2828](compiler-error-c2828.md)|不能用 binary 形式全局重写 "operator *operator*"|
|[编译器错误 C2829](compiler-error-c2829.md)|"operator *operator*" 不能有变量参数列表|
|[编译器错误 C2830](compiler-error-c2830.md)|只有 "operator new" 的位置参数可以有默认值|
|[编译器错误 C2831](compiler-error-c2831.md)|"operator *operator*" 不能有默认参数|
|编译器错误 C2832|"*identifier*"：引用类型不能进行值初始化|
|[编译器错误 C2833](compiler-error-c2833.md)|"operator *token*" 不是可识别的运算符或类型|
|[编译器错误 C2834](compiler-error-c2834.md)|"operator *operator*" 必须是全局限定的|
|[编译器错误 C2835](compiler-error-c2835.md)|用户定义的转换 "*type*" 不采用形参|
|编译器错误 C2836|"*identifier*"：只有联合的一个非静态数据成员可以有默认成员初始值设定项|
|编译器错误 C2837|"*function*"：不能在同一函数中使用 OpenMP 指令和 #pragma 循环 (hint_parallel) |
|[编译器错误 C2838](compiler-error-c2838.md)|"*identifier*"：成员声明中的非法限定名|
|[编译器错误 C2839](compiler-error-c2839.md)|重载 "operator->" 的返回类型 "*type*" 无效|
|编译器错误 C2840|指令字参数不是常量|
|编译器错误 C2841|寄存器参数不是常量|
|[编译器错误 C2842](compiler-error-c2842.md)|"*class*"：托管或 WinRT 类型不能定义自己的 "operator new" 或 "operator delete"|
|[编译器错误 C2843](compiler-error-c2843.md)|"*member*"：不能采用非静态数据成员的地址或托管/WinRT 类型的方法|
|[编译器错误 C2844](compiler-error-c2844.md)|"*identifier*"：不能是接口 "*interface*" 的成员|
|[编译器错误 C2845](compiler-error-c2845.md)|"*type*"：此类型上不允许使用指针算法|
|[编译器错误 C2846](compiler-error-c2846.md)|"*interface*"：接口不能有构造函数|
|[编译器错误 C2847](compiler-error-c2847.md)|无法将 sizeof 应用于托管/WinRT 类型 "*class*"|
|编译器错误 C2848|"*class*"：托管或 WinRT 类型不能是联合的成员|
|[编译器错误 C2849](compiler-error-c2849.md)|"*interface*"：接口不能有析构函数|
|[编译器错误 C2850](compiler-error-c2850.md)|"*构造*"：仅允许在文件范围内使用;不能在嵌套构造中|
|编译器错误 C2851|"*enum*"：公共 WinRT 枚举只能使用 "int" 或 "无符号 int" 作为基类型|
|编译器错误 C2852|"*identifier*"：只有数据成员才能在类中初始化|
|编译器错误 C2853|"*identifier*"：非静态数据成员不能具有包含 "auto" 的类型|
|[编译器错误 C2854](compiler-error-c2854.md)|#pragma hdrstop 中的语法错误|
|[编译器错误 C2855](compiler-error-c2855.md)|命令行选项 "*option*" 与预编译头不一致|
|[编译器错误 C2856](compiler-error-c2856.md)|#pragma hdrstop 不能在 #if 块内|
|[编译器错误 C2857](compiler-error-c2857.md)|在源文件中找不到用/Yc *filename* 命令行选项指定的 "#include" 语句|
|[编译器错误 C2858](compiler-error-c2858.md)|命令行选项 "/Yc (/Fd *filename*) " 与使用 "/fd *filename*" 的预编译头不一致|
|[编译器错误 C2859](compiler-error-c2859.md)|*filename* 不是创建此预编译头时使用的文件 *类型* 文件，请重新创建预编译头。|
|[编译器错误 C2860](compiler-error-c2860.md)|"void" 不能是参数类型，" (void) " 除外|
|[编译器错误 C2861](compiler-error-c2861.md)|"*声明*"：不能定义接口成员函数|
|[编译器错误 C2862](compiler-error-c2862.md)|"*interface*"：接口只能有公共成员|
|[编译器错误 C2863](compiler-error-c2863.md)|"*interface*"：接口不能有友元|
|[编译器错误 C2864](compiler-error-c2864.md)|"*identifier*"：具有类内初始值设定项的静态数据成员/模板变量必须具有非易失性常量整型|
|[编译器错误 C2865](compiler-error-c2865.md)|"*operator*"：对象指针/句柄的比较非法|
|编译器错误 C2866|已过时。|
|[编译器错误 C2867](compiler-error-c2867.md)|"*identifier*"：不是命名空间|
|[编译器错误 C2868](compiler-error-c2868.md)|"*identifier*"：非法的 using 声明语法;应为限定名|
|[编译器错误 C2869](compiler-error-c2869.md)|"*identifier*"：已被定义为命名空间|
|[编译器错误 C2870](compiler-error-c2870.md)|"*identifier*"：命名空间定义必须出现在文件范围内或紧跟在另一个命名空间定义中|
|[编译器错误 C2871](compiler-error-c2871.md)|"*identifier*"：不存在具有此名称的命名空间|
|[编译器错误 C2872](compiler-error-c2872.md)|"*identifier*"：不明确的符号|
|[编译器错误 C2873](compiler-error-c2873.md)|"*symbol*"：符号不能用在 using 声明中|
|[编译器错误 C2874](compiler-error-c2874.md)|using 声明导致 "*identifier*" 的多个声明|
|[编译器错误 C2875](compiler-error-c2875.md)|using 声明导致 "*class*：：*identifier*" 的多个声明|
|[编译器错误 C2876](compiler-error-c2876.md)|"*class*：：*member*"：并非所有的重载都可访问|
|[编译器错误 C2877](compiler-error-c2877.md)|无法从 "*类*" 访问 "*member*"|
|[编译器错误 C2878](compiler-error-c2878.md)|"*identifier*"：该名称的命名空间或类不存在|
|[编译器错误 C2879](compiler-error-c2879.md)|"*identifier*"：只有现有命名空间才能由命名空间别名定义赋予备用名称|
|编译器错误 C2880|__swi 或 __hvc 需要一个有效常量作为第一个参数 (SWI number) |
|[编译器错误 C2881](compiler-error-c2881.md)|"*identifier*"：已作为 "*class*" 的别名使用|
|[编译器错误 C2882](compiler-error-c2882.md)|"*identifier*"：在表达式中非法使用命名空间标识符|
|[编译器错误 C2883](compiler-error-c2883.md)|"*function*"：函数声明与 using 声明引入的 "*identifier*" 冲突|
|[编译器错误 C2884](compiler-error-c2884.md)|"*identifier*"：由 using 声明引入，与本地函数 "*function*" 冲突|
|[编译器错误 C2885](compiler-error-c2885.md)|"*class*：：*identifier*"：在非类范围内不是有效的 using 声明|
|[编译器错误 C2886](compiler-error-c2886.md)|"*class*：：*identifier*"：符号不能用在成员 using 声明中|
|编译器错误 C2887|__swi 或 __hvc 的参数不能超过五个 (SWI number，r0) |
|[编译器错误 C2888](compiler-error-c2888.md)|"*identifier*"：不能在命名空间 "*namespace*" 内定义符号|
|编译器错误 C2889|"*class*"：托管的/WinRT 类类型不能是虚拟基类|
|[编译器错误 C2890](compiler-error-c2890.md)|"*class*"： ref 类只能有一个非接口基类|
|[编译器错误 C2891](compiler-error-c2891.md)|"*parameter*"：无法获取模板参数的地址|
|[编译器错误 C2892](compiler-error-c2892.md)|局部类不应有成员模板|
|[编译器错误 C2893](compiler-error-c2893.md)|未能使函数模板 "*template*" 专用化|
|[编译器错误 C2894](compiler-error-c2894.md)|模板不能声明为具有 "C" 链接|
|编译器错误 C2895|"*声明*"：无法显式实例化已使用 dllimport 声明的函数模板|
|[编译器错误 C2896](compiler-error-c2896.md)|"*function1*"：不能将函数模板/泛型 "*function2*" 用作函数参数|
|[编译器错误 C2897](compiler-error-c2897.md)|析构函数/终结器不能是函数模板|
|[编译器错误 C2898](compiler-error-c2898.md)|"*声明*"：成员函数模板不能是虚拟的|
|编译器错误 C2899|已过时。|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
