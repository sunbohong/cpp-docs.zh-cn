---
description: '了解详细信息：/MERGE (合并部分) '
title: /MERGE（合并节）
ms.date: 11/04/2016
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
ms.openlocfilehash: 579e5432facd6deb8d2b26b997d9b61f167d2b3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199098"
---
# <a name="merge-combine-sections"></a>/MERGE（合并节）

```
/MERGE:from=to
```

## <a name="remarks"></a>备注

/MERGE 选项将第一节 (*从*) ，第二部分结合 (*到*) ，并将生成的部分命名 *为*。 例如 `/merge:.rdata=.text`。

如果第二个部分不存在，则 LINK 将节 *从* 重命名 *为。*

/MERGE 选项对于创建 Vxd 和重写编译器生成的部分名称很有用。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **高级** " 属性页。

1. 修改 **合并部分** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
