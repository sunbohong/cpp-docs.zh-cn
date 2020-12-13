---
description: 了解详细信息： __emul、__emulu
title: __emul, __emulu
ms.date: 09/02/2019
f1_keywords:
- __emulu_cpp
- __emul
- __emul_cpp
- __emulu
helpviewer_keywords:
- __emul intrinsic
- __emulu intrinsic
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
ms.openlocfilehash: cdcbd14e4e72bcaf7d2c7fd5f098a291e32227cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337054"
---
# <a name="__emul-__emulu"></a>__emul, __emulu

**Microsoft 专用**

执行溢出32位整数可以保存的内容的祖。

## <a name="syntax"></a>语法

```C
__int64 __emul(
   int a,
   int b
);
unsigned __int64 __emulu(
   unsigned int a,
   unsigned int b
);
```

### <a name="parameters"></a>parameters

*的*\
中乘法的第一个整数操作数。

*b*\
中乘法的第二个整数操作数。

## <a name="return-value"></a>返回值

相乘的结果。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__emul`|x86、x64|
|`__emulu`|x86、x64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

`__emul` 采用 2 32 位的带符号值，并以64位带符号整数值的形式返回相乘的结果。

`__emulu` 采用 2 32 位无符号整数值，并以64位无符号整数值的形式返回相乘的结果。

## <a name="example"></a>示例

```cpp
// emul.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__emul)
#pragma intrinsic(__emulu)

int main()
{
   int a = -268435456;
   int b = 2;

   __int64 result = __emul(a, b);

   cout << a << " * " << b << " = " << result << endl;

   unsigned int ua = 0xFFFFFFFF; // Dec value: 4294967295
   unsigned int ub = 0xF000000;  // Dec value: 251658240

   unsigned __int64 uresult = __emulu(ua, ub);

   cout << ua << " * " << ub << " = " << uresult << endl;

}
```

## <a name="output"></a>输出

```Output
-268435456 * 2 = -536870912
4294967295 * 251658240 = 1080863910317260800
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
