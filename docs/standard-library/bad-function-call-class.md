---
description: 了解详细信息： bad_function_call 类
title: bad_function_call 类
ms.date: 11/04/2016
f1_keywords:
- functional/std::bad_function_call
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
ms.openlocfilehash: 659630874f84ea9e7d164b560408b162f07e1f68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321594"
---
# <a name="bad_function_call-class"></a>bad_function_call 类

报告错误的函数调用。

## <a name="syntax"></a>语法

```cpp
class bad_function_call : public std::exception {};
```

## <a name="remarks"></a>备注

该类描述引发的异常以指示在 [function 类](../standard-library/function-class.md)上调用 `operator()`
