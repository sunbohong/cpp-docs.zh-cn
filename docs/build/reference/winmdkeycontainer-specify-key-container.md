---
description: '了解详细信息：/WINMDKEYCONTAINER (指定密钥容器) '
title: /WINMDKEYCONTAINER（指定密钥容器）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 94b203c56b7724c2b2569ba22039da38c4501985
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258988"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER（指定密钥容器）

指定用于对 Windows 元数据 (.winmd) 文件进行签名的密钥容器。

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>备注

类似于应用于 ( winmd) 文件的 [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md) 链接器选项。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **链接器** " 文件夹。

1. 选择 " **Windows 元数据** " 属性页。

1. 在 " **Windows 元数据密钥容器** " 框中，输入位置。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
