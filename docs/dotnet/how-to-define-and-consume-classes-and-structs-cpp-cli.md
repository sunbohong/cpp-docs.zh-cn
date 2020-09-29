---
title: '如何：在 c + +/CLI 中定义和使用类和结构 () '
description: 如何在 c + +/CLI 代码中创建和使用用户定义的类和结构类型。
ms.date: 09/25/2020
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 17d0885d42febc1d2789c8711b54a76066ee8176
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414576"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>如何：在 c + +/CLI 中定义和使用类和结构 () 

本文介绍如何在 c + +/CLI 中定义和使用用户定义的引用类型和值类型。

## <a name="object-instantiation"></a><a name="BKMK_Object_instantiation"></a> 对象实例化

引用 (引用) 类型只能在托管堆上实例化，而不能在堆栈或本机堆上实例化。 值类型可以在堆栈或托管堆上实例化。

```cpp
// mcppv2_ref_class2.cpp
// compile with: /clr
ref class MyClass {
public:
   int i;

   // nested class
   ref class MyClass2 {
   public:
      int i;
   };

   // nested interface
   interface struct MyInterface {
      void f();
   };
};

ref class MyClass2 : public MyClass::MyInterface {
public:
   virtual void f() {
      System::Console::WriteLine("test");
   }
};

public value struct MyStruct {
   void f() {
      System::Console::WriteLine("test");
   }
};

int main() {
   // instantiate ref type on garbage-collected heap
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass -> i = 4;

   // instantiate value type on garbage-collected heap
   MyStruct ^ p_MyStruct = gcnew MyStruct;
   p_MyStruct -> f();

   // instantiate value type on the stack
   MyStruct p_MyStruct2;
   p_MyStruct2.f();

   // instantiate nested ref type on garbage-collected heap
   MyClass::MyClass2 ^ p_MyClass2 = gcnew MyClass::MyClass2;
   p_MyClass2 -> i = 5;
}
```

## <a name="implicitly-abstract-classes"></a><a name="BKMK_Implicitly_abstract_classes"></a> 隐式抽象类

*隐式抽象类*不能实例化。 类在以下情况中是隐式抽象的：

- 类的基类型是接口，
- 类不实现所有接口的成员函数。

您可能无法从从接口派生的类构造对象。 这可能是因为该类是隐式抽象的。 有关抽象类的详细信息，请参阅 [abstract](../extensions/abstract-cpp-component-extensions.md)。

下面的代码示例演示了 `MyClass` 由于未实现函数而无法实例化类 `MyClass::func2` 。 若要使此示例能够编译，请取消注释 `MyClass::func2` 。

```cpp
// mcppv2_ref_class5.cpp
// compile with: /clr
interface struct MyInterface {
   void func1();
   void func2();
};

ref class MyClass : public MyInterface {
public:
   void func1(){}
   // void func2(){}
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;   // C2259
                                          // To resolve, uncomment MyClass::func2.
}
```

## <a name="type-visibility"></a><a name="BKMK_Type_visibility"></a> 类型可见性

可以 (CLR) 类型控制公共语言运行时的可见性。 引用程序集时，您可以控制程序集中的类型是可见还是在程序集外可见。

`public` 指示类型对包含包含该类型的程序集的指令的任何源文件都可见 `#using` 。  `private` 指示类型对包含 `#using` 类型的程序集的指令的源文件不可见。 但是，私有类型在同一程序集中可见。 默认情况下，类的可见性为 `private` 。

默认情况下，在 Visual Studio 2005 之前，本机类型在程序集外具有公共可访问性。 启用 [编译器警告 (级别 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) ，以帮助你了解不正确使用私有本机类型的位置。 使用 [make_public](../preprocessor/make-public.md) 杂注向源代码文件中无法修改的本机类型授予公共可访问性。

有关详细信息，请参阅 [#using 指令](../preprocessor/hash-using-directive-cpp.md)。

下面的示例演示如何声明类型并指定其可访问性，然后访问程序集内的这些类型。 如果使用引用具有私有类型的程序集，则 `#using` 只有程序集中的公共类型可见。

```cpp
// type_visibility.cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// default accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   Private_Class ^ b = gcnew Private_Class;
   b->Test();

   Private_Class_2 ^ c = gcnew Private_Class_2;
   c->Test();
}
```

**输出**

```Output
in Public_Class
in Private_Class
in Private_Class_2
```

现在，我们将重写上一个示例，使其构建为 DLL。

```cpp
// type_visibility_2.cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside the assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// by default, accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};
```

下一个示例演示如何访问程序集外部的类型。 在此示例中，客户端使用在前面的示例中生成的组件。

```cpp
// type_visibility_3.cpp
// compile with: /clr
#using "type_visibility_2.dll"
int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   // private types not accessible outside the assembly
   // Private_Class ^ b = gcnew Private_Class;
   // Private_Class_2 ^ c = gcnew Private_Class_2;
}
```

**输出**

```Output
in Public_Class
```

## <a name="member-visibility"></a><a name="BKMK_Member_visibility"></a> 成员可见性

您可以通过使用一对访问说明符 **`public`** 、和，从程序集外部访问公共类的成员，而不是从程序集访问它。 **`protected`****`private`**

下表总结了各种访问说明符的影响：

|说明符|效果|
|---------------|------------|
|`public`|可在程序集内部和外部访问成员。 有关详细信息，请参阅 [`public`](../cpp/public-cpp.md)。|
|`private`|在程序集的内部和外部无法访问成员。  有关详细信息，请参阅 [`private`](../cpp/private-cpp.md)。|
|`protected`|成员可在程序集内部和外部访问，但只能用于派生类型。 有关详细信息，请参阅 [`protected`](../cpp/protected-cpp.md)。|
|`internal`|成员在程序集内部是公共的，而在程序集外是私有的。 `internal` 是上下文相关的关键字。  有关详细信息，请参阅[上下文相关关键字](../extensions/context-sensitive-keywords-cpp-component-extensions.md)。|
|`public protected` - 或 - `protected public`|成员在程序集内部是公共的，但在程序集外受到保护。|
|`private protected` - 或 - `protected private`|成员在程序集内受到保护，但在程序集外是私有的。|

下面的示例演示包含使用不同访问说明符声明的成员的公共类型。 然后，它会显示从程序集内部对这些成员的访问权限。

```cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();
   a->Protected_Public_Function();
   a->Public_Protected_Function();

   // accessible inside but not outside the assembly
   a->Internal_Function();

   // call protected functions
   b->Test();

   // not accessible inside or outside the assembly
   // a->Private_Function();
}
```

**输出**

```Output
in Public_Function
in Protected_Public_Function
in Public_Protected_Function
in Internal_Function
=======================
in function of derived class
in Protected_Function
in Protected_Private_Function
in Private_Protected_Function
exiting function of derived class
=======================
```

现在，让我们以 DLL 形式构建上一个示例。

```cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};
```

下面的示例使用在前面的示例中创建的组件。 它演示如何从程序集外部访问成员。

```cpp
// compile with: /clr
#using "type_member_visibility_2.dll"
using namespace System;
// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Public_Function();
      Public_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();

   // call protected functions
   b->Test();

   // can't be called outside the assembly
   // a->Private_Function();
   // a->Internal_Function();
   // a->Protected_Private_Function();
   // a->Private_Protected_Function();
}
```

**输出**

```Output
in Public_Function
=======================
in function of derived class
in Protected_Function
in Protected_Public_Function
in Public_Protected_Function
exiting function of derived class
=======================
```

## <a name="public-and-private-native-classes"></a><a name="BKMK_Public_and_private_native_classes"></a> 公共和私有本机类

可以从托管类型引用本机类型。  例如，托管类型中的函数可以采用类型为本机结构的参数。  如果托管类型和函数在程序集中是公共的，则本机类型必须也是公共的。

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

接下来，创建使用本机类型的源代码文件：

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

现在，编译客户端：

```cpp
// compile with: /clr
#using "mcppv2_ref_class3.dll"

#include "mcppv2_ref_class3.h"

int main() {
   R ^r = gcnew R;
   N n;
   r->f(n);
}
```

## <a name="static-constructors"></a><a name="BKMK_Static_constructors"></a> 静态构造函数

CLR 类型（例如类或结构）可以具有可用于初始化静态数据成员的静态构造函数。  静态构造函数最多调用一次，并在第一次访问该类型的任何静态成员之前调用。

实例构造函数始终在静态构造函数之后运行。

如果类具有静态构造函数，则编译器不能内联对构造函数的调用。 如果类是值类型，它具有静态构造函数，并且不具有实例构造函数，则编译器无法以内联方式调用任何成员函数。 CLR 可能内联调用，但编译器不能。

将静态构造函数定义为私有成员函数，因为它只是由 CLR 调用。

有关静态构造函数的详细信息，请参阅 [如何：在 c + +/cli)  (定义接口静态构造函数 ](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) 。

```cpp
// compile with: /clr
using namespace System;

ref class MyClass {
private:
   static int i = 0;

   static MyClass() {
      Console::WriteLine("in static constructor");
      i = 9;
   }

public:
   static void Test() {
      i++;
      Console::WriteLine(i);
   }
};

int main() {
   MyClass::Test();
   MyClass::Test();
}
```

**输出**

```Output
in static constructor
10
11
```

## <a name="semantics-of-the-this-pointer"></a><a name="BKMK_Semantics_of_the_this_pointer"></a>指针的语义 `this`

使用 c + + \CLI 定义类型时， **`this`** 引用类型中的指针为类型 *句柄*。 **`this`** 值类型中的指针为*内部指针*类型。

**`this`** 当调用默认索引器时，指针的这些不同的语义可能导致意外的行为。 下一个示例演示了访问引用类型和值类型中的默认索引器的正确方法。

有关详细信息，请参阅 [对象操作员的 Handle (^) ](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) 和 [Interior_ptr (c + +/cli) ](../extensions/interior-ptr-cpp-cli.md)

```cpp
// compile with: /clr
using namespace System;

ref struct A {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }

   A() {
      // accessing default indexer
      Console::WriteLine("{0}", this[3.3]);
   }
};

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      // accessing default indexer
      Console::WriteLine("{0}", this->default[3.3]);
   }
};

int main() {
   A ^ mya = gcnew A();
   B ^ myb = gcnew B();
   myb->Test();
}
```

**输出**

```Output
10.89
10.89
```

## <a name="hide-by-signature-functions"></a><a name="BKMK_Hide_by_signature_functions"></a> 按签名隐藏函数

在标准 c + + 中，基类中的函数由派生类中具有相同名称的函数隐藏，即使派生类函数没有相同的类型或数量的参数也是如此。 这称为 *按名称隐藏* 语义。 在引用类型中，如果名称和参数列表相同，基类中的函数将仅由派生类中的函数隐藏。 这称为 " *按签名隐藏* " 语义。

当某个类的所有函数在元数据中标记为时，该类被视为隐藏签名类 `hidebysig` 。 默认情况下，在下创建的所有类 **`/clr`** 都具有 `hidebysig` 函数。 当某个类具有 `hidebysig` 函数时，编译器不会按名称隐藏任何直接基类中的函数，但如果编译器遇到继承链中的按名称隐藏的类，它将继续以名称隐藏的行为。

在对对象调用函数时，如果在对象上调用函数，则编译器会标识包含可满足函数调用的函数的派生程度为 如果类中只有一个函数满足调用，则编译器将调用该函数。 如果类中有多个函数可满足调用，编译器将使用重载决策规则来确定要调用的函数。 有关重载规则的详细信息，请参阅 [函数重载](../cpp/function-overloading.md)。

对于给定的函数调用，基类中的函数可能具有使其比派生类中的函数稍微更好的匹配项的签名。 但是，如果在派生类的对象上显式调用了函数，则调用派生类中的函数。

因为返回值不被视为函数签名的一部分，所以如果基类函数具有相同的名称并且采用与派生类函数相同的类型和数量的自变量，则该函数将被隐藏，即使返回值的类型不同也是如此。

下面的示例显示基类中的函数未被派生类中的函数隐藏。

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test() {
      Console::WriteLine("Base::Test");
   }
};

ref struct Derived : public Base {
   void Test(int i) {
      Console::WriteLine("Derived::Test");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Test() in the base class will not be hidden
   t->Test();
}
```

**输出**

```Output
Base::Test
```

下一个示例显示，Microsoft c + + 编译器在派生程度最高的类中调用函数，即使需要转换才能匹配一个或多个参数，并且不调用基类中的函数，该函数调用的匹配更好。

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test2(Single d) {
      Console::WriteLine("Base::Test2");
   }
};

ref struct Derived : public Base {
   void Test2(Double f) {
      Console::WriteLine("Derived::Test2");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Base::Test2 is a better match, but the compiler
   // calls a function in the derived class if possible
   t->Test2(3.14f);
}
```

**输出**

```Output
Derived::Test2
```

下面的示例演示即使基类与派生类具有相同的签名，也可以隐藏函数。

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   int Test4() {
      Console::WriteLine("Base::Test4");
      return 9;
   }
};

ref struct Derived : public Base {
   char Test4() {
      Console::WriteLine("Derived::Test4");
      return 'a';
   }
};

int main() {
   Derived ^ t = gcnew Derived;

   // Base::Test4 is hidden
   int i = t->Test4();
   Console::WriteLine(i);
}
```

**输出**

```Output
Derived::Test4
97
```

## <a name="copy-constructors"></a><a name="BKMK_Copy_constructors"></a> 复制构造函数

C + + 标准表明在移动对象时调用了复制构造函数，以便在同一地址创建并销毁对象。

但是，当编译为 MSIL 的函数调用本机函数，其中本机类（或多个）按值传递，其中本机类具有复制构造函数或析构函数时，不会调用任何复制构造函数，并且会在不同于创建对象的地址处销毁对象。 如果类具有一个指向自身的指针，或者如果代码按地址跟踪对象，则此行为可能会导致问题。

有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md)。

下面的示例演示了复制构造函数不生成的时间。

```cpp
// compile with: /clr
#include<stdio.h>

struct S {
   int i;
   static int n;

   S() : i(n++) {
      printf_s("S object %d being constructed, this=%p\n", i, this);
   }

   S(S const& rhs) : i(n++) {
      printf_s("S object %d being copy constructed from S object "
               "%d, this=%p\n", i, rhs.i, this);
   }

   ~S() {
      printf_s("S object %d being destroyed, this=%p\n", i, this);
   }
};

int S::n = 0;

#pragma managed(push,off)
void f(S s1, S s2) {
   printf_s("in function f\n");
}
#pragma managed(pop)

int main() {
   S s;
   S t;
   f(s,t);
}
```

**输出**

```Output
S object 0 being constructed, this=0018F378
S object 1 being constructed, this=0018F37C
S object 2 being copy constructed from S object 1, this=0018F380
S object 3 being copy constructed from S object 0, this=0018F384
S object 4 being copy constructed from S object 2, this=0018F2E4
S object 2 being destroyed, this=0018F380
S object 5 being copy constructed from S object 3, this=0018F2E0
S object 3 being destroyed, this=0018F384
in function f
S object 5 being destroyed, this=0018F2E0
S object 4 being destroyed, this=0018F2E4
S object 1 being destroyed, this=0018F37C
S object 0 being destroyed, this=0018F378
```

## <a name="destructors-and-finalizers"></a><a name="BKMK_Destructors_and_finalizers"></a> 析构函数和终结器

引用类型中的析构函数对资源进行确定性的清理。 终结器清除非托管资源，并可由析构函数或不确定地由垃圾回收器确定。 有关标准 c + + 中的析构函数的信息，请参阅 [析构函数](../cpp/destructors-cpp.md)。

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

CLR 垃圾回收器会删除未使用的托管对象并在不再需要时释放其内存。 但是，类型可以使用垃圾回收器不知道如何释放的资源。 这些资源称为 *非托管* 资源 (本机文件句柄，例如) 。 建议释放终结器中的所有非托管资源。 垃圾回收器释放托管资源不确定地，因此在终结器中引用托管资源是不安全的。 这是因为垃圾回收器可能已清除了这些文件。

Visual C++ 终结器与 <xref:System.Object.Finalize%2A> 方法不同。  (CLR 文档使用终结器和 <xref:System.Object.Finalize%2A> 方法同义词) 。 此 <xref:System.Object.Finalize%2A> 方法由垃圾回收器调用，该回收器调用类继承链中的每个终结器。 与 Visual C++ 析构函数不同，派生类的终结器调用不会导致编译器在所有基类中调用终结器。

由于 Microsoft c + + 编译器支持资源的确定性释放，因此不要尝试实现 <xref:System.IDisposable.Dispose%2A> 或 <xref:System.Object.Finalize%2A> 方法。 但是，如果你熟悉这些方法，以下是 Visual C++ 终结器和调用终结器的析构函数映射到模式的方式 <xref:System.IDisposable.Dispose%2A> ：

```cpp
// Visual C++ code
ref class T {
   ~T() { this->!T(); }   // destructor calls finalizer
   !T() {}   // finalizer
};

// equivalent to the Dispose pattern
void Dispose(bool disposing) {
   if (disposing) {
      ~T();
   } else {
      !T();
   }
}
```

托管类型也可以使用您希望确定的托管资源。 当不再需要对象时，你可能不希望垃圾回收器释放对象不确定地。 资源的确定性版本可显著提高性能。

Microsoft c + + 编译器启用析构函数的定义，以明确地清理对象。 使用析构函数释放你要确定的发布的所有资源。  如果存在终结器，则从析构函数调用它以避免代码重复。

```cpp
// compile with: /clr /c
ref struct A {
   // destructor cleans up all resources
   ~A() {
      // clean up code to release managed resource
      // ...
      // to avoid code duplication,
      // call finalizer to release unmanaged resources
      this->!A();
   }

   // finalizer cleans up unmanaged resources
   // destructor or garbage collector will
   // clean up managed resources
   !A() {
      // clean up code to release unmanaged resources
      // ...
   }
};
```

如果使用类型的代码不会调用析构函数，则垃圾回收器最终会释放所有托管资源。

析构函数的存在并不表示存在终结器。 但是，如果存在终结器，则意味着必须定义析构函数并从该析构函数调用终结器。 此调用提供非托管资源的确定性释放。

调用析构函数会取消对象的终止（通过使用 <xref:System.GC.SuppressFinalize%2A> ）。 如果未调用析构函数，则会最终由垃圾回收器调用类型的终结器。

可以通过调用析构函数来确定对象的资源，而不是让 CLR 不确定地完成对象，从而提高性能。

在以下情况中，使用在 Visual C++ 中编写并使用编译的代码 **`/clr`** 运行类型的析构函数：

- 使用堆栈语义创建的对象不在范围内。 有关详细信息，请参阅 [引用类型的 c + + 堆栈语义](../dotnet/cpp-stack-semantics-for-reference-types.md)。

- 对象的构造过程中会引发异常。

- 对象是其析构函数正在运行的对象中的成员。

- 对对象运算符 (句柄调用 [delete](../cpp/delete-operator-cpp.md) 运算符 [ (^) ](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)) 。

- 显式调用析构函数。

如果使用另一种语言编写的客户端使用您的类型，则会调用析构函数，如下所示：

- 在调用时 <xref:System.IDisposable.Dispose%2A> 。

- 对类型调用时 `Dispose(void)` 。

- 如果类型在 c # 语句中超出范围，则为 **`using`** 。

如果未对引用类型使用 stack 语义并在托管堆上创建引用类型的对象，请使用 [try-finally](../cpp/try-finally-statement.md) 语法确保异常不会阻止析构函数运行。

```cpp
// compile with: /clr
ref struct A {
   ~A() {}
};

int main() {
   A ^ MyA = gcnew A;
   try {
      // use MyA
   }
   finally {
      delete MyA;
   }
}
```

如果类型具有析构函数，则编译器将生成一个 `Dispose` 实现的方法 <xref:System.IDisposable> 。 如果使用编写的类型 Visual C++ 并具有从另一种语言中使用的析构函数，则 `IDisposable::Dispose` 对该类型调用将导致调用该类型的析构函数。 当从 Visual C++ 客户端使用该类型时，不能直接调用 `Dispose` ，而是使用运算符调用析构函数 **`delete`** 。

如果类型具有终结器，则编译器将生成一个 `Finalize(void)` 重写的方法 <xref:System.Object.Finalize%2A> 。

如果类型具有终结器或析构函数，则编译器将 `Dispose(bool)` 根据设计模式生成方法。  (信息，请参阅 [Dispose 模式](/dotnet/standard/design-guidelines/dispose-pattern)) 。 无法在 Visual C++ 中显式创作或调用 `Dispose(bool)` 。

如果某个类型具有符合设计模式的基类，则在调用派生类的析构函数时，将调用所有基类的析构函数。  (如果您的类型是使用 Visual C++ 编写的，则编译器将确保您的类型实现此模式。 ) 换句话说，引用类的析构函数会按照 c + + 标准的指定链接到其基和成员。 首先，运行类的析构函数。 然后，其成员的析构函数将以其构造顺序相反的顺序运行。 最后，其基类的析构函数将以其构造顺序相反的顺序运行。

不允许在值类型或接口内使用析构函数和终结器。

终结器只能在引用类型中定义或声明。 与构造函数和析构函数一样，终结器没有返回类型。

对象的终结器运行后，还会调用任何基类中的终结器（从派生程度最小的类型开始）。 类的终结器不会自动链接数据成员的终结器。

如果终结器删除托管类型中的本机指针，则必须确保不会提前收集对本机指针或本机指针的引用。 对托管类型调用析构函数，而不是使用 <xref:System.GC.KeepAlive%2A> 。

在编译时，可以检测某一类型是否具有终结器或析构函数。 有关详细信息，请参阅[编译器对类型特征的支持](../extensions/compiler-support-for-type-traits-cpp-component-extensions.md)。

下一个示例显示了两种类型：一个具有非托管资源，另一个具有可确定释放的托管资源。

```cpp
// compile with: /clr
#include <vcclr.h>
#include <stdio.h>
using namespace System;
using namespace System::IO;

ref class SystemFileWriter {
   FileStream ^ file;
   array<Byte> ^ arr;
   int bufLen;

public:
   SystemFileWriter(String ^ name) : file(File::Open(name, FileMode::Append)),
                                     arr(gcnew array<Byte>(1024)) {}

   void Flush() {
      file->Write(arr, 0, bufLen);
      bufLen = 0;
   }

   ~SystemFileWriter() {
      Flush();
      delete file;
   }
};

ref class CRTFileWriter {
   FILE * file;
   array<Byte> ^ arr;
   int bufLen;

   static FILE * getFile(String ^ n) {
      pin_ptr<const wchar_t> name = PtrToStringChars(n);
      FILE * ret = 0;
      _wfopen_s(&ret, name, L"ab");
      return ret;
   }

public:
   CRTFileWriter(String ^ name) : file(getFile(name)), arr(gcnew array<Byte>(1024) ) {}

   void Flush() {
      pin_ptr<Byte> buf = &arr[0];
      fwrite(buf, 1, bufLen, file);
      bufLen = 0;
   }

   ~CRTFileWriter() {
      this->!CRTFileWriter();
   }

   !CRTFileWriter() {
      Flush();
      fclose(file);
   }
};

int main() {
   SystemFileWriter w("systest.txt");
   CRTFileWriter ^ w2 = gcnew CRTFileWriter("crttest.txt");
}
```

## <a name="see-also"></a>另请参阅

[类和结构](../extensions/classes-and-structs-cpp-component-extensions.md)
