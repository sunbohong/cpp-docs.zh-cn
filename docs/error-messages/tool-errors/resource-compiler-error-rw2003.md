---
description: 了解更多：资源编译器错误 RW2003
title: 资源编译器错误 RW2003
ms.date: 11/04/2016
f1_keywords:
- RW2003
helpviewer_keywords:
- RW2003
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
ms.openlocfilehash: 545168aae1c483c358c55dfc90ce320aafac3ca2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259677"
---
# <a name="resource-compiler-error-rw2003"></a>资源编译器错误 RW2003

生成错误

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. **错误：位图文件资源-文件的格式不是3.00**

   使用的 Windows 版本 2.x 格式的位图不能用于版本 3.x 资源文件。 必须重绘该位图或将其转换为1.x 格式。

1. **错误：资源名称中存在旧 DIB。通过 SDKPAINT 传递**

   指定资源中与设备无关的位图 (DIB) 与 Windows 3.0 格式不兼容。 必须重绘该位图或将其转换为1.x 格式。

1. **错误：资源文件资源名称不是3.00 格式**

   指定资源中的图标或光标使用以前版本的 Windows 中的格式。 图标或光标必须重绘或转换为1.x 格式。

1. **未知的 DIB 标题格式**

   Bitmap 标头不是 BITMAPCOREHEADER 或 BITMAPINFOHEADER 结构。

1. **无法初始化符号信息**

   此错误仅出现在 Visual C++ 中。 可能的原因是，打开的文件太多，或者无法打开或写入 Visual C++ 导入脚本中的符号所需的数据文件。 Visual C++ 尝试在 **TMP** 环境变量指定的目录或当前目录中创建这些文件（如果未指定）。

1. **无法保存符号信息**

   此错误仅出现在 Visual C++ 中。 可能的原因是，打开的文件太多，或者无法关闭或写入 Visual C++ 导入脚本中的符号所需的数据文件。 Visual C++ 尝试在 **TMP** 环境变量指定的目录或当前目录中使用这些文件（如果未指定）。

1. **位图文件资源文件的格式不是2.03**

   位图使用了早于 2.03 版的格式。 必须使用 3.00 版或更高版本的格式转换或重绘该位图。

1. **资源太大**

   对于 Windows 3.1，资源的长度不能超过65000个字节。 如果资源确实如此，则无法用 Visual C++ 或命令行资源编译器对其进行编译。 该限制不适用于游标、图标、位图或其他基于文件的资源。

1. **资源文件的格式不是3.00**

   使用早于版本3.00 的格式的游标或图标。 必须使用3.00 版或更高版本的格式转换或重绘资源。

1. **无法打开临时文件**

   资源编译器/Visual C++ 无法打开临时文件。 可能的原因是您没有目录的写入权限或该目录不存在。 资源编译器/Visual C++ 尝试在 **TMP** 环境变量指定的目录或当前目录（如果未指定任何目录）中使用这些文件。
