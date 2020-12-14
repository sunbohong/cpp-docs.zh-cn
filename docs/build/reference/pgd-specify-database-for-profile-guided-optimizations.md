---
description: '了解详细信息：/PGD (指定数据库 Profile-Guided 优化) '
title: /PGD（为按配置文件优化指定数据库）
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
ms.openlocfilehash: 7030ddaef33c6ee794c470df2c42c72d78555369
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225981"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD（为按配置文件优化指定数据库）

**/PGD 选项已弃用。** 从 Visual Studio 2015 开始，改用 [/GENPROFILE 或/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 链接器选项。 此选项用于指定按配置优化过程使用的 .pgd 文件的名称。

## <a name="syntax"></a>语法

> **/PGD：**_文件名_

## <a name="argument"></a>参数

*filename*<br/>
指定 .pgd 文件的名称，该文件用于保存有关正在运行的程序的信息。

## <a name="remarks"></a>备注

使用弃用的 [/ltcg： PGINSTRUMENT](ltcg-link-time-code-generation.md) 选项时，请使用 **/PGD** 为 .pgd 文件指定非默认名称或位置。 如果未指定 **/PGD**，则 .pgd 文件基名称与输出文件 ( .exe 或 .dll) 基名称相同，并且是在从中调用链接的同一目录中创建的。

使用弃用的 **/ltcg： PGOPTIMIZE** 选项时，请使用 **/PGD** 选项来指定要用于创建优化映像的 .pgd 文件的名称。 *Filename* 参数应与指定给 **/ltcg： PGINSTRUMENT** 的 *文件名* 匹配。

有关详细信息，请参阅[按配置优化](../profile-guided-optimizations.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **优化**" 属性页。

1. 修改 " **按配置文件** " 属性。 选择“确定”以保存更改  。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)<br/>
