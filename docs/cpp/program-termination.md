---
title: C + + 程序终止
description: 了解退出 c + + 语言程序的标准方法。
ms.date: 12/07/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.openlocfilehash: 15d31d8d454f6ac90e012d35ef14e6d6e0a9e29a
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933204"
---
# <a name="c-program-termination"></a>C + + 程序终止

在 c + + 中，可以通过以下方式退出程序：

- 调用 [`exit`](../c-runtime-library/reference/exit-exit-exit.md) 函数。
- 调用 [`abort`](../c-runtime-library/reference/abort.md) 函数。
- 从执行 [`return`](return-statement-cpp.md) 语句 `main` 。

## <a name="exit-function"></a>`exit` 函数

[`exit`](../c-runtime-library/reference/exit-exit-exit.md)在中声明的函数 \<stdlib.h> 终止 c + + 程序。 作为的参数提供的值 `exit` 将作为程序的返回代码或退出代码返回到操作系统。 按照约定，返回代码为零表示该程序已成功完成。 您可以使用常量 `EXIT_FAILURE` 以及 `EXIT_SUCCESS` 在中定义的 \<stdlib.h> 来指示程序是成功还是失败。

**`return`** 从函数发出语句 `main` 等效于 `exit` 使用返回值作为参数来调用函数。

## <a name="abort-function"></a>`abort` 函数

[`abort`](../c-runtime-library/reference/abort.md)还在标准包含文件中声明的函数 \<stdlib.h> 终止 c + + 程序。 与之间的区别在于 `exit` `abort` `exit` 允许 c + + 运行时终止处理 (全局对象析构函数) 调用，但会 `abort` 立即终止程序。 `abort`函数会绕过已初始化全局静态对象的正常析构进程。 它还会绕过函数指定的任何特殊处理 [`atexit`](../c-runtime-library/reference/atexit.md) 。

## <a name="atexit-function"></a>`atexit` 函数

使用 [`atexit`](../c-runtime-library/reference/atexit.md) 函数指定在程序终止之前执行的操作。 在 `atexit` 执行退出处理函数之前，不会在对的调用之前初始化全局静态对象。

## <a name="return-statement-in-main"></a>`return` 语句 `main`

发出的 [`return`](return-statement-cpp.md) 语句 `main` 在功能上等效于调用 `exit` 函数。 请考虑以下示例：

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit`前面的 **`return`** 示例中的和语句在功能上相同。 通常情况下，c + + 要求具有以外返回类型的函数 **`void`** 返回值。 此 `main` 函数是一个异常，它可以不带 **`return`** 语句结束。 在这种情况下，它会将实现特定值返回到调用进程。 **`return`** 语句允许您指定返回值 `main` 。

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
   ShowData sd1( "CON" ), sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>另请参阅

[`main` 函数和命令行参数](main-function-command-line-args.md)
