---
description: '了解详细信息：/LARGEADDRESSAWARE (处理大地址) '
title: /LARGEADDRESSAWARE（处理大地址）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
ms.openlocfilehash: 72b2ba20b2ea2b91ecd234497c433bcdd9e9ee42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199566"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE（处理大地址）

```
/LARGEADDRESSAWARE[:NO]
```

## <a name="remarks"></a>备注

/LARGEADDRESSAWARE 选项告知链接器应用程序可以处理大于 2 gb 的地址。 在64位编译器中，默认情况下启用此选项。 在32位编译器中，如果未在链接器行上指定/LARGEADDRESSAWARE，则不启用/LARGEADDRESSAWARE： NO。

如果应用程序是与/LARGEADDRESSAWARE 链接的，则 DUMPBIN [/HEADERS](headers.md) 将显示该效果的信息。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **系统** " 属性页。

1. 修改 " **启用大地址** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
