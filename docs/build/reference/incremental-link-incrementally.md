---
description: '了解详细信息：/INCREMENTAL (链接增量) '
title: /INCREMENTAL（增量链接）
ms.date: 11/04/2016
f1_keywords:
- /incremental
- VC.Project.VCLinkerTool.LinkIncremental
helpviewer_keywords:
- /INCREMENTAL linker option
- -INCREMENTAL linker option
- INCREMENTAL linker option
- link incrementally option
- LINK tool [C++], options for full linking
- incremental linking
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
ms.openlocfilehash: 4b115bd88bed5b012c29c3d0e61d471aa869b78a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191285"
---
# <a name="incremental-link-incrementally"></a>/INCREMENTAL（增量链接）

```
/INCREMENTAL[:NO]
```

## <a name="remarks"></a>备注

控制链接器处理增量链接的方式。

默认情况下，链接器以增量模式运行。 若要重写默认增量链接，请指定 /INCREMENTAL:NO。

增量链接的程序在功能上等效于非增量链接的程序。 但是，因为它是为后续增量链接而准备的，所以增量链接的可执行文件、静态库或动态链接库文件：

- 大于非增量链接的程序，因为有代码和数据的填充。 填充使链接器可以增加函数和数据的大小，而无需重新创建文件。

- 可以包含跳转 thunk 以处理函数重定位到新地址。

   > [!NOTE]
   > 为了确保最终发布版本不包含填充或 thunk，请以非增量方式链接程序。

若要增量链接而不管默认值，请指定 /INCREMENTAL。 选中此选项后，如果链接器无法增量链接，则链接器将发出警告，然后以非增量方式链接程序。 某些选项和情况重写 /INCREMENTAL。

大多数程序都可以增量链接。 但是，某些更改太大，还有某些选项与增量链接不兼容。 如果指定了以下任一选项，则 LINK 执行完全链接：

- 未选定增量链接 (/INCREMENTAL:NO)

- 选定 /OPT:REF

- 选定 /OPT:ICF

- 选定 /OPT:LBR

- 选定 /ORDER

指定 [/debug](debug-generate-debug-info.md) 时，/INCREMENTAL 是隐含的。

此外，如果发生以下任何情况，则 LINK 执行完全链接：

- 缺少增量状态 (.ilk) 文件。 （LINK 将创建新的 .ilk 文件以为后面的增量链接作准备。）

- 对 .ilk 文件没有写入权限。  (链接将忽略 .ilk 文件并以非增量方式链接。 ) 

- 缺少 .exe 或 .dll 输出文件。

- 更改了 .ilk、.exe 或 .dll 的时间戳。

- 更改了 LINK 选项。 大多数 LINK 选项在各生成间更改时会导致完全链接。

- 添加或省略了对象 (.obj) 文件。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **链接器** " 文件夹。

1. 选择 **“常规”** 属性页。

1. 修改 " **启用增量链接** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
