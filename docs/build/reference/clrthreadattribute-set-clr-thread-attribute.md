---
description: '了解详细信息：/CLRTHREADATTRIBUTE (设置 CLR 线程特性) '
title: /CLRTHREADATTRIBUTE（设置 CLR 线程特性）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
ms.openlocfilehash: 119797ee10ed0c08477b8e08635605e4299ffd41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179117"
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE（设置 CLR 线程特性）

显式指定 CLR 程序入口点的线程特性。

## <a name="syntax"></a>语法

```
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}
```

#### <a name="parameters"></a>parameters

**MTA**<br/>
将 MTAThreadAttribute 特性应用于程序的入口点。

**NONE**<br/>
与不指定/CLRTHREADATTRIBUTE. 相同  使公共语言运行时 (CLR) 设置默认线程特性。

**STA**<br/>
将 STAThreadAttribute 特性应用于程序的入口点。

## <a name="remarks"></a>备注

设置 thread 特性仅在生成 .exe 时有效，因为它会影响主线程的入口点。

例如，如果使用 (main 或 wmain 的默认入口点，则) 使用/CLRTHREADATTRIBUTE 或通过将线程特性置于默认项函数上 (STAThreadAttribute 或 MTAThreadAttribute) 来指定线程模型。

如果使用非默认入口点，请使用/CLRTHREADATTRIBUTE 或通过将线程特性置于非默认项函数来指定线程模型，然后使用 [/ENTRY](entry-entry-point-symbol.md)指定非默认入口点。

如果源代码中指定的线程模型不同意使用/CLRTHREADATTRIBUTE 指定的线程模型，则链接器将忽略/CLRTHREADATTRIBUTE 并应用在源代码中指定的线程模型。

例如，如果您的 CLR 程序托管使用单线程的 COM 对象，则必须使用单线程。  如果 CLR 程序使用多线程处理，则它不能承载使用单线程的 COM 对象。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 展开“配置属性”节点。

1. 展开“链接器”节点。

1. 选择“高级”属性页。

1. 修改 **CLR 线程特性** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
