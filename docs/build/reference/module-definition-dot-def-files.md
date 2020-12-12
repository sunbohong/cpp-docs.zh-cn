---
description: 了解详细信息： Module-Definition (。.Def) 文件
title: 模块定义 (.Def) 文件
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: d52141a2917b2c82616597b2d070a84b96d1a653
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137808"
---
# <a name="module-definition-def-files"></a>模块定义 (.Def) 文件

模块定义 ( .def) 文件为链接器提供有关导出、属性以及与要链接的程序有关的其他信息的信息。 生成 DLL 时，.def 文件最有用。 由于存在可代替模块定义语句使用的 [MSVC 链接器选项](linker-options.md) ，因此通常不需要 .def 文件。 你还可以使用 [__declspec (dllexport) ](../exporting-from-a-dll-using-declspec-dllexport.md) 指定导出函数的方式。

您可以使用/DEF 在链接器阶段调用 .def 文件， [ (指定 Module-Definition file) ](def-specify-module-definition-file.md) 链接器选项。

如果生成的 .exe 文件没有导出，则使用 .def 文件会使输出文件更大且更慢。

有关示例，请参阅 [使用 DEF 文件从 DLL 导出](../exporting-from-a-dll-using-def-files.md)。

有关详细信息，请参阅下列各节：

- [Module-Definition 语句的规则](rules-for-module-definition-statements.md)

- [导出](exports.md)

- [HEAPSIZE](heapsize.md)

- [类库](library.md)

- [NAME](name-c-cpp.md)

- [个](sections-c-cpp.md)

- [STACKSIZE](stacksize.md)

- [存根](stub.md)

- [VERSION](version-c-cpp.md)

- [保留字](reserved-words.md)

## <a name="see-also"></a>请参阅

[C/C++ 生成参考](c-cpp-building-reference.md)<br/>
[MSVC 链接器选项](linker-options.md)
