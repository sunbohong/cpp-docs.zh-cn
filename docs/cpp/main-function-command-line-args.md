---
title: '`main` 函数和命令行参数 (c + +) '
description: '`main`函数是 c + + 程序的入口点。'
ms.date: 12/16/2020
no-loc:
- main
- wmain
- inline
- static
- _tmain
- void
- exit
- argc
- argv
- envp
- CreateProcess
- GetModuleFileName
- char
- wchar_t
- extern
ms.openlocfilehash: a9c68f199d4169c02260542a9730472e4ab397bd
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645067"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>`main` 函数和命令行参数

所有 c + + 程序必须具有 `main` 函数。 如果尝试编译没有函数的 c + + 程序 `main` ，编译器将引发错误。  (动态链接库和 static 库没有 `main` 函数。 ) `main` 函数是源代码开始执行的位置，但在程序进入 `main` 函数之前，所有 static 没有显式初始值设定项的类成员都将设置为零。 在 Microsoft c + + 中，全局 static 对象还会在进入之前进行初始化 `main` 。 一些限制适用于 `main` 不适用于任何其他 c + + 函数的函数。 `main` 函数：

- 无法重载 (请参阅 [函数重载](./function-overloading.md)) 。
- 不能声明为 **`inline`** 。
- 不能声明为 **`static`** 。
- 无法获取其地址。
- 不能从程序调用。

## <a name="the-no-locmain-function-signature"></a>`main`函数签名

该 `main` 函数不具有声明，因为它内置于该语言中。 如果是这样，的声明语法将如下所 `main` 示：

```cpp
int main();
int main(int argc, char *argv[]);
```

如果未在中指定返回值 `main` ，则编译器将提供返回值零。

## <a name="standard-command-line-arguments"></a>标准命令行参数

的参数 `main` 允许自变量的命令行分析。 `argc` 和 `argv` 的类型由语言定义。 名称 `argc` 和 `argv` 是传统的，但你可以将其命名为你喜欢的任何名称。

自变量定义如下所示：

*`argc`*\
一个整数，其中包含后面的参数的计数 *argv* 。 *argc* 参数始终大于或等于1。

*`argv`*\
表示由杂注用户输入的命令行自变量的以 null 结尾的字符串的数组。 按照约定， `argv[0]` 是用于调用程序的命令。 `argv[1]` 是第一个命令行参数。 命令行中的最后一个参数为 `argv[argc - 1]` ，并且 `argv[argc]` 始终为 NULL。

有关如何禁止显示命令行处理的信息，请参阅 [自定义 c + + 命令行处理](#customize)。

> [!NOTE]
> 按照约定， `argv[0]` 是程序的文件名。 但是，在 Windows 上，可以使用来生成进程 [`CreateProcess`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 。 如果同时使用第一个和第二个参数 (*`lpApplicationName`* 和 *`lpCommandLine`*) ，则 `argv[0]` 可能不是可执行的名称。 您可以使用 [`GetModuleFileName`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 检索可执行文件名称及其完全限定路径。

## <a name="microsoft-specific-extensions"></a>Microsoft 专用扩展

以下各节介绍了特定于 Microsoft 的行为。

## <a name="the-no-locwmain-function-and-no-loc_tmain-macro"></a>`wmain`函数和 `_tmain` 宏

如果将源代码设计为使用 Unicode 宽 char acters，则可以使用特定于 Microsoft 的 `wmain` 入口点，这是的 char acter 版本 `main` 。 下面是的有效声明语法 `wmain` ：

```cpp
int wmain();
int wmain(int argc, wchar_t *argv[]);
```

你还可以使用 Microsoft 特定的 `_tmain` ，它是在中定义的预处理器宏 *`tchar.h`* 。 `_tmain` 解析为， `main` 除非 `_UNICODE` 定义了。 在该示例中，`_tmain` 将解析为 `wmain`。 `_tmain`宏和以开头的宏 `_t` 对于必须为窄和宽 acter 集生成不同版本的代码非常有用 char 。 有关详细信息，请参阅 [使用一般文本映射](../c-runtime-library/using-generic-text-mappings.md)。

## <a name="returning-no-locvoid-from-no-locmain"></a>返回 `void` 自 main

作为 Microsoft 扩展， `main` 和 `wmain` 函数可以声明为返回 **`void`** (不) 返回值。 此扩展在某些其他编译器中也可用，但不建议使用。 它可用于在 `main` 不返回值时进行对称。

如果声明 `main` 或 `wmain` 返回 **`void`** ，则不能 exit 使用语句将代码返回到父进程或操作系统 [`return`](./program-termination.md) 。 若要 exit 在 `main` 或声明为时返回代码 `wmain` **`void`** ，则必须使用 [`exit`](./program-termination.md) 函数。

## <a name="the-no-locenvp-command-line-argument"></a>`envp`命令行参数

`main`或 `wmain` 签名允许使用可选的 Microsoft 专用扩展来访问环境变量。 此扩展在适用于 Windows 和 UNIX 系统的其他编译器中也很常见。 名称 *`envp`* 为传统名称，但你可以将环境参数命名为任何所需的名称。 下面是包含环境参数的自变量列表的有效声明：

```cpp
int main(int argc, char* argv[], char* envp[]);
int wmain(int argc, wchar_t* argv[], wchar_t* envp[]);
```

*`envp`*\
可选 *`envp`* 参数是一个字符串数组，表示用户环境中设置的变量。 该数组由 NULL 项终止。 它可以声明为指向)  (的指针的数组，也可以声明为指向 **`char`** `char *envp[]` () 的指针的指针 **`char`** `char **envp` 。 如果程序使用 `wmain` 而不是 `main` ，请使用 **`wchar_t`** 数据类型而不是 **`char`** 。

环境块传递到 `main` ，并 `wmain` 是当前环境的 "冻结" 副本。 如果稍后通过调用或来更改环境 `putenv` `_wputenv` ，则当前环境 (由或返回， `getenv` `_wgetenv` 而 `_environ` 或  `_wenviron` 变量) 将更改，而指向的块将 *`envp`* 不会更改。 有关如何取消环境处理的详细信息，请参阅 [自定义 c + + 命令行处理](#customize)。 *`envp`* 参数与 C89 标准兼容，但与 c + + 标准兼容。

### <a name="example-arguments-to-no-locmain"></a>的示例参数 `main`

下面的示例演示如何使用 *`argc`* 、 *`argv`* 和 *`envp`* 参数 `main` 执行以下操作：

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int main( int argc, char *argv[], char *envp[] )
{
    bool numberLines = false;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.
    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )
         numberLines = true;

    // Walk through list of strings until a NULL is encountered.
    for ( int i = 0; envp[i] != NULL; ++i )
    {
        if ( numberLines )
            cout << i << ": "; // Prefix with numbers if /n specified
        cout << envp[i] << "\n";
    }
}
```

## <a name="parsing-c-command-line-arguments"></a>分析 C++ 命令行自变量

Microsoft C/c + + 代码使用的命令行分析规则是 Microsoft 特定的。 在解释操作系统命令行上给出的参数时，运行时启动代码使用这些规则：

- 参数用空白分隔，空白可以是一个空格或制表符。

- 第一个参数 (`argv[0]`) 是经过专门处理的。 它表示程序名称。 因为它必须是有效的路径名，因此允许用双引号 (`"`) 括起来一些部分。 双引号不包含在 `argv[0]` 输出中。 用双引号引起来的部分禁止将空格或制表符 char acter 解释为参数的结尾。 此列表中的后续规则不适用。

- 用双引号引起来的字符串被解释为单个参数，该参数可以包含空白 char acters。 带引号的字符串可以嵌入在自变量内。 不能将插入符号 (**`^`**) 被识别为转义 char acter 或分隔符。 在带引号的字符串中，一对双引号被解释为单个转义的双引号。 如果在找到结束双引号之前命令行结束，则所有 char acters 读取的都是最后一个参数。

- 前面有反斜杠的双引号 (`\"`) 被解释为原义双引号 (`"`)。

- 反斜杠按其原义解释，除非它们紧位于双引号之前。

- 如果偶数个反斜杠后跟双引号，则每对反斜杠 (`\\`) 中有一个反斜杠 (`\`) 被置于 `argv` 数组中，而双引号 (`"`) 被解释为字符串分隔符。

- 如果奇数个反斜杠后跟双引号，则每对反斜杠 (`\\`) 中有一个反斜杠 (`\`) 被置于 `argv` 数组中。 用反斜杠将双引号解释为转义序列 main ，这会导致文本双引号 (**`"`**) 放入 `argv` 。

### <a name="example-of-command-line-argument-parsing"></a>命令行参数分析的示例

以下程序演示如何传递命令行参数：

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int main( int argc,      // Number of strings in array argv
          char *argv[],   // Array of command-line argument strings
          char *envp[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < argc; count++ )
         cout << "  argv[" << count << "]   "
                << argv[count] << "\n";
}
```

### <a name="results-of-parsing-command-lines"></a>分析命令行的结果

下表显示了示例输入和预期输出，并演示了上述列表中的规则。

| 命令行输入 | argv[1] | argv[2] | argv三维空间 |
|--|--|--|--|
| `"abc" d e` | `abc` | `d` | `e` |
| `a\\b d"e f"g h` | `a\\b` | `de fg` | `h` |
| `a\\\"b c d` | `a\"b` | `c` | `d` |
| `a\\\\"b c" d e` | `a\\b c` | `d` | `e` |
| `a"b"" c d` | `ab" c d` |  |  |

## <a name="wildcard-expansion"></a>通配符扩展

Microsoft 编译器可选择使用 *通配符* char acters （问号 (**`?`**) 和星号 (**`*`**) ）来指定命令行上的文件名和路径参数。

命令行参数由运行时启动代码中的内部例程处理，默认情况下，它不会将通配符扩展到字符串数组中的各个字符串 `argv` 。 可以通过 *`setargv.obj`* *`wsetargv.obj`* `wmain` 在 **`/link`** 编译器选项或命令行中包含) 的文件 (文件来启用通配符扩展 **`LINK`** 。

有关运行时启动链接器选项的详细信息，请参阅[链接选项](../c-runtime-library/link-options.md)。

## <a name="customize-c-command-line-processing"></a><a name="customize"/> 自定义 c + + 命令行处理

如果程序不采用命令行参数，则可以取消命令行处理例程来节省少量空间。 若要禁止使用该方法，请在 `/link` 编译器选项或 `LINK` 命令行中包含 `noarg.obj` 文件（用于 `main` 和 `wmain`）。

同样，如果从不通过 `envp` 参数访问环境表，则可以取消内部环境处理例程。 若要禁止使用该方法，请在 `/link` 编译器选项或 `LINK` 命令行中包含 `noenv.obj` 文件（用于 `main` 和 `wmain`）。

程序可以调用 C 运行时库中的 `spawn` 或 `exec` 系列例程。 如果是这样，则不应取消环境处理例程，因为可使用它将环境从父进程传递到子进程中。

## <a name="see-also"></a>另请参阅

[基本概念](../cpp/basic-concepts-cpp.md)
