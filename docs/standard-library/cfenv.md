---
description: 了解详细信息： &lt; cfenv&gt;
title: '&lt;cfenv&gt;'
ms.date: 11/04/2016
ms.assetid: 6a17ad51-2182-4e91-8108-65997382acd3
ms.openlocfilehash: e01a74b9df3431ed257cb015260d0775320a88ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325284"
---
# <a name="ltcfenvgt"></a>&lt;cfenv&gt;

包含标准 C 库标头 \<fenv.h> 并将关联名称添加到 `std` 命名空间。

## <a name="syntax"></a>语法

```cpp
#include <cfenv>
```

## <a name="remarks"></a>备注

包含该标头还将确保使用标准 C 库标头中的外部链接声明的名称在 `std` 命名空间中声明。

## <a name="constants-and-types"></a>常量和类型

```cpp
#define FE_ALL_EXCEPT see below
#define FE_DIVBYZERO see below
#define FE_INEXACT see below
#define FE_INVALID see below
#define FE_OVERFLOW see below
#define FE_UNDERFLOW see below
#define FE_DOWNWARD see below
#define FE_TONEAREST see below
#define FE_TOWARDZERO see below
#define FE_UPWARD see below
#define FE_DFL_ENV see below

namespace std {
    using fenv_t = object type ;
    using fexcept_t = integer type ;
}
```

## <a name="functions"></a>函数

```cpp
int feclearexcept(int except);
int fegetexceptflag(fexcept_t* pflag, int except);
int feraiseexcept(int except);
int fesetexceptflag(const fexcept_t* pflag, int except);
int fetestexcept(int except);
int fegetround();
int fesetround(int mode);
int fegetenv(fenv_t* penv);
int feholdexcept(fenv_t* penv);
int fesetenv(const fenv_t* penv);
int feupdateenv(const fenv_t* penv);
```

## <a name="see-also"></a>请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库概述](../standard-library/cpp-standard-library-overview.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
