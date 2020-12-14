---
description: 了解详细信息：如何：访问 System：： String 中的字符
title: 如何：访问 System::String 中的字符
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: 1959293cc7a984cdce2e1258b2dc6fab0d832267
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335435"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>如何：访问 System::String 中的字符

可以访问对象的字符，以对 <xref:System.String> 采用字符串的非托管函数进行高性能调用 `wchar_t*` 。 方法生成指向对象的第一个字符的内部指针 <xref:System.String> 。 可以直接或固定此指针，并将其传递给需要普通字符串的函数 **`wchar_t`** 。

## <a name="examples"></a>示例

`PtrToStringChars` 返回一个 <xref:System.Char> ，它是 (也称为) 的内部指针 `byref` 。 因此，它可能会进行垃圾回收。 除非要将指针传递到本机函数，否则不需要固定指针。

考虑下列代码。  不需要固定，因为 `ppchar` 是内部指针，如果垃圾回收器移动其指向的字符串，则它也会更新 `ppchar` 。 如果没有 [pin_ptr (c + +/cli) ](../extensions/pin-ptr-cpp-cli.md)，则代码将工作，而不会因固定而导致性能下降。

如果传递 `ppchar` 到本机函数，则它必须是钉住指针; 垃圾回收器将无法更新非托管堆栈帧上的任何指针。

```cpp
// PtrToStringChars.cpp
// compile with: /clr
#include<vcclr.h>
using namespace System;

int main() {
   String ^ mystring = "abcdefg";

   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );

   for ( ; *ppchar != L'\0'; ++ppchar )
      Console::Write(*ppchar);
}
```

```Output
abcdefg
```

此示例演示需要固定的位置。

```cpp
// PtrToStringChars_2.cpp
// compile with: /clr
#include <string.h>
#include <vcclr.h>
// using namespace System;

size_t getlen(System::String ^ s) {
   // Since this is an outside string, we want to be secure.
   // To be secure, we need a maximum size.
   size_t maxsize = 256;
   // make sure it doesn't move during the unmanaged call
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);
   return wcsnlen(pinchars, maxsize);
};

int main() {
   System::Console::WriteLine(getlen("testing"));
}
```

```Output
7
```

内部指针包含本机 c + + 指针的所有属性。 例如，您可以使用它来遍历链接的数据结构，并只使用一个指针执行插入和删除操作：

```cpp
// PtrToStringChars_3.cpp
// compile with: /clr /LD
using namespace System;
ref struct ListNode {
   Int32 elem;
   ListNode ^ Next;
};

void deleteNode( ListNode ^ list, Int32 e ) {
   interior_ptr<ListNode ^> ptrToNext = &list;
   while (*ptrToNext != nullptr) {
      if ( (*ptrToNext) -> elem == e )
         *ptrToNext = (*ptrToNext) -> Next;   // delete node
      else
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node
   }
}
```

## <a name="see-also"></a>请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)
