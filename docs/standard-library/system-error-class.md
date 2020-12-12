---
description: 了解详细信息： system_error 类
title: system_error 类
ms.date: 11/04/2016
f1_keywords:
- system_error/std::system_error
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
ms.openlocfilehash: 51e629e9fffca6ec82e06521d1d81174da5ff1f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183160"
---
# <a name="system_error-class"></a>system_error 类

表示为报告低级别系统错误而引发的所有异常的基类。

## <a name="syntax"></a>语法

```cpp
class system_error : public runtime_error {
    explicit system_error(error_code _Errcode, const string& _Message = "");
    system_error(error_code _Errcode, const char *_Message);
    system_error(error_code::value_type _Errval, const error_category& _Errcat, const string& _Message);
    system_error(error_code::value_type _Errval, const error_category& _Errcat, const char *_Message);

    const error_code& code() const throw();
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>备注

由 [](../standard-library/exception-class.md) 类中的 `what` 返回的值根据 `_Message` 和 [error_code](../standard-library/error-code-class.md)（`code` 或 `error_code(_Errval, _Errcat)`）进行构造。

成员函数 `code` 返回存储的 [error_code](../standard-library/error-code-class.md) 对象。
