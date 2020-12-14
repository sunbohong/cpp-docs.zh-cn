---
description: '了解详细信息： Debug 类 (c + +/CLI) '
title: Debug 类 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
ms.openlocfilehash: 255fe306684928faf836cd550005eea820d64ce5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258429"
---
# <a name="debug-class-ccli"></a>Debug 类 (C++/CLI)

<xref:System.Diagnostics.Debug>在 Visual C++ 应用程序中使用时，调试版本和发布版本之间的行为不会更改。

## <a name="remarks"></a>备注

的行为与 <xref:System.Diagnostics.Trace> Debug 类的行为相同，但依赖于所定义的符号跟踪。 这意味着，你必须 `#ifdef` 具有跟踪相关的任何代码，以防止在发布版本中调试行为。

## <a name="example-always-executes-output-statements"></a>示例：始终执行 output 语句

### <a name="description"></a>描述

下面的示例始终执行 output 语句，无论你是用 **/DDEBUG** 还是 **/DTRACE** 进行编译。

### <a name="code"></a>代码

```cpp
// mcpp_debug_class.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
   Trace::Unindent();

   Debug::WriteLine("test");
}
```

### <a name="output"></a>输出

```Output
    Entering Main
Hello World.
    Exiting Main
test
```

## <a name="example-use-ifdef-and-endif-directives"></a>示例：使用 #ifdef 和 #endif 指令

### <a name="description"></a>描述

若要获取预期的行为 (也就是说，不会为发布版本) 打印 "测试" 输出，必须使用 `#ifdef` 和 `#endif` 指令。 下面修改了上面的代码示例，以演示此修补程序：

### <a name="code"></a>代码

```cpp
// mcpp_debug_class2.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();

#ifdef TRACE   // checks for a debug build
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
#endif
   Trace::Unindent();

#ifdef DEBUG   // checks for a debug build
   Debug::WriteLine("test");
#endif   //ends the conditional block
}
```

## <a name="see-also"></a>请参阅

[用 c + +/CLI (Visual C++ 的 .NET 编程) ](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
