---
description: '了解详细信息：/LIBPATH (其他 Libpath) '
title: /LIBPATH（附加的 Libpath）
ms.date: 11/04/2016
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
ms.openlocfilehash: 5db7a0f80cb741a65bac5a4dbb7fd79e28b67459
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191025"
---
# <a name="libpath-additional-libpath"></a>/LIBPATH（附加的 Libpath）

```
/LIBPATH:dir
```

## <a name="parameters"></a>parameters

*dir*<br/>
指定链接器将在搜索 LIB 环境选项中指定的路径之前搜索的路径。

## <a name="remarks"></a>备注

使用/LIBPATH 选项重写环境库路径。 链接器将首先搜索此选项指定的路径，然后在 LIB 环境变量中指定的路径中进行搜索。 对于输入的每个/LIBPATH 选项，只能指定一个目录。 如果要指定多个目录，则必须指定多个/LIBPATH 选项。 然后，链接器将按顺序搜索指定的目录。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **常规** " 属性页。

1. 修改 " **附加库目录** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
