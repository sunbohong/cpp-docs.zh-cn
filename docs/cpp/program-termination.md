---
title: C + + 程序终止
description: 介绍 exit c + + 语言程序的方式。
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- exit
- abort
- return
- main
- atexit
- void
ms.openlocfilehash: fd0c7699ae032b5551f4fbc37eb3b7fa999a168f
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352916"
---
# <a name="c-program-termination"></a>C + + 程序终止

在 c + + 中，可以通过 exit 以下方式使用程序：

- 调用 [exit](../c-runtime-library/reference/exit-exit-exit.md) 函数。
- 调用 [abort](../c-runtime-library/reference/abort.md) 函数。
- 从执行 [return](return-statement-cpp.md) 语句 `main` 。

## <a name="no-locexit-function"></a>exit 函数

[exit](../c-runtime-library/reference/exit-exit-exit.md)在中声明的函数 \<stdlib.h> 终止 c + + 程序。 作为的参数提供的值 `exit` 是 return 作为程序的 return 代码或代码的操作系统 exit 。 按照约定，如果 return 代码为零，则表示程序已成功完成。 您可以使用 EXIT_FAILURE 和 EXIT_SUCCESS 中定义的常量 \<stdlib.h> 来指示程序是成功还是失败。

**`return`** 从函数发出语句 `main` 等效于 `exit` 使用 return 值作为其参数调用函数。

## <a name="no-locabort-function"></a>abort 函数

[abort](../c-runtime-library/reference/abort.md)还在标准包含文件中声明的函数 \<stdlib.h> 终止 c + + 程序。 与之间的区别在于 `exit` `abort` `exit` 允许 c + + 运行时终止处理 (全局对象析构函数) 调用，而是 `abort` 立即终止程序。 `abort`函数会绕过已初始化全局静态对象的正常析构进程。 它还会绕过函数指定的任何特殊处理 [atexit](../c-runtime-library/reference/atexit.md) 。

## <a name="no-locatexit-function"></a>atexit 函数

使用 [atexit](../c-runtime-library/reference/atexit.md) 函数指定在程序终止之前执行的操作。 在 **atexit** 执行 exit -处理函数之前，不会对调用之前初始化的全局静态对象进行销毁。

## <a name="no-locreturn-statement-in-no-locmain"></a>return 语句 main

发出的 [return](return-statement-cpp.md) 语句 `main` 在功能上等效于调用 `exit` 函数。 请考虑以下示例：

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit`前面的 **`return`** 示例中的和语句在功能上相同。 但是，c + + 要求 return 类型不 **`void`** return 是值的函数。 **`return`** 语句允许 return 使用中的值 `main` 。

## <a name="destruction-of-static-objects"></a>静态对象的析构

当从调用 `exit` 或执行 **`return`** 语句时 `main` ，静态对象会按其初始化 (的相反顺序销毁，前提是在 `atexit`) 存在时调用。 以下示例演示如何进行此类初始化和清理工作。

### <a name="example"></a>示例

在下面的示例中，将在 `sd1` `sd2` 进入之前创建并初始化静态对象和 `main` 。 此程序使用语句终止后 **`return`** ，首先 `sd2` 销毁，然后再销毁 `sd1` 。 `ShowData` 类的析构函数将关闭与这些静态对象关联的文件。

```cpp
// using_exit_or_return1.cpp
#include <stdio.h>
class ShowData {
public:
   // Constructor opens a file.
   ShowData( const char *szDev ) {
   errno_t err;
      err = fopen_s(&OutputDev, szDev, "w" );
   }

   // Destructor closes the file.
   ~ShowData() { fclose( OutputDev ); }

   // Disp function shows a string on the output device.
   void Disp( char *szData ) {
      fputs( szData, OutputDev );
   }
private:
   FILE *OutputDev;
};

//  Define a static object of type ShowData. The output device
//   selected is "CON" -- the standard output device.
ShowData sd1 = "CON";

//  Define another static object of type ShowData. The output
//   is directed to a file called "HELLO.DAT"
ShowData sd2 = "hello.dat";

int main() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

另一种编写此代码的方式为，使用块范围声明 `ShowData` 对象，并允许在它们超出范围时将其销毁：

```cpp
int main() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>另请参阅

[main 函数和命令行参数](main-function-command-line-args.md)
