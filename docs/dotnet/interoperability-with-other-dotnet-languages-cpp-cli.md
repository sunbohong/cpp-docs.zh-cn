---
description: '了解更多详细信息：与其他 .NET 语言的互操作性 (c + +/CLI) '
title: 与其他 .NET 语言的互操作性 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- C++, indexers
- indexers, consuming C#
- as C# keyword [C++]
- is C# keyword [C++]
- lock statement
- lock C# keyword [C++]
ms.assetid: a5902cf8-a14d-4559-aefb-c178615d45bb
ms.openlocfilehash: 51cead7fcc7dedc05f0225facf10fe70a3d606fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316604"
---
# <a name="interoperability-with-other-net-languages-ccli"></a>与其他 .NET 语言的互操作性 (C++/CLI)

本节中的主题说明如何在 Visual C++ 中创建使用的程序集，或向用 c # 或 Visual Basic 编写的程序集提供功能。

## <a name="consume-a-c-indexer"></a><a name="consume_indexer"></a> 使用 c # 索引器

Visual C++ 不包含索引器;它包含索引属性。 若要使用 c # 索引器，请访问索引器，就像它是索引属性一样。

有关索引器的详细信息，请参阅：

- [索引器](/dotnet/csharp/programming-guide/indexers/index)

### <a name="example"></a>示例

下面的 c # 程序定义索引器。

```csharp
// consume_cs_indexers.cs
// compile with: /target:library
using System;
public class IndexerClass {
   private int [] myArray = new int[100];
   public int this [int index] {   // Indexer declaration
      get {
         // Check the index limits.
         if (index < 0 || index >= 100)
            return 0;
         else
            return myArray[index];
      }
      set {
         if (!(index < 0 || index >= 100))
            myArray[index] = value;
      }
   }
}
/*
// code to consume the indexer
public class MainClass {
   public static void Main() {
      IndexerClass b = new IndexerClass();

      // Call indexer to initialize elements 3 and 5
      b[3] = 256;
      b[5] = 1024;
      for (int i = 0 ; i <= 10 ; i++)
         Console.WriteLine("Element #{0} = {1}", i, b[i]);
   }
}
*/
```

### <a name="example"></a>示例

此 Visual C++ 程序使用索引器。

```cpp
// consume_cs_indexers_2.cpp
// compile with: /clr
#using "consume_cs_indexers.dll"
using namespace System;

int main() {
   IndexerClass ^ ic = gcnew IndexerClass;
   ic->default[0] = 21;
   for (int i = 0 ; i <= 10 ; i++)
      Console::WriteLine("Element #{0} = {1}", i, ic->default[i]);
}
```

```Output
Element #0 = 21
Element #1 = 0
Element #2 = 0
Element #3 = 0
Element #4 = 0
Element #5 = 0
Element #6 = 0
Element #7 = 0
Element #8 = 0
Element #9 = 0
Element #10 = 0
```

## <a name="implement-is-and-as-c-keywords"></a><a name="implement_isas"></a> 实现 is 和 as c # 关键字

本主题演示如何 `is` `as` 在 Visual C++ 中实现和 c # 关键字的功能。

### <a name="example"></a>示例

```cpp
// CS_is_as.cpp
// compile with: /clr
using namespace System;

interface class I {
public:
   void F();
};

ref struct C : public I {
   virtual void F( void ) { }
};

template < class T, class U >
Boolean isinst(U u) {
   return dynamic_cast< T >(u) != nullptr;
}

int main() {
   C ^ c = gcnew C();
   I ^ i = safe_cast< I ^ >(c);   // is (maps to castclass in IL)
   I ^ ii = dynamic_cast< I ^ >(c);   // as (maps to isinst in IL)

   // simulate 'as':
   Object ^ o = "f";
   if ( isinst< String ^ >(o) )
      Console::WriteLine("o is a string");
}
```

```Output
o is a string
```

## <a name="implement-the-lock-c-keyword"></a><a name="implement_locak"></a> 实现 lock c # 关键字

本主题演示如何 `lock` 在 Visual C++ 中实现 c # 关键字。

你还可以使用 `lock` c + + 支持库中的类。 有关详细信息，请参阅 [同步 (锁定类) ](../dotnet/synchronization-lock-class.md) 。

### <a name="example"></a>示例

```cpp
// CS_lock_in_CPP.cpp
// compile with: /clr
using namespace System::Threading;
ref class Lock {
   Object^ m_pObject;
public:
   Lock( Object ^ pObject ) : m_pObject( pObject ) {
      Monitor::Enter( m_pObject );
   }
   ~Lock() {
      Monitor::Exit( m_pObject );
   }
};

ref struct LockHelper {
   void DoSomething();
};

void LockHelper::DoSomething() {
   // Note: Reference type with stack allocation semantics to provide
   // deterministic finalization

   Lock lock( this );
   // LockHelper instance is locked
}

int main()
{
   LockHelper lockHelper;
   lockHelper.DoSomething();
   return 0;
}
```

## <a name="see-also"></a>请参阅

[用 c + +/CLI (Visual C++ 的 .NET 编程) ](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
