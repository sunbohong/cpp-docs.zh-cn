---
description: 了解详细信息： once_flag 结构
title: once_flag 结构
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 4419353e68da5929d8abed9b2c718438855057e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338012"
---
# <a name="once_flag-structure"></a>once_flag 结构

表示一个 **`struct`** ，它与模板函数 [call_once](../standard-library/mutex-functions.md#call_once) 一起使用，以确保初始化代码只调用一次，即使存在多个执行线程。

## <a name="syntax"></a>语法

struct once_flag {constexpr once_flag ( # A1 noexcept;};

## <a name="remarks"></a>备注

`once_flag` **`struct`** 仅具有默认构造函数。

可以创建 `once_flag` 类型的对象，但不能复制它们。

## <a name="requirements"></a>要求

**标头：**\<mutex>

**命名空间:** std

## <a name="see-also"></a>请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
