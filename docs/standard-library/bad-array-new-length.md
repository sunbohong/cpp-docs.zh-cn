---
description: 了解详细信息： bad_array_new_length 类
title: bad_array_new_length 类
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_array_new_length
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: e9de10b6fee215651ac8ff6ce2fce4af55ce6c82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321635"
---
# <a name="bad_array_new_length-class"></a>bad_array_new_length 类

类描述引发的异常，以指示分配请求未成功，因为数组大小小于零或大于其限制。

## <a name="syntax"></a>语法

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>备注

返回的值 `what` 是实现定义的 C 字符串。 无成员函数引发任何异常。

## <a name="requirements"></a>要求

**标头：**\<new>

## <a name="see-also"></a>请参阅

[exception 类](../standard-library/exception-class.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
