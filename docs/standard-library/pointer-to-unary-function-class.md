---
description: 了解详细信息： pointer_to_unary_function 类
title: pointer_to_unary_function 类
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: 45a927add90915bcbd8791eeba5561027b7e9217
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340692"
---
# <a name="pointer_to_unary_function-class"></a>pointer_to_unary_function 类

将一元函数指针转换为自适应一元函数。 在 c + + 11 中已弃用，在 c + + 17 中删除。

## <a name="syntax"></a>语法

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>parameters

*pfunc*\
要转换的二元函数。

*左中*\
要对其调用 *\* pfunc* 的对象。

## <a name="return-value"></a>返回值

类模板存储的副本 `pfunc` 。 它将其成员函数 `operator()` 定义为返回 (\* **pfunc**)(_ *Left*)。

## <a name="remarks"></a>备注

一元函数指针是一个函数对象，且可能会被传递到期望将一元函数作为参数的任何 C++ 标准库算法，但它不可调适。 若要将其与适配器一起使用（如向其绑定值或将值与配合一起使用），必须与嵌套类型一起提供， `argument_type` 并 `result_type` 使此类可进行调整。 `pointer_to_unary_function` 执行的转换允许函数适配器与二元函数指针配合使用。

## <a name="example"></a>示例

很少直接使用 `pointer_to_unary_function` 的构造函数。 有关如何声明和使用 `pointer_to_unary_function` 适配器谓词的示例，请参阅帮助程序函数 [ptr_fun](../standard-library/functional-functions.md#ptr_fun)。
