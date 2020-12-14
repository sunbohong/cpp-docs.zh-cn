---
description: 了解详细信息：指定路径名
title: 指定路径名
ms.date: 11/04/2016
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
ms.openlocfilehash: a8c55822bcb19864955ffa37ef2dd4cb18765ae5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224525"
---
# <a name="specifying-the-pathname"></a>指定路径名

每个输出文件选项都接受 *路径名* 参数，该参数可指定输出文件的位置和名称。 参数可以包含驱动器名称、目录和文件名。 选项与参数之间不允许有空格。

如果 *pathname* 包含不带扩展名的文件名，则编译器会为输出提供默认扩展。 如果 *pathname* 包含一个目录，但没有文件名，则编译器将在指定的目录中创建具有默认名称的文件。 默认名称基于源文件的基名称和基于输出文件的类型的默认扩展名。 如果完全关闭 *路径名* ，编译器将在默认目录中创建一个默认名称为的文件。

或者， *pathname* 参数可以是 (AUX、CON、PRN 或 NUL) 的设备名称，而不是文件名。 请不要在选项和设备名称之间使用空格，也不要使用冒号作为设备名称的一部分。

|设备名称|表示|
|-----------------|----------------|
|AUX|辅助设备|
|CON|控制台|
|PRN|打印机|
|NUL|空设备 (未创建文件) |

## <a name="example"></a>示例

以下命令行向打印机发送映射：

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>请参阅

[Output-File (/F) 选项](output-file-f-options.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
