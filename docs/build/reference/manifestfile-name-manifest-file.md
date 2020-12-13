---
description: '了解详细信息：/MANIFESTFILE (名称清单文件) '
title: /MANIFESTFILE（命名清单文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
ms.openlocfilehash: a0d3a4ba1d17c4aa8c97cb09cc768e614e46c864
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138016"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE（命名清单文件）

```
/MANIFESTFILE:filename
```

## <a name="remarks"></a>备注

/MANIFESTFILE 使你可以更改清单文件的默认名称。  清单文件的默认名称是附加了 .manifest 的文件名。

如果你还不链接到 [/MANIFEST](manifest-create-side-by-side-assembly-manifest.md)，则/MANIFESTFILE 将不起作用。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 展开“配置属性”节点。

1. 展开“链接器”节点。

1. 选择 " **清单文件** " 属性页。

1. 修改 **清单文件** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
