---
description: 了解详细信息：附加的 MSVC 生成工具
title: 其他 MSVC 生成工具
ms.date: 08/28/2019
f1_keywords:
- c.build
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
ms.openlocfilehash: 41395edcbc2f375b4173f2cff25cbcac581ee5d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182640"
---
# <a name="additional-msvc-build-tools"></a>其他 MSVC 生成工具

Visual Studio 提供了以下命令行实用程序，用于查看或操作生成输出：

- [LIB.EXE](lib-reference.md) 用于创建和管理 (COFF) 对象文件的通用对象文件格式库。 它还可用于创建导出文件和导入库，以便引用导出的定义。

- [EDITBIN.EXE](editbin-reference.md) 用于修改 COFF 二进制文件。

- [DUMPBIN.EXE](dumpbin-reference.md) 显示信息 (如有关 COFF 二进制文件的符号表) 。

- [NMAKE](nmake-reference.md) 读取和执行生成的。

- [ERRLOOK](value-edit-control.md)，错误查找实用工具根据输入的值检索系统错误消息或模块错误消息。

- [XDCMake](xdcmake-reference.md)。 用于处理源代码文件的工具，其中包含用 XML 标记标记的文档注释。

- 为实现向后兼容性而提供[BSCMAKE.EXE](bscmake-reference.md) (仅) 生成一个 ( .bsc 的浏览信息文件，其中包含有关程序中) 类、函数、数据、宏和类型 (符号的信息。 可在开发环境中的 "浏览" 窗口中查看此信息。  (.bsc 文件也可以在开发环境中生成。 ) 

Windows SDK 还包含多个生成工具，包括 [RC.EXE](/windows/win32/menurc/resource-compiler)，c + + 编译器将调用这些工具来编译本机 Windows 资源，如对话框、属性页、位图、字符串表等。

## <a name="see-also"></a>请参阅

[C/C++ 生成参考](c-cpp-building-reference.md)<br/>
[修饰名](decorated-names.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 链接器选项](linker-options.md)
