---
description: '了解详细信息：/TLBID (指定类型库的资源 ID) '
title: /TLBID（指定类型库的资源 ID）
ms.date: 11/04/2016
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
ms.openlocfilehash: 4958229cbebe988867c5419d7953b6ffd968e45f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230011"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID（指定类型库的资源 ID）

```
/TLBID:id
```

## <a name="arguments"></a>参数

*id*<br/>
链接器创建的类型库的用户指定值。 它覆盖默认资源 ID 1。

## <a name="remarks"></a>备注

在编译使用属性的程序时，链接器将创建类型库。 链接器将资源 ID 1 分配给类型库。

如果此资源 ID 与现有资源之一冲突，可以通过/TLBID. 指定其他 ID。 可以传递到的值的范围是从 `id` 1 到65535。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 **嵌入的 IDL** 属性页。

1. 修改 **TypeLib 资源 ID** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
