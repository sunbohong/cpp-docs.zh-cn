---
description: 了解详细信息： domain_error 类
title: domain_error 类
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::domain_error
helpviewer_keywords:
- domain_error class
ms.assetid: a1d8245d-61c2-4d1e-973f-073bd5dd5fa3
ms.openlocfilehash: 337df7c7c8e2327a4e5b88a45a736c697e6cb1bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324483"
---
# <a name="domain_error-class"></a>domain_error 类

此类用作引发报告域错误的所有异常的基类。

## <a name="syntax"></a>语法

```cpp
class domain_error : public logic_error {
public:
    explicit domain_error(const string& message);

    explicit domain_error(const char *message);

};
```

## <a name="remarks"></a>备注

返回的值 `what()` 是的副本 `message.data()` 。 有关详细信息，请参阅 [`what`](../standard-library/exception-class.md) 和 [`data`](../standard-library/basic-string-class.md#data)。

## <a name="example"></a>示例

```cpp
// domain_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      throw domain_error( "Your domain is in error!" );
   }
   catch (exception &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid(e).name( ) << endl;
   };
}
/* Output:
Caught: Your domain is in error!
Type: class std::domain_error
*/
```

## <a name="requirements"></a>要求

**标头：**\<stdexcept>

**命名空间:** std

## <a name="see-also"></a>请参阅

[logic_error 类](../standard-library/logic-error-class.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
