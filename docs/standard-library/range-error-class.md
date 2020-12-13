---
description: 了解详细信息： range_error 类
title: range_error 类
ms.date: 08/14/2018
f1_keywords:
- stdexcept/std::range_error
helpviewer_keywords:
- range_error class
ms.assetid: 8afb3e88-fc49-4213-b096-ed63d7aea37c
ms.openlocfilehash: c9d1ef328ba077b4b675d782df9c85d2db3a2072
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337954"
---
# <a name="range_error-class"></a>range_error 类

此类用作引发报告范围错误的所有异常的基类。

## <a name="syntax"></a>语法

```cpp
class range_error : public runtime_error {
public:
    explicit range_error(const string& message);
    explicit range_error(const char *message);
};
```

## <a name="remarks"></a>备注

的副本 [返回的值](../standard-library/exception-class.md) `message.data` 。 有关详细信息，请参阅 [basic_string：:d ata](../standard-library/basic-string-class.md#data)。

## <a name="example"></a>示例

```cpp
// range_error.cpp
// compile with: /EHsc /GR
#include <iostream>
using namespace std;
int main()
{
   try
   {
      throw range_error( "The range is in error!" );
   }
   catch (range_error &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught: The range is in error!
Type: class std::range_error
*/
```

## <a name="requirements"></a>要求

**标头：**\<stdexcept>

**命名空间:** std

## <a name="see-also"></a>请参阅

[runtime_error 类](../standard-library/runtime-error-class.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
