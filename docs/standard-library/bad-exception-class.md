---
description: 了解详细信息： bad_exception 类
title: bad_exception 类
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 6b47facc751e1f16e033f26be284db1287e79ea8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321607"
---
# <a name="bad_exception-class"></a>bad_exception 类

该类描述可从意外处理程序引发的异常。

## <a name="syntax"></a>语法

```cpp
class bad_exception : public exception {};

bad_exception();
bad_exception(const bad_exception&);
bad_exception& operator=(const bad_exception&);
const char* what() const override;
```

## <a name="remarks"></a>备注

如果 `bad_exception` 包含在函数的引发列表中，则 [unexpected](../standard-library/exception-functions.md#unexpected) 将引发 `bad_exception`，而不是终止或调用使用 [set_unexpected](../standard-library/exception-functions.md#set_unexpected) 指定的其他函数。

返回的值 `what` 是实现定义的 C 字符串。 无成员函数引发任何异常。

有关通过 `bad_exception` 类继承的成员列表，请参阅 [exception 类](../standard-library/exception-class.md)。

## <a name="example"></a>示例

有关引发 `bad_exception` 的 [unexpected](../standard-library/exception-functions.md#unexpected) 的使用示例，请参阅 [set_unexpected](../standard-library/exception-functions.md#set_unexpected)。
