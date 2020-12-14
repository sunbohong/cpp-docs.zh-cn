---
description: '了解详细信息：/WINMD (生成 Windows 元数据) '
title: /WINMD（生成 Windows 元数据）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
ms.openlocfilehash: 7cf52a49716e6ec30a29c7e6a96fe7a078b4830c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259079"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD（生成 Windows 元数据）

启用 Windows 运行时元数据 (.winmd) 文件的生成。

> **/WINMD** \[**：**{**NO NO** \| }]

## <a name="arguments"></a>参数

**/WINMD**<br/>
通用 Windows 平台应用的默认设置。 链接器生成二进制可执行文件和 .winmd 元数据文件。

**/WINMD:NO**<br/>
链接器仅生成二进制可执行文件，但不生成 .winmd 文件。

**/WINMD:ONLY**<br/>
链接器仅生成 .winmd 文件，但不生成二进制可执行文件。

## <a name="remarks"></a>备注

**/WINMD** 链接器选项用于 UWP 应用和 Windows 运行时组件，以控制是否 ( WINMD) 文件创建 Windows 运行时元数据。 Winmd 文件是一种 DLL，其中包含 Windows 运行时类型的元数据，在运行时组件的情况下为这些类型的实现。 元数据遵循 [ECMA-335](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 标准。

默认情况下，输出文件名的格式为 *binaryname*。 若要指定不同的文件名，请使用 [/WINMDFILE](winmdfile-specify-winmd-file.md) 选项。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **Windows 元数据**" 属性页。

1. 在 " **生成 Windows 元数据** " 下拉列表框中，选择所需的选项。

## <a name="see-also"></a>请参阅

[演练：创建简单的 Windows 运行时组件并从 JavaScript 中调用该组件](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Microsoft 接口定义语言3.0 简介](/uwp/midl-3/intro)<br/>
[/WINMDFILE (指定 winmd 文件) ](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (指定 winmd 密钥文件) ](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (指定密钥容器) ](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (部分签署 winmd) ](winmddelaysign-partially-sign-a-winmd.md)<br/>
[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
