---
description: 了解详细信息： bad_optional_access 类
title: bad_optional_access 类
ms.date: 08/06/2019
f1_keywords:
- optional/std::bad_optional_access
ms.openlocfilehash: e3439c53766a1890592bde8ed449f5ff2779f347
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132751"
---
# <a name="bad_optional_access-class"></a>bad_optional_access 类

定义作为异常引发的对象的类型，以报告尝试访问不包含值的对象的值时所发生的情况 `optional` 。

## <a name="syntax"></a>语法

```cpp
class bad_optional_access : public exception
{
public:
    bad_optional_access() noexcept;
    bad_optional_access(const bad_optional_access&) noexcept;
    bad_optional_access& operator=(const bad_optional_access&) noexcept;
    const char* what() const noexcept override;
};
```

## <a name="see-also"></a>请参阅

[\<optional>](optional.md)\
[可选类](optional-class.md)
