---
description: 了解有关以下内容的详细信息：编译器错误 C2900 到 C2999
title: 编译器错误 C2900 - C2999
ms.date: 04/21/2019
f1_keywords:
- C2900
- C2901
- C2905
- C2907
- C2915
- C2916
- C2922
- C2924
- C2925
- C2926
- C2938
- C2949
- C2950
- C2954
- C2956
- C2960
- C2961
- C2963
- C2964
- C2965
- C2966
- C2967
- C2968
- C2972
- C2980
- C2981
- C2982
- C2983
- C2984
- C2985
- C2986
- C2987
- C2997
- C2999
helpviewer_keywords:
- C2900
- C2901
- C2905
- C2907
- C2915
- C2916
- C2922
- C2924
- C2925
- C2926
- C2938
- C2949
- C2950
- C2954
- C2956
- C2960
- C2961
- C2963
- C2964
- C2965
- C2966
- C2967
- C2968
- C2972
- C2980
- C2981
- C2982
- C2983
- C2984
- C2985
- C2986
- C2987
- C2997
- C2999
ms.assetid: e3440738-e11b-4878-9ae3-6bc6c53ba461
ms.openlocfilehash: 73770588a27bb0f5150f3334f33e0a1c33aa2296
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238760"
---
# <a name="compiler-errors-c2900-through-c2999"></a>编译器错误 C2900 - C2999

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|编译器错误 C2900|"*声明符*"： WinRT 类中的成员函数模板必须为 "private"、"internal" 或 "protected private"|
|编译器错误 C2901|"*identifier*"：泛型接口或委托不能是公共的|
|[编译器错误 C2902](compiler-error-c2902.md)|"*token*"： "template/generic" 后面有意外标记，应输入标识符|
|[编译器错误 C2903](compiler-error-c2903.md)|"*identifier*"：符号既不是类模板/泛型，也不是函数模板/泛型|
|[编译器错误 C2904](compiler-error-c2904.md)|"*identifier*"：名称已经用于当前范围内的模板|
|编译器错误 C2905|已过时。|
|[编译器错误 C2906](compiler-error-c2906.md)|"*template*"：显式专用化需要 "template <>"|
|编译器错误 C2907|寄存器参数 "*number*" 未指定有效寄存器号|
|[编译器错误 C2908](compiler-error-c2908.md)|显式专用化;已实例化 "*template*"|
|[编译器错误 C2909](compiler-error-c2909.md)|"*identifier*"：函数模板的显式实例化需要返回类型|
|[编译器错误 C2910](compiler-error-c2910.md)|"*function*"：不能显式专用化|
|[编译器错误 C2911](compiler-error-c2911.md)|"*member*"：无法在当前范围中声明或定义|
|[编译器错误 C2912](compiler-error-c2912.md)|显式专用化 "*声明*" 不是函数模板的专用化|
|[编译器错误 C2913](compiler-error-c2913.md)|显式专用化;"*声明*" 不是类模板的专用化|
|[编译器错误 C2914](compiler-error-c2914.md)|"*identifier*"：无法推导模板/泛型参数，因为函数参数不明确|
|编译器错误 C2915|"*identifier*"：不能在 WinRT 类型的发布接口上直接使用 "*type*"。 请改用 "Platform：： Object ^" 来传递此类型|
|编译器错误 C2916|"*identifier*"： [FlagsAttribute] 必须 (只能在具有 "无符号 int" 基础类型的公共枚举上指定) |
|[编译器错误 C2917](compiler-error-c2917.md)|"*identifier*"：模板参数无效|
|[编译器错误 C2918](compiler-error-c2918.md)|"*identifier*"：不能在 WinRT 类型的发布接口上使用索引属性|
|[编译器错误 C2919](compiler-error-c2919.md)|"*type*"：不能在 WinRT 类型的发布接口上使用运算符|
|[编译器错误 C2920](compiler-error-c2920.md)|重定义： "*type*"：类模板/泛型已经声明为 "*声明*"|
|[编译器错误 C2921](compiler-error-c2921.md)|重定义： "*type*"：类模板/泛型正在被重新声明为 "*声明*"|
|编译器错误 C2922|"*interface*"： WinRT 接口不能包含静态成员|
|[编译器错误 C2923](compiler-error-c2923.md)|"*type*"： "*identifier*" 不是参数 "*parameter*" 的有效模板/泛型类型参数|
|编译器错误 C2924|__declspec (中断) 例程参数不在 R2 中|
|编译器错误 C2925|__declspec (中断) 例程不能使用浮点|
|编译器错误 C2926|"*identifier*"：联合中的匿名结构的成员不允许使用默认成员初始值设定项|
|[编译器错误 C2927](compiler-error-c2927.md)|"*identifier*"：必须至少用一个参数调用函数模板|
|[编译器错误 C2928](compiler-error-c2928.md)|显式实例化;"*identifier*" 不是模板类 "*class*" 的函数或静态数据成员|
|[编译器错误 C2929](compiler-error-c2929.md)|"*声明符*"：显式实例化;无法显式强制和取消模板类成员的实例化|
|[编译器错误 C2930](compiler-error-c2930.md)|"*class*"：模板 id/泛型 id 重新定义为 "enum *标识符*" 的枚举器|
|[编译器错误 C2931](compiler-error-c2931.md)|"*class1*"： template id/generic id 重新定义为 "*class2*" 的成员函数|
|[编译器错误 C2932](compiler-error-c2932.md)|"*type*"： template id/generic id 重新定义为 "*identifier*" 的数据成员|
|[编译器错误 C2933](compiler-error-c2933.md)|"*type*"： template id/generic id 重定义为 "*identifier*" 的 typedef 成员|
|[编译器错误 C2934](compiler-error-c2934.md)|"*type*"： template id/generic id 重新定义为 "*identifier*" 的嵌套 "*item*"|
|[编译器错误 C2935](compiler-error-c2935.md)|"*type*"： template id/generic id 重新定义为全局函数|
|[编译器错误 C2936](compiler-error-c2936.md)|"*type*"： template id/generic id 重新定义为全局数据变量|
|[编译器错误 C2937](compiler-error-c2937.md)|"*type*"： template id/generic id 重新定义为全局 typedef|
|编译器错误 C2938|"*identifier*"：未能使别名模板专用化|
|[编译器错误 C2939](compiler-error-c2939.md)|"*type*"：模板 id/泛型 id 重定义为本地数据变量|
|[编译器错误 C2940](compiler-error-c2940.md)|"*type*"：模板 id/泛型 id 重定义为本地 typedef|
|[编译器错误 C2941](compiler-error-c2941.md)|"*type*"： template id/generic id 重定义为本地 "*item*"|
|[编译器错误 C2942](compiler-error-c2942.md)|"*type*"： template id/generic id 重新定义为函数的形参|
|[编译器错误 C2943](compiler-error-c2943.md)|"*type*"：模板 id/泛型 id 重新定义为模板的类型参数|
|[编译器错误 C2944](compiler-error-c2944.md)|"*type*"：模板 id/泛型 id 重新定义为模板的值参数|
|[编译器错误 C2945](compiler-error-c2945.md)|显式实例化不引用模板类专用化|
|[编译器错误 C2946](compiler-error-c2946.md)|显式实例化;"*type*" 不是模板类专用化|
|[编译器错误 C2947](compiler-error-c2947.md)|应为 ">" 以终止模板参数，但找到的是 "*token*"|
|[编译器错误 C2948](compiler-error-c2948.md)|显式实例化;专用化中不允许存储类说明符 "*说明符*"|
|编译器错误 C2949|/kernel 不支持 thread_local|
|编译器错误 C2950|已过时。|
|[编译器错误 C2951](compiler-error-c2951.md)|仅在全局、命名空间或类范围内允许模板/泛型声明|
|[编译器错误 C2952](compiler-error-c2952.md)|"*声明*"：模板/泛型声明缺少模板/泛型参数列表|
|[编译器错误 C2953](compiler-error-c2953.md)|"*type*"：类模板已经定义|
|编译器错误 C2954|指令字参数不在范围内|
|[编译器错误 C2955](compiler-error-c2955.md)|"*type*"：类模板/泛型的使用需要模板/泛型参数列表|
|编译器错误 C2956|大小释放函数 "operator delete (void *，size_t) " 将被选作定位释放函数。|
|[编译器错误 C2957](compiler-error-c2957.md)|"*token*"：无效的左侧分隔符：应为 "<"|
|[编译器错误 C2958](compiler-error-c2958.md)|位于 "*file* (*line_number*) " 的左侧 *分隔符* 未正确匹配|
|[编译器错误 C2959](compiler-error-c2959.md)|泛型类或函数不能是模板的成员|
|编译器错误 C2960|已过时。|
|编译器错误 C2961|"*function*"：显式实例化不一致，上一个显式实例化未指定 "*argument*"|
|[编译器错误 C2962](compiler-error-c2962.md)|语法错误： "*token*"：模板类成员函数定义应以 "}" 结尾|
|编译器错误 C2963|已过时。|
|编译器错误 C2964|已过时。|
|编译器错误 C2965|/kernel 不支持 __declspec (*说明符*) |
|编译器错误 C2966|"*identifier1*"：必须具有相同的 __declspec (code_seg ( ... ) # A3 作为其基类 "*identifier2*"|
|编译器错误 C2967|"*identifier*"：重写虚函数必须具有相同的 __declspec (code_seg ( ... ) # A3 作为重写虚拟函数|
|编译器错误 C2968|"*identifier*"：递归别名声明|
|[编译器错误 C2969](compiler-error-c2969.md)|语法错误： "*token*"：成员函数定义应以 "}" 结尾|
|[编译器错误 C2970](compiler-error-c2970.md)|"*type*"：模板参数 "*parameter*"： "*argument*"：涉及带有内部链接的对象的表达式不能用作非类型参数|
|[编译器错误 C2971](compiler-error-c2971.md)|"*type*"：模板参数 "*parameter*"： "*argument*"：包含非静态存储持续时间的变量不能用作非类型参数|
|编译器错误 C2972|"*type*"：模板参数 "*parameter*"：非类型参数的类型无效|
|[编译器错误 C2973](compiler-error-c2973.md)|"*template*"：无效的模板参数 "*number*"|
|[编译器错误 C2974](compiler-error-c2974.md)|"*type*"： "*parameter*" 的模板/泛型参数无效，应为类型|
|[编译器错误 C2975](compiler-error-c2975.md)|"*type*"： "*parameter*" 的模板参数无效，应为编译时常量表达式|
|[编译器错误 C2976](compiler-error-c2976.md)|"*type*"：模板/泛型参数太少|
|[编译器错误 C2977](compiler-error-c2977.md)|"*type*"：模板/泛型参数太多|
|[编译器错误 C2978](compiler-error-c2978.md)|语法错误：应为 "*keyword1*" 或 "*keyword2*";找到类型 "*type*";泛型中不支持非类型参数|
|[编译器错误 C2979](compiler-error-c2979.md)|泛型中不支持显式专用化|
|编译器错误 C2980|/Kernel 不支持 c + + 异常处理|
|编译器错误 C2981|/kernel 不支持动态形式的 "*关键字*"|
|编译器错误 C2982|"*声明*"：不同的 __declspec (code_seg ( ... ) # A3 已使用：现在为 "*identifier1*"，现在为 "*identifier2*"|
|编译器错误 C2983|"*声明*"：所有声明都必须具有相同的 __declspec (code_seg ( ... ) # A3|
|编译器错误 C2984|已过时。|
|编译器错误 C2985|"*argument*"： code_seg )  ( __declspec (的参数必须是文本部分|
|编译器错误 C2986|"*identifier*"： __declspec (code_seg ( ... ) # A3 只能应用于类或函数|
|编译器错误 C2987|声明不能同时具有 __declspec (code_seg ( "*identifier*" ) # A3 和 __declspec (code_seg ( "*value*" ) # A7|
|[编译器错误 C2988](compiler-error-c2988.md)|不可识别的模板声明/定义|
|[编译器错误 C2989](compiler-error-c2989.md)|"*class*"：类模板/泛型已经声明为非类模板/泛型|
|[编译器错误 C2990](compiler-error-c2990.md)|"*class*"：非类模板/泛型已经声明为类模板/泛型|
|[编译器错误 C2991](compiler-error-c2991.md)|模板/泛型参数 "*parameter*" 的重定义|
|[编译器错误 C2992](compiler-error-c2992.md)|"*class*"：模板/泛型参数列表无效或缺失|
|[编译器错误 C2993](compiler-error-c2993.md)|"*type*"：非类型模板参数 "*identifier*" 的类型非法|
|[编译器错误 C2994](compiler-error-c2994.md)|模板参数列表中未命名的类|
|[编译器错误 C2995](compiler-error-c2995.md)|"*声明*"：函数模板已经定义|
|[编译器错误 C2996](compiler-error-c2996.md)|"*function*"：递归函数模板定义|
|编译器错误 C2997|"*function*"：无法从默认成员初始值设定项推导数组界限|
|[编译器错误 C2998](compiler-error-c2998.md)|"*声明符*"：不能是模板定义|
|编译器错误 C2999|未知错误，请选择 Visual C++ "帮助" 菜单上的 "技术支持" 命令，或打开技术支持帮助文件以获取详细信息|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
