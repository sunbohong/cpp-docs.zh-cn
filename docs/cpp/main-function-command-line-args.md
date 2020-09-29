---
title: 'main 函数和命令行参数 (c + +) '
description: main函数是 c + + 程序的入口点。
ms.date: 01/15/2019
ms.assetid: c6568ee6-40ab-4ae8-aa44-c99e232f64ac
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
ms.openlocfilehash: b27668c3c7ce77e4369af144bb8be4efb695e522
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499806"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>main 函数和命令行参数

所有 c + + 程序必须具有 `main` 函数。 如果尝试编译不带函数的 c + + *.exe* 项目 main ，编译器将引发错误。  (动态链接库和 static 库没有 `main` 函数。 ) `main` 函数是源代码开始执行的位置，但在程序进入 `main` 函数之前，所有 static 没有显式初始值设定项的类成员都将设置为零。 在 Microsoft c + + 中，全局 static 对象还会在进入之前进行初始化 `main` 。 一些限制适用于 `main` 不应用于任何其他 c + + 函数的函数。 `main`函数：

- 无法重载 (请参阅 [函数重载](function-overloading.md)) 。
- 不能声明为 **`inline`** 。
- 不能声明为 **`static`** 。
- 不能提取其地址。
- 无法被调用。

该 main 函数不具有声明，因为它内置于该语言中。 如果是这样，的声明语法将如下所 `main` 示：

```cpp
int main();
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft 专用**

如果源文件使用 Unicode 宽 char acters，则可以使用 `wmain` ，这是 char 的 acter 版本 `main` 。 `wmain` 的声明语法如下所示：

```cpp
int wmain( );
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

你还可以使用 `_tmain` 在 \t\t 中定义的 char 。 `_tmain` 解析为， `main` 除非定义 _UNICODE。 在该示例中，`_tmain` 将解析为 `wmain`。

如果未指定返回值，则编译器提供返回值零。 此外， `main` 和 `wmain` 函数可以声明为返回 **`void`** (不) 返回值。 如果声明 `main` 或 `wmain` 返回 **`void`** ，则不能 exit 使用 [return](./program-termination.md) 语句将代码返回到父进程或操作系统。 若要 exit 在 `main` 或声明为时返回代码 `wmain` **`void`** ，则必须使用 [exit](./program-termination.md) 函数。

**结束 Microsoft 专用**

## <a name="command-line-arguments"></a>命令行参数

或的参数 `main` `wmain` 允许自变量的命令行分析，还可以选择访问环境变量。 `argc` 和 `argv` 的类型由语言定义。 名称 `argc` 、 `argv` 和 `envp` 是传统的，但你可以将其命名为你喜欢的任何名称。

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

自变量定义如下所示：

*argc*<br/>
一个整数，其中包含后面的参数的计数 *argv* 。 *argc* 参数始终大于或等于1。

*argv*<br/>
表示由杂注用户输入的命令行自变量的以 null 结尾的字符串的数组。 按照约定， `argv[0]` 是用于调用程序的命令， `argv[1]` 是第一个命令行参数，依此类推，直到 `argv[argc]` ，这始终为 NULL。 有关抑制命令行处理的信息，请参阅 [自定义命令行处理]() 。

第一个命令行参数始终是 `argv[1]`，而最后一个命令行参数是 `argv[argc - 1]`。

> [!NOTE]
> 按照约定， `argv[0]` 是用于调用程序的命令。 但是，可以使用来生成进程， [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 并且如果同时使用第一个和第二个参数 (*LpApplicationName* 和 *lpCommandLine*) ，则 `argv[0]` 可能不是可执行文件名称; 使用 [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 检索可执行文件名称及其完全限定路径。

**Microsoft 专用**

*envp*<br/>
*envp* 在 Microsoft c + + 中使用数组，这是许多 UNIX 系统中的通用扩展。 它是表示用户环境中的变量集的字符串的数组。 该数组由 NULL 项终止。 它可以声明为指向)  (的指针的数组，也可以声明为指向 **`char`** `char *envp[]` () 的指针的指针 **`char`** `char **envp` 。 如果程序使用 `wmain` 而不是 `main` ，请使用 **`wchar_t`** 数据类型而不是 **`char`** 。 环境块传递到 `main` ，并 `wmain` 是当前环境的 "冻结" 副本。 如果您随后通过调用或更改环境，则 `putenv` `_wputenv` 当前环境 (由或返回， `getenv` `_wgetenv` 而 `_environ` 或  `_wenviron` 变量) 将更改，但指向的块 envp 将不会更改。 有关取消环境处理的信息，请参阅 [自定义命令行处理]() 。 此参数在 C 中是 ANSI 兼容的，但在 C++ 中不是这样。

**结束 Microsoft 专用**

### <a name="example"></a>示例

下面的示例演示如何使用 *argc* 、 *argv* 和 *envp* 参数 `main` 执行以下操作：

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int main( int argc, char *argv[], char *envp[] ) {
    int iNumberLines = 0;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.

    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )
         iNumberLines = 1;

    // Walk through list of strings until a NULL is encountered.
    for( int i = 0; envp[i] != NULL; ++i ) {
        if( iNumberLines )
            cout << i << ": " << envp[i] << "\n";
    }
}
```

## <a name="parsing-c-command-line-arguments"></a>分析 c + + 命令行参数

**Microsoft 专用**

在解释操作系统命令行上给出的参数时，Microsoft C/c + + 启动代码使用以下规则：

- 参数用空白分隔，空白可以是一个空格或制表符。

- 脱字号 char acter (^) 未被识别为转义 char acter 或分隔符。 在将 char acter 传递到程序中的数组之前，将由操作系统中的命令行分析器完全处理 `argv` 。

- 括在双引号中的字符串 ( "*string*" ) 被解释为单个参数，而不考虑中包含的空格。 带引号的字符串可以嵌入在自变量内。

- 前面有反斜杠的双引号 (\\ ") 被解释为文字的双引号 char acter (" ) 。

- 反斜杠按其原义解释，除非它们紧位于双引号之前。

- 如果偶数个反斜杠后跟双引号，则每对反斜杠中有一个反斜杠被置于数组中， `argv` 而双引号被解释为字符串分隔符。

- 如果奇数个反斜杠后跟双引号，则每对反斜杠中有一个反斜杠被置于数组中， `argv` 而双引号用反斜杠进行 "转义" main ，导致原义双引号 ( ") 放入 `argv` 。

### <a name="example"></a>示例

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

下表显示了示例输入和预期输出，并演示了上述列表中的规则。

### <a name="results-of-parsing-command-lines"></a>分析命令行的结果

|命令行输入|argv[1]|argv[2]|argv三维空间|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**结束 Microsoft 专用**

## <a name="wildcard-expansion"></a>通配符扩展

**Microsoft 专用**

可以使用通配符（问号 (?) 和星号 (*)）在命令行上指定文件名和路径参数。

命令行参数由名为 `_setargv` (或 `_wsetargv` acter 环境中的例程处理 char) ，默认情况下，它不会将通配符扩展到字符串数组中的单独字符串中 `argv` 。 有关启用通配符扩展的详细信息，请参阅 [扩展通配符参数](../c-language/expanding-wildcard-arguments.md)。

**结束 Microsoft 专用**

## <a name="customizing-c-command-line-processing"></a>自定义 C++ 命令行处理

**Microsoft 专用**

如果程序不采用命令行自变量，则可以通过取消使用执行命令行处理的库例程来节省少量空间。 此例程被称为 `_setargv` ，并在 [通配符扩展]()中进行了介绍。 若要禁止使用，请在包含函数的文件中定义不执行任何操作的例程 `main` ，并将其命名为 `_setargv` 。 然后，对的定义满足对的调用 `_setargv` `_setargv` ，并且不加载库版本。

同样，如果您从不通过参数访问环境表 `envp` ，则可以提供自己的空例程用于替代 `_setenvp` 环境处理例程。 与 `_setargv` 函数一样， `_setenvp` 必须将声明为** extern "C"**。

程序可能会调用 `spawn` `exec` C 运行库中的或系列的例程。 如果是这样，则不应取消环境处理例程，因为使用此例程将环境从父进程传递到子进程。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[基本概念](../cpp/basic-concepts-cpp.md)
