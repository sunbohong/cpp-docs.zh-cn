---
description: 了解详细信息：如何：在非托管内存中保存对象引用
title: 如何：在非托管内存中保存对象引用
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
ms.openlocfilehash: 9c54d0ce376e57c5865c2fef5987d878bfa8d7f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134922"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>如何：在非托管内存中保存对象引用

可以使用 gcroot <xref:System.Runtime.InteropServices.GCHandle> 来包装，以便在非托管内存中保存 CLR 对象引用。 或者，您可以 `GCHandle` 直接使用。

## <a name="examples"></a>示例

```cpp
// hold_object_reference.cpp
// compile with: /clr
#include "gcroot.h"
using namespace System;

#pragma managed
class StringWrapper {

private:
   gcroot<String ^ > x;

public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      x = str;
   }

   void PrintString() {
      String ^ targetStr = x;
      Console::WriteLine("StringWrapper::x == {0}", targetStr);
   }
};
#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::x == ManagedString
```

`GCHandle` 提供在非托管内存中保存托管对象引用的方法。  使用方法可为 <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> 托管对象创建不透明的句柄并 <xref:System.Runtime.InteropServices.GCHandle.Free%2A> 将其释放。 此外，该 <xref:System.Runtime.InteropServices.GCHandle.Target%2A> 方法还允许您从托管代码中的句柄获取对象引用。

```cpp
// hold_object_reference_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed
class StringWrapper {
   IntPtr m_handle;
public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));
   }
   ~StringWrapper() {
      static_cast<GCHandle>(m_handle).Free();
   }

   void PrintString() {
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);
   }
};

#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::m_handle == ManagedString
```

## <a name="see-also"></a>请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)
