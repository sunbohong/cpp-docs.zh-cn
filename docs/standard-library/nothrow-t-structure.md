---
description: 了解详细信息： nothrow_t 结构
title: nothrow_t 结构
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: 974fbe3a1e27da41c6366c62d748426293a54437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338091"
---
# <a name="nothrow_t-structure"></a>nothrow_t 结构

该结构用作运算符 new 的函数参数，指示函数应返回一个 null 指针来报告分配失败，而不是引发异常。

## <a name="syntax"></a>语法

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>备注

该结构可帮助编译器选择正确版本的构造函数。 [nothrow](../standard-library/new-functions.md#nothrow) 是 `std::nothrow_t` 类型的对象的同义词。

## <a name="example"></a>示例

有关如何将 `std::nothrow_t` 用作函数参数的示例，请参阅[运算符 new](../standard-library/new-operators.md#op_new) 和[运算符 new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)。
