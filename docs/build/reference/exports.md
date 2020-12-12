---
description: 了解更多：导出
title: EXPORTS
ms.date: 09/07/2018
f1_keywords:
- EXPORTS
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
ms.openlocfilehash: b886f626854012c3cc477fcb11ac74a1e7776299
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192339"
---
# <a name="exports"></a>EXPORTS

引入了一个由一个或多个导出定义组成的节，这些定义可指定函数或数据的导出名或序号。 每个定义必须在单独一行上。

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>备注

第一个 *定义* 可以与关键字在同一行上， `EXPORTS` 也可以在后面的行上。 .DEF 文件可以包含一个或多个 `EXPORTS` 语句。

导出 *定义* 的语法为：

>  \[ entryname __=__*internal_name* |*other_module.exported_name*]\[ **\@** _ordinal_ \[ **NONAME**] \[ ] \[**专用**]|\[**数据**]]

*entryname* 是要导出的函数或变量名称。 这是必填字段。 如果导出的名称与 DLL 中的名称不同，请使用 *internal_name* 在 dll 中指定导出的名称。 例如，如果 DLL 导出函数 `func1`，并且你希望调用方将其用作 `func2`，则应指定：

```DEF
EXPORTS
   func2=func1
```

如果导出的名称来自其他某个模块，请使用 *other_module* 在 DLL 中指定导出的名称。 例如，如果 DLL 导出函数 `other_module.func1`，并且你希望调用方将其用作 `func2`，则应指定：

```DEF
EXPORTS
   func2=other_module.func1
```

如果导出的名称来自按序号导出的其他模块，请使用 *other_module* 在 DLL 中指定导出的序号。 __#__*序数*。 例如，如果您的 DLL 从另一个模块中导出函数，而该模块的序号为42，而您希望调用方将其用作 `func2` ，则应指定：

```DEF
EXPORTS
   func2=other_module.#42
```

由于 MSVC 编译器使用了 c + + 函数的名称修饰，因此您必须使用修饰名 *internal_name* 或使用 `extern "C"` 在源代码中定义导出的函数。 编译器还修饰 C 函数，这些函数使用 [__stdcall](../../cpp/stdcall.md) 调用约定，其中包含下划线 (\_) 前缀和由 at 符号 (组成的后缀， \@ 后跟在参数列表中) 十进制 (中的字节数。

若要查找由编译器生成的修饰名，请使用 [DUMPBIN](dumpbin-reference.md) 工具或链接器 [/MAP](map-generate-mapfile.md) 选项。 修饰名特定于编译器。 如果要将修饰名导出到 .DEF 文件中，则链接到 DLL 的可执行文件也必须通过使用同一版本的编译器生成。 这可确保调用方中的修饰名与 .DEF 文件中的导出名相匹配。

您可以使用 \@ *序数* 来指定数值（而不是函数名）进入 DLL 的导出表。 许多 Windows DLL 将导出序号以支持旧版代码。 通常使用采用 16 位 Windows 编码的序号，因为这有助于最大程度地减小 DLL 的大小。 建议你不要按序号导出函数，除非你的 DLL 的客户端需要它来实现旧支持。 由于 .LIB 文件将包含序号与函数之间的映射，因此你可以像通常在使用 DLL 的项目中那样使用函数名。

通过使用可选的 **NONAME** 关键字，可以仅按序号导出，并减少生成的 DLL 中导出表的大小。 但是，如果要在 DLL 上使用 [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) ，则必须知道序号，因为名称将无效。

可选关键字 **PRIVATE** 禁止将 *entryname* 包含在由 LINK 生成的导入库中。 它不会影响同样是由 LINK 生成的映像中的导出。

可选关键字 **DATA** 指定导出为数据，而不是代码。 此示例显示如何导出名为 `exported_global` 的数据变量：

```DEF
EXPORTS
   exported_global DATA
```

可通过采用建议的顺序列出的四种方式导出定义：

1. 源代码中的 [__declspec (dllexport) ](../../cpp/dllexport-dllimport.md) 关键字

1. .DEF 文件中的 `EXPORTS` 语句

1. LINK 命令中的 [/export](export-exports-a-function.md) 规范

1. 源代码中的 [注释](../../preprocessor/comment-c-cpp.md) 指令，其形式为 `#pragma comment(linker, "/export: definition ")` 。 下面的示例演示函数声明之前的 #pragma 注释指令，其中 `PlainFuncName` 是未修饰的名称， `_PlainFuncName@4` 是函数的修饰名：

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

如果需要导出未修饰的函数名称，并且具有不同的导出（例如，32位或64版本) 中的生成 (配置），则 #pragma 指令非常有用。

所有这四种方法可以用在同一个程序中。 LINK 在生成包含导出的程序时还创建导入库，除非生成中使用了 .EXP 文件。

下面是 EXPORTS 节的一个示例：

```DEF
EXPORTS
   DllCanUnloadNow      @1          PRIVATE
   DllWindowName = WindowName       DATA
   DllGetClassObject    @4 NONAME   PRIVATE
   DllRegisterServer    @7
   DllUnregisterServer
```

使用 .DEF 文件从 DLL 中导出变量时，不必在变量上指定 `__declspec(dllexport)`。 但是，在任何使用 DLL 的文件中，必须仍在数据的声明上使用 `__declspec(dllimport)`。

## <a name="see-also"></a>请参阅

[Module-Definition 语句的规则](rules-for-module-definition-statements.md)
