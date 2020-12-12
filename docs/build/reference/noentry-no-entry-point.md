---
description: '了解详细信息：/NOENTRY (无入口点) '
title: /NOENTRY（无入口点）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
ms.openlocfilehash: c3d1f725a4e185a052d443010894ff2dc2261675
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196680"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY（无入口点）

```
/NOENTRY
```

## <a name="remarks"></a>备注

/NOENTRY 选项是创建不包含可执行代码的纯资源 DLL 所必需的。 有关详细信息，请参阅 [创建 Resource-Only DLL](../creating-a-resource-only-dll.md)。

请使用此选项防止 LINK 将 `_main` 的引用链接到 DLL 中。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **链接器** " 文件夹。

1. 选择“高级”属性页。

1. 修改 " **无入口点** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>。

## <a name="see-also"></a>请参阅

[创建 Resource-Only DLL](../creating-a-resource-only-dll.md)<br/>
[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
