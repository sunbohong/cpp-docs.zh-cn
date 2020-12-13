---
description: 了解详细信息： ConvertBSTRToString
title: ConvertBSTRToString
ms.date: 11/04/2016
f1_keywords:
- ConvertBSTRToString
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
ms.openlocfilehash: 72d6033003f186f358d9b4143498df65858ee354
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344609"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString

**Microsoft 专用**

将 `BSTR` 值转换为 `char *`。

## <a name="syntax"></a>语法

```
char* __stdcall ConvertBSTRToString(BSTR pSrc);
```

#### <a name="parameters"></a>parameters

*.Psrc*<br/>
BSTR 变量。

## <a name="remarks"></a>备注

**ConvertBSTRToString** 分配必须删除的字符串。

## <a name="example"></a>示例

```cpp
// ConvertBSTRToString.cpp
#include <comutil.h>
#include <stdio.h>

#pragma comment(lib, "comsuppw.lib")

int main() {
   BSTR bstrText = ::SysAllocString(L"Test");
   wprintf_s(L"BSTR text: %s\n", bstrText);

   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);
   printf_s("char * text: %s\n", lpszText2);

   SysFreeString(bstrText);
   delete[] lpszText2;
}
```

```Output
BSTR text: Test
char * text: Test
```

**结束 Microsoft 专用**

## <a name="requirements"></a>要求

**标头：**\<comutil.h>

**Lib：** comsuppw.lib 或 comsuppwd.lib (参阅 [/zc： Wchar_t (Wchar_t 是本机类型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 有关详细信息) 

## <a name="see-also"></a>请参阅

[编译器 COM 全局函数](../cpp/compiler-com-global-functions.md)
