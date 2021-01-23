---
description: 详细了解 pragma Microsoft c/c + + 中的注释指令
title: 条 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.comment
- comment_CPP
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragma, comment
- comment pragma
no-loc:
- pragma
ms.openlocfilehash: 8a4df005b672cb108a2b55004a1149693acd4f95
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713059"
---
# <a name="comment-no-locpragma"></a>`comment` pragma

将注释记录置于对象文件或可执行文件中。

## <a name="syntax"></a>语法

> **`#pragma comment(`***comment-类型*[ **`,`** "*comment-string*"]**`)`**

## <a name="remarks"></a>注解

*Comment 类型* 是预定义的标识符之一，如下所述，指定注释记录的类型。 可选的 *注释字符串* 是提供某些注释类型附加信息的字符串文字。 由于 *注释字符串* 是字符串文字，因此它服从使用转义符、嵌入引号 () 和串联的所有字符串文字规则 `"` 。

### <a name="compiler"></a>compiler

将编译器的名称和版本号置于对象文件中。 此注释记录将被链接器忽略。 如果为此记录类型提供 *注释字符串* 参数，编译器将生成警告。

### <a name="lib"></a>lib

将库搜索记录置于对象文件中。 此注释类型必须附带一个 *注释字符串* 参数，该参数的名称为 (，可能是您希望链接器搜索的库的路径) 。 库名称遵循对象文件中的默认库搜索记录。 链接器将以与你在命令行上指定的相同方式搜索此库，前提是未使用指定库 [`/nodefaultlib`](../build/reference/nodefaultlib-ignore-libraries.md) 。 可以将多个库搜索记录置于同一源文件中。 每个记录都按其在源文件中的相同顺序出现在对象文件中。

如果默认库和添加的库的顺序很重要，则使用开关进行编译 [`/Zl`](../build/reference/zl-omit-default-library-name.md) 将阻止将默认的库名称放置在对象模块中。 然后，可以使用第二条注释在 pragma 添加的库后插入默认库的名称。 与这些指令一起列出的库 pragma 将按照它们在源代码中找到的相同顺序出现在对象模块中。

### <a name="linker"></a>链接器

将 [链接器选项](../build/reference/linker-options.md) 放在对象文件中。 可以使用注释类型来指定链接器选项，而不是将其传递到命令行或在开发环境中指定它。 例如，可以指定 /include 选项来强制包含符号：

```C
#pragma comment(linker, "/include:__mySymbol")
```

只有以下 (*注释类型*) 链接器选项可传递到链接器标识符：

- [`/DEFAULTLIB`](../build/reference/defaultlib-specify-default-library.md)

- [`/EXPORT`](../build/reference/export-exports-a-function.md)

- [`/INCLUDE`](../build/reference/include-force-symbol-references.md)

- [`/MANIFESTDEPENDENCY`](../build/reference/manifestdependency-specify-manifest-dependencies.md)

- [`/MERGE`](../build/reference/merge-combine-sections.md)

- [`/SECTION`](../build/reference/section-specify-section-attributes.md)

### <a name="user"></a>用户

将一般注释置于对象文件中。 *Comment 字符串* 参数包含注释的文本。 此注释记录将被链接器忽略。

## <a name="examples"></a>示例

以下将 pragma 导致链接器搜索 EMAPI。链接时的 LIB 库。 链接器首先搜索当前工作目录中的，然后在 LIB 环境变量中指定的路径中进行搜索。

```C
#pragma comment( lib, "emapi" )
```

以下 pragma 操作将导致编译器将编译器的名称和版本号置于对象文件中：

```C
#pragma comment( compiler )
```

对于采用 *注释字符串* 参数的注释，只要宏展开为字符串文字，就可以在使用字符串文字的任何位置使用宏。 您还可以字符串与扩展到字符串的宏的任意组合串联在一起。 例如，以下语句是可接受的：

```C
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
