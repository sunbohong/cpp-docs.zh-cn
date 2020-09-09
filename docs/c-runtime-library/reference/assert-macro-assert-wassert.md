---
title: assert 宏、_assert、_wassert
description: 断言宏和函数在 C 运行时中的效果。
ms.date: 11/04/2016
api_name:
- assert
- _assert
- _wassert
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
ms.openlocfilehash: 071424f2201ceda43438fe1056801811fe444a01
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609078"
---
# <a name="assert-macro-_assert-_wassert"></a>assert 宏、_assert、_wassert

计算表达式，并在结果为时 **`false`** ，打印诊断消息并中止程序。

## <a name="syntax"></a>语法

```C
assert(
   expression
);
void _assert(
   char const* message,
   char const* filename,
   unsigned line
);
void _wassert(
   wchar_t const* message,
   wchar_t const* filename,
   unsigned line
);
```

### <a name="parameters"></a>参数

*expression*<br/>
标量表达式 (包括) 计算结果为非零 (**`true`**) 或 () 的指针表达式 **`false`** 。

*message*<br/>
要显示的消息。

*filename*<br/>
断言失败的源文件的名称。

*line*<br/>
断言失败处所在的源文件行号。

## <a name="remarks"></a>备注

`assert` 宏通常用于标识程序开发过程中的逻辑错误。 使用它可以在出现意外情况时停止程序执行，方法是实现 *表达式* 参数，使其 **`false`** 在程序运行不正常时计算结果为。 通过定义宏 **NDEBUG**，可以在编译时关闭断言检查。 使用 `assert` 命令行选项，可以在不修改源文件的情况下来关闭 **assert** 宏。 在包含之前，可以 `assert` 使用指令在源代码中关闭宏 `#define NDEBUG` \<assert.h> 。

`assert`当*表达式*的计算结果为 **`false`** (0) 并调用停止程序执行时，宏将打印诊断消息 [`abort`](abort.md) 。 如果 *expression* **`true`** (非零) ，则不执行任何操作。 诊断消息包括失败的表达式、源文件的名称以及断言失败的行号。

诊断消息以宽 (`wchar_t`) 字符打印。 因此，它将按预期工作，即使表达式中存在 Unicode 字符也是如此。

诊断消息的目标取决于调用例程的应用程序的类型。 控制台应用程序通过 **stderr**接收消息。 在基于 Windows 的应用程序中， `assert` 调用 Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) 函数以创建消息框，以显示带有三个按钮的消息： " **中止**"、" **重试**" 和 " **忽略**"。 如果用户单击 **“中止”**，则程序将立即中止。 如果用户单击 **“重试”**，则将调用调试器，之后用户可以调试程序，前提是启用了实时 (JIT) 调试。 如果用户单击 " **忽略**"，则程序将继续正常执行。 当存在错误条件时单击 " **忽略** " 可能导致未定义的行为，因为调用代码的前置条件不满足。

若要重写默认输出行为而不管应用类型如何，请调用 [`_set_error_mode`](set-error-mode.md) 以在输出到 stderr 和显示对话框行为之间进行选择。

`assert`显示其消息后，它将调用 [`abort`](abort.md) ，其中显示一个对话框，其中包含 "**中止**"、"**重试**" 和 "**忽略**" 按钮。 [`abort`](abort.md) 退出程序，因此 " **重试** " 和 " **忽略** " 按钮不会在调用后恢复程序执行 `assert` 。 如果 `assert` 显示一个对话框，则 [`abort`](abort.md) 不会显示该对话框。 仅 [`abort`](abort.md) 显示对话框的时间是将 `assert` 其输出发送到 stderr。

作为上述行为的结果，对话框始终在调试模式下的调用后显示 `assert` 。 下表中捕获了每个按钮的行为。

|错误模式|输出到 stderr (Console/_OUT_TO_STDERR) |显示 (Windows/_OUT_TO_MSGBOX 的对话框) |
|----------|----------------|------------------|
|中止|退出并退出代码3|退出并退出代码3|
|重试|在期间中断调试器 `abort`|在期间中断调试器 `assert`|
|忽略|完成退出 `abort`|请继续执行程序，如同断言未激发 (可能会导致未定义的行为，因为调用代码的前置条件不满足) |

有关 CRT 调试的详细信息，请参阅 [CRT 调试技术](/visualstudio/debugger/crt-debugging-techniques)。

`_assert` 和 `_wassert` 函数是内部 CRT 函数。 这两个函数可帮助最大程度地减少在对象文件中支持断言所需的代码。 建议您不要直接调用这些函数。

`assert`如果未定义**NDEBUG** ，则在 C 运行库的发布版本和调试版本中均启用了宏。 定义 **NDEBUG** 后，宏可用，但不会计算其自变量，并且不起作用。 启用后， `assert` 宏会调用 `_wassert` 其实现。 其他断言宏 [_ASSERT](assert-asserte-assert-expr-macros.md)、 [_ASSERTE](assert-asserte-assert-expr-macros.md) 和 [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md)也可用，但它们只有在已定义 [_DEBUG](../../c-runtime-library/debug.md) 宏的情况下以及存在于与 C 运行时库调试版本关联的代码中时才会计算传递给它们的表达式。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`assert`, `_wassert`|\<assert.h>|

函数的签名 `_assert` 在头文件中不可用。 函数的签名 `_wassert` 仅在未定义 **NDEBUG** 宏时才可用。

## <a name="example"></a>示例

在此程序中， **analyze_string** 函数使用 `assert` 宏来测试与字符串和长度相关的一些条件。 如果任意条件失败，则程序将打印指示失败原因的消息。

```C
// crt_assert.c
// compile by using: cl /W4 crt_assert.c
#include <stdio.h>
#include <assert.h>
#include <string.h>

void analyze_string( char *string );   // Prototype

int main( void )
{
   char  test1[] = "abc", *test2 = NULL, test3[] = "";

   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );
   analyze_string( test1 );
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );
   analyze_string( test2 );
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );
   analyze_string( test3 );
}

// Tests a string to see if it is NULL,
// empty, or longer than 0 characters.
void analyze_string( char * string )
{
   assert( string != NULL );        // Cannot be NULL
   assert( *string != '\0' );       // Cannot be empty
   assert( strlen( string ) > 2 );  // Length must exceed 2
}
```

该程序会生成以下输出：

```Output
Analyzing string 'abc'
Analyzing string '(null)'
Assertion failed: string != NULL, file crt_assert.c, line 25
```

断言失败后，根据操作系统和运行时库的版本，你可能会看到一个消息框，其中包含类似于以下内容的消息框：

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

如果已安装调试器，请选择“调试” **** 按钮以启动调试器，或选择“关闭程序” **** 以退出。

## <a name="see-also"></a>请参阅

[错误处理](../../c-runtime-library/error-handling-crt.md)<br/>
[进程和环境控制](../../c-runtime-library/process-and-environment-control.md)<br/>
[中止](abort.md)<br/>
[提出](raise.md)<br/>
[signal](signal.md)<br/>
[_ASSERT、_ASSERTE _ASSERT_EXPR 宏](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
