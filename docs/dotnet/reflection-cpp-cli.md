---
description: '了解详细信息：反射 (c + +/CLI) '
title: 反射 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
- plug-ins [C++]
- reflection [C++}, plug-ins
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
ms.openlocfilehash: a3a9a33a239ec678279455ea41b7c60749cc0189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245793"
---
# <a name="reflection-ccli"></a>反射 (C++/CLI)

反射允许在运行时检查已知的数据类型。 反射允许枚举给定程序集中的数据类型，并且可以发现给定类或值类型的成员。 无论在编译时是已知类型还是引用类型，都是如此。 这使得反射成为开发和代码管理工具的一项有用功能。

请注意，提供的程序集名称是强名称 (请参阅 [创建和使用 Strong-Named 程序集](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)) ，其中包括程序集版本、区域性和签名信息。 另请注意，可在其中定义数据类型的命名空间的名称，以及基类的名称。

访问反射功能最常见的方法是通过 <xref:System.Object.GetType%2A> 方法。 此方法由提供 <xref:System.Object?displayProperty=nameWithType> ，所有垃圾回收类都从中派生。

> [!NOTE]
> 仅当使用 **/clr： pure** 或 **/clr： safe** 编译器选项生成 .exe 时，才允许在使用 Microsoft c + + 编译器生成的 .exe 上进行反射。 **/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不可用。 有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md) 。

有关详细信息，请参阅<xref:System.Reflection>。

## <a name="example-gettype"></a>示例： GetType

`GetType`方法返回指向类对象的指针 <xref:System.Type> ，该对象描述对象所基于的类型。  (**类型** 对象不包含任何特定于实例的信息。 ) 一个此类项是类型的完整名称，可按如下方式显示：

请注意，类型名称包括定义该类型的完整范围（包括命名空间），并以 .NET 语法显示，用点作为范围解析运算符。

```cpp
// vcpp_reflection.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^ s = "sample string";
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());
}
```

```Output
full type name of 'sample string' is 'System.String'
```

## <a name="example-boxed-value-types"></a>示例：装箱值类型

值类型也可以与函数一起使用 `GetType` ，但必须先将值类型装箱。

```cpp
// vcpp_reflection_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Int32 i = 100;
   Object ^ o = i;
   Console::WriteLine("type of i = '{0}'", o->GetType());
}
```

```Output
type of i = 'System.Int32'
```

## <a name="example-typeid"></a>示例： typeid

与方法一样 `GetType` ， [typeid](../extensions/typeid-cpp-component-extensions.md) 运算符返回指向 **类型** 对象的指针，因此此代码指示类型名称 **system.object**。 显示类型名称是反射的最基本的功能，但可能更有用的方法是检查或发现枚举类型的有效值。 这可以通过使用静态 **Enum：： GetNames** 函数来完成，该函数返回一个字符串数组，每个字符串都包含一个文本格式的枚举值。  下面的示例检索一个字符串数组，该数组描述 (CLR) 枚举的 **选项** 的值枚举值并将它们显示在一个循环中。

如果在 **选项** 枚举中添加了第四个选项，则此代码将报告新选项而不重新编译，即使枚举是在单独的程序集中定义的也是如此。

```cpp
// vcpp_reflection_3.cpp
// compile with: /clr
using namespace System;

enum class Options {   // not a native enum
   Option1, Option2, Option3
};

int main() {
   array<String^>^ names = Enum::GetNames(Options::typeid);

   Console::WriteLine("there are {0} options in enum '{1}'",
               names->Length, Options::typeid);

   for (int i = 0 ; i < names->Length ; i++)
      Console::WriteLine("{0}: {1}", i, names[i]);

   Options o = Options::Option2;
   Console::WriteLine("value of 'o' is {0}", o);
}
```

```Output
there are 3 options in enum 'Options'
0: Option1
1: Option2
2: Option3
value of 'o' is Option2
```

## <a name="example-gettype-members-and-properties"></a>示例： GetType 成员和属性

`GetType`对象支持多个可用于检查类型的成员和属性。 此代码检索并显示以下信息：

```cpp
// vcpp_reflection_4.cpp
// compile with: /clr
using namespace System;
int main() {
   Console::WriteLine("type information for 'String':");
   Type ^ t = String::typeid;

   String ^ assemblyName = t->Assembly->FullName;
   Console::WriteLine("assembly name: {0}", assemblyName);

   String ^ nameSpace = t->Namespace;
   Console::WriteLine("namespace: {0}", nameSpace);

   String ^ baseType = t->BaseType->FullName;
   Console::WriteLine("base type: {0}", baseType);

   bool isArray = t->IsArray;
   Console::WriteLine("is array: {0}", isArray);

   bool isClass = t->IsClass;
   Console::WriteLine("is class: {0}", isClass);
}
```

```Output
type information for 'String':
assembly name: mscorlib, Version=1.0.5000.0, Culture=neutral,
PublicKeyToken=b77a5c561934e089
namespace: System
base type: System.Object
is array: False
is class: True
```

## <a name="example-enumeration-of-types"></a>示例：类型的枚举

反射还允许枚举程序集中的类型和类中的成员。 若要演示此功能，请定义一个简单的类：

```cpp
// vcpp_reflection_5.cpp
// compile with: /clr /LD
using namespace System;
public ref class TestClass {
   int m_i;
public:
   TestClass() {}
   void SimpleTestMember1() {}
   String ^ SimpleMember2(String ^ s) { return s; }
   int TestMember(int i) { return i; }
   property int Member {
      int get() { return m_i; }
      void set(int i) { m_i = i; }
   }
};
```

## <a name="example-inspection-of-assemblies"></a>示例：检查程序集

如果上面的代码编译到名为 vcpp_reflection_6.dll 的 DLL 中，则可以使用反射来检查此程序集的内容。 这涉及到使用静态反射 API 函数 x： displayProperty% 2A？ = Namewithtype> 加载程序集。 此函数返回 **程序集** 对象的地址，然后可以查询该对象中有关模块和类型的信息。

反射系统成功加载程序集后，将使用函数检索 **类型** 对象的数组 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> 。 每个数组元素都包含不同类型的相关信息，但在这种情况下，只定义了一个类。 使用循环时，将使用 **type：： GetMembers** 函数查询此数组中的每个 **类型** 有关类型成员的信息。 此函数返回 **MethodInfo** 对象的数组，每个对象都包含有关该类型中的成员函数、数据成员或属性的信息。

请注意，方法的列表包括 **TestClass** 中显式定义的函数，以及从 **System：： Object** 类隐式继承的函数。 作为在 .NET 中描述的一部分，而不是在 Visual C++ 语法中，属性显示为 get/set 函数访问的基础数据成员。 Get/set 函数在此列表中显示为常规方法。 反射支持通过公共语言运行时，而不是 Microsoft c + + 编译器。

尽管你使用此代码来检查你定义的程序集，但你也可以使用此代码来检查 .NET 程序集。 例如，如果将 TestAssembly 更改为 mscorlib，则会看到在 mscorlib.dll 中定义的每个类型和方法的列表。

```cpp
// vcpp_reflection_6.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;
using namespace System::Reflection;
int main() {
   Assembly ^ a = nullptr;
   try {
      // load assembly -- do not use file extension
      // will look for .dll extension first
      // then .exe with the filename
      a = Assembly::Load("vcpp_reflection_5");
   }
   catch (FileNotFoundException ^ e) {
      Console::WriteLine(e->Message);
      return -1;
   }

   Console::WriteLine("assembly info:");
   Console::WriteLine(a->FullName);
   array<Type^>^ typeArray = a->GetTypes();

   Console::WriteLine("type info ({0} types):", typeArray->Length);

   int totalTypes = 0;
   int totalMembers = 0;
   for (int i = 0 ; i < typeArray->Length ; i++) {
      // retrieve array of member descriptions
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();

      Console::WriteLine("  members of {0} ({1} members):",
      typeArray[i]->FullName, member->Length);
      for (int j = 0 ; j < member->Length ; j++) {
         Console::Write("       ({0})",
         member[j]->MemberType.ToString() );
         Console::Write("{0}  ", member[j]);
         Console::WriteLine("");
         totalMembers++;
      }
      totalTypes++;
   }
   Console::WriteLine("{0} total types, {1} total members",
   totalTypes, totalMembers);
}
```

## <a name="how-to-implement-a-plug-in-component-architecture-using-reflection"></a><a name="implement"></a> 如何：使用反射实现 Plug-In 组件体系结构

下面的代码示例演示如何使用反射来实现简单的 "插件" 体系结构。 第一个列表是应用程序，第二个列表是插件。 应用程序是一种多文档窗体，该窗体使用在作为命令行参数提供的插件 DLL 中找到的任何基于窗体的类进行填充。

应用程序尝试使用方法加载提供的程序集 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 。 如果成功，则使用方法枚举程序集内的类型 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> 。 然后，使用方法检查每个类型的兼容性 <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> 。 在此示例中，在提供的程序集中找到的类必须从 <xref:System.Windows.Forms.Form> 类派生，才能作为插件。

然后使用方法实例化兼容的类 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> ，该方法接受 <xref:System.Type> 作为参数，并返回指向新实例的指针。 然后，每个新实例都附加到窗体并显示。

请注意， <xref:System.Reflection.Assembly.Load%2A> 方法不接受包含文件扩展名的程序集名称。 应用程序中的 main 函数剪裁任何提供的扩展，因此下面的代码示例适用于这两种情况。

### <a name="example"></a>示例

下面的代码定义了接受插件的应用程序。必须提供程序集名称作为第一个参数。 此程序集应包含至少一个公共 <xref:System.Windows.Forms.Form> 派生类型。

```cpp
// plugin_application.cpp
// compile with: /clr /c
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;

ref class PluggableForm : public Form  {
public:
   PluggableForm() {}
   PluggableForm(Assembly^ plugAssembly) {
      Text = "plug-in example";
      Size = Drawing::Size(400, 400);
      IsMdiContainer = true;

      array<Type^>^ types = plugAssembly->GetTypes( );
      Type^ formType = Form::typeid;

      for (int i = 0 ; i < types->Length ; i++) {
         if (formType->IsAssignableFrom(types[i])) {
            // Create an instance given the type description.
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));
            if (f) {
               f->Text = types[i]->ToString();
               f->MdiParent = this;
               f->Show();
            }
         }
      }
   }
};

int main() {
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");
   Application::Run(gcnew PluggableForm(a));
}
```

### <a name="example"></a>示例

下面的代码定义了从派生的三个类 <xref:System.Windows.Forms.Form> 。 当生成的程序集名称的名称传递到上一列表中的可执行文件时，将发现并实例化这三个类中的每个类，尽管在编译时它们都是未知的。

```cpp
// plugin_assembly.cpp
// compile with: /clr /LD
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;
using namespace System::Drawing;

public ref class BlueForm : public Form {
public:
   BlueForm() {
      BackColor = Color::Blue;
   }
};

public ref class CircleForm : public Form {
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);
   }
};

public ref class StarburstForm : public Form {
public:
   StarburstForm(){
      BackColor = Color::Black;
   }
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      Pen^ p = gcnew Pen(Color::Red, 2);
      Random^ r = gcnew Random( );
      Int32 w = ClientSize.Width;
      Int32 h = ClientSize.Height;
      for (int i=0; i<100; i++) {
         float x1 = w / 2;
         float y1 = h / 2;
         float x2 = r->Next(w);
         float y2 = r->Next(h);
         args->Graphics->DrawLine(p, x1, y1, x2, y2);
      }
   }
};
```

## <a name="how-to-enumerate-data-types-in-assemblies-using-reflection"></a><a name="enumerate"></a> 如何：使用反射枚举程序集中的数据类型

下面的代码演示了使用的公共类型和成员的枚举 <xref:System.Reflection> 。

给定程序集的名称，无论是在本地目录中还是 GAC 中，以下代码都尝试打开程序集并检索说明。 如果成功，则每个类型都将与其公共成员一起显示。

请注意， <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 不需要使用任何文件扩展名。 因此，使用 "mscorlib.dll" 作为命令行参数将失败，而仅使用 "mscorlib" 将导致显示 .NET Framework 类型。 如果未提供任何程序集名称，则代码将检测并报告当前程序集中的类型 (由此代码) 生成的 EXE。

### <a name="example"></a>示例

```cpp
// self_reflection.cpp
// compile with: /clr
using namespace System;
using namespace System::Reflection;
using namespace System::Collections;

public ref class ExampleType {
public:
   ExampleType() {}
   void Func() {}
};

int main() {
   String^ delimStr = " ";
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ args = Environment::CommandLine->Split( delimiter );

// replace "self_reflection.exe" with an assembly from either the local
// directory or the GAC
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");
   Console::WriteLine(a);

   int count = 0;
   array<Type^>^ types = a->GetTypes();
   IEnumerator^ typeIter = types->GetEnumerator();

   while ( typeIter->MoveNext() ) {
      Type^ t = dynamic_cast<Type^>(typeIter->Current);
      Console::WriteLine("   {0}", t->ToString());

      array<MemberInfo^>^ members = t->GetMembers();
      IEnumerator^ memberIter = members->GetEnumerator();
      while ( memberIter->MoveNext() ) {
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);
         Console::Write("      {0}", mi->ToString( ) );
         if (mi->MemberType == MemberTypes::Constructor)
            Console::Write("   (constructor)");

         Console::WriteLine();
      }
      count++;
   }
   Console::WriteLine("{0} types found", count);
}
```

## <a name="see-also"></a>请参阅

- [用 c + +/CLI (Visual C++ 的 .NET 编程) ](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
