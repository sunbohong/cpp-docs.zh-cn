---
description: '了解更多相关信息：/Zf (加速 PDB 生成) '
title: /Zf（更快的 PDB 生成）
ms.date: 03/29/2018
f1_keywords:
- /Zf
helpviewer_keywords:
- /Zf
- -Zf
ms.openlocfilehash: 6acf84de3c286131f470808505cdf0e895feeaeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178883"
---
# <a name="zf-faster-pdb-generation"></a>/Zf（更快的 PDB 生成）

通过最大程度地减少对 mspdbsrv.exe 的 RPC 调用，并行生成中实现更快的 PDB 生成。

## <a name="syntax"></a>语法

> **/Zf**

## <a name="remarks"></a>备注

使用 **/Zf** 选项可以更快地生成 PDB 文件（在使用 [/Mp (使用多个进程) 选项生成](mp-build-with-multiple-processes.md) 时）; 或者，如果生成系统 (，则 [MSBuild](/visualstudio/msbuild/msbuild-reference) 或 [CMake](../cmake-projects-in-visual-studio.md)) 可同时运行多个 cl.exe 编译器进程。 此选项将导致编译器前端延迟 PDB 文件中每个类型记录的类型索引的生成，直到编译结束，然后在单个 RPC 调用中将它们全部请求到 mspdbsrv.exe，而不是对每个记录发出 RPC 请求。 这可以通过减少运行多个 cl.exe 编译器进程的环境中 mspdbsrv.exe 进程的 RPC 负载来大幅提高生成吞吐量。

由于 **/Zf** 选项仅适用于 PDB 生成，因此它需要 [/zi](z7-zi-zi-debug-information-format.md) 或 [/zi](z7-zi-zi-debug-information-format.md) 选项。

从 Visual Studio 2017 15.1 版开始， **/Zf** 选项在默认情况下处于关闭状态。 从 Visual Studio 2017 版本15.7 预览版3开始，默认情况下，当启用 **/zi** 或 **/zi** 选项时，此选项处于启用状态。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以包含 **/Zf** ，然后选择 **"确定"**。

## <a name="see-also"></a>请参阅

[按字母顺序列出的编译器选项](compiler-options-listed-alphabetically.md)<br/>
[具有多个进程的/MP (生成) ](mp-build-with-multiple-processes.md)<br/>
