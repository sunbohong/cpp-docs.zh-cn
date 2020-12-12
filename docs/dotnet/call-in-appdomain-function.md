---
description: 了解详细信息： call_in_appdomain 函数
title: call_in_appdomain 函数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- call_in_appdomain
helpviewer_keywords:
- call_in_appdomain function
ms.assetid: 9a1a5026-b76b-4cae-a3d4-29badeb9db9c
ms.openlocfilehash: ece4929e2b99b09f3c9148b50c609ec1b5596b3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282570"
---
# <a name="call_in_appdomain-function"></a>call_in_appdomain 函数

在指定的应用程序域中执行函数。

## <a name="syntax"></a>语法

```
template <typename ArgType1, ...typename ArgTypeN>
void call_in_appdomain(
   DWORD appdomainId,
   void (*voidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
template <typename RetType, typename ArgType1, ...typename ArgTypeN>
RetType call_in_appdomain(
   DWORD appdomainId,
   RetType (*nonvoidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
```

#### <a name="parameters"></a>parameters

*appdomainId*<br/>
要在其中调用函数的 appdomain。

*voidFunc*<br/>
指向一个 **`void`** 函数的指针，该函数采用 N 个参数 (0 <= N <= 15) 。

*nonvoidFunc*<br/>
指向非 **`void`** 函数的指针，该函数采用 N 参数 (0 <= N <= 15) 。

*arg1 .。。argN*<br/>
要传递到 `voidFunc` 或 `nonvoidFunc` 在另一个 appdomain 中的零到15个参数。

## <a name="return-value"></a>返回值

`voidFunc` `nonvoidFunc` 在指定的应用程序域中执行或的结果。

## <a name="remarks"></a>备注

传递给的函数的自变量 `call_in_appdomain` 不得为 CLR 类型。

## <a name="example"></a>示例

```cpp
// msl_call_in_appdomain.cpp
// compile with: /clr

// Defines two functions: one takes a parameter and returns nothing,
// the other takes no parameters and returns an int.  Calls both
// functions in the default appdomain and in a newly-created
// application domain using call_in_appdomain.

#include <msclr\appdomain.h>

using namespace System;
using namespace msclr;

void PrintCurrentDomainName( char* format )
{
   String^ s = gcnew String(format);
   Console::WriteLine( s, AppDomain::CurrentDomain->FriendlyName );
}

int GetDomainId()
{
   return AppDomain::CurrentDomain->Id;
}

int main()
{
   AppDomain^ appDomain1 = AppDomain::CreateDomain( "First Domain" );

   call_in_appdomain( AppDomain::CurrentDomain->Id,
                   &PrintCurrentDomainName,
                   (char*)"default appdomain: {0}" );
   call_in_appdomain( appDomain1->Id,
                   &PrintCurrentDomainName,
                   (char*)"in appDomain1: {0}" );

   int id;
   id = call_in_appdomain( AppDomain::CurrentDomain->Id, &GetDomainId );
   Console::WriteLine( "default appdomain id = {0}", id );
   id = call_in_appdomain( appDomain1->Id, &GetDomainId );
   Console::WriteLine( "appDomain1 id = {0}", id );
}
```

## <a name="output"></a>输出

```
default appdomain: msl_call_in_appdomain.exe
in appDomain1: First Domain
default appdomain id = 1
appDomain1 id = 2
```

## <a name="requirements"></a>要求

**头文件** \<msclr\appdomain.h>

**命名空间** msclr
