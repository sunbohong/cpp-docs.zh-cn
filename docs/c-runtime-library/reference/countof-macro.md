---
description: 了解详细信息： _countof 宏
title: _countof 宏
ms.date: 03/22/2018
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _countof
- countof
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 190f47aa7bb6bcf6bbd9478cce9df90aca81b437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146453"
---
# <a name="_countof-macro"></a>_countof 宏

计算静态分配的数组中的元素数目。

## <a name="syntax"></a>语法

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>parameters

*array*<br/>
数组的名称。

## <a name="return-value"></a>返回值

数组中的元素数，以 **size_t** 表示。

## <a name="remarks"></a>备注

**_countof** 实现为类似于函数的预处理器宏。 如果传递的是指针而不是静态声明的数组，则 c + + 版本具有额外的模板机械来检测编译时。

确保 *数组* 实际上是数组，而不是指针。 在 C 中，如果 *数组* 是指针， **_countof** 会产生错误的结果。 在 c + + 中，如果 *array* 是指针， **_countof** 无法编译。  作为参数传递给 *decays 到指针* 的函数的数组，这意味着在函数内，不能使用 **_countof** 来确定数组的范围。

## <a name="requirements"></a>要求

|宏|必需的标头|
|-----------|---------------------|
|**_countof**|\<stdlib.h>|

## <a name="example"></a>示例

```cpp
// crt_countof.cpp
#define _UNICODE
#include <stdio.h>
#include <stdlib.h>
#include <tchar.h>

int main( void )
{
   _TCHAR arr[20], *p;
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );
   // In C++, the following line would generate a compile-time error:
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)

   _tcscpy_s( arr, _countof(arr), _T("a string") );
   // unlike sizeof, _countof works here for both narrow- and wide-character strings
}
```

```Output
sizeof(arr) = 40 bytes
_countof(arr) = 20 elements
```

## <a name="see-also"></a>请参阅

[sizeof 运算符](../../cpp/sizeof-operator.md)<br/>
