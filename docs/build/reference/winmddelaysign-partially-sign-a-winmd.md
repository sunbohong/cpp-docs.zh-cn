---
description: '了解详细信息：/WINMDDELAYSIGN (部分签署 winmd) '
title: /WINMDDELAYSIGN（对 winmd 进行部分签名）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 801b172f52a9beb9d09617644b3096e460359724
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259053"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN（对 winmd 进行部分签名）

通过将公钥部分放在 Windows 运行时元数据 (.winmd) 文件中来启用该文件的部分签名。

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>备注

类似于应用于 winmd 文件的 [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) 链接器选项。 如果只希望将公钥放在 winmd 文件中，请使用 **/WINMDDELAYSIGN** 。 默认情况下，链接器的行为类似于指定了 **/WINMDDELAYSIGN： NO** ;也就是说，它不会对 winmd 文件进行签名。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **链接器** " 文件夹。

1. 选择 " **Windows 元数据** " 属性页。

1. 在 " **Windows 元数据延迟签名** " 下拉列表框中，选择所需的选项。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
