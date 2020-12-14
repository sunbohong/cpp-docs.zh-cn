---
description: '了解有关以下内容的详细信息：/link (将选项传递给链接器) '
title: /link（将选项传递到链接器）
ms.date: 03/25/2019
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: 3617a005e6adbc41a589606aa145712fa2df442d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199488"
---
# <a name="link-pass-options-to-linker"></a>/link（将选项传递到链接器）

将一个或多个链接器选项传递到链接器。

## <a name="syntax"></a>语法

> **/link** *链接器-选项*

## <a name="arguments"></a>参数

*链接器-选项*<br/>
要传递给链接器的链接器选项或选项。

## <a name="remarks"></a>备注

**/Link** 选项及其链接器选项必须出现在任何文件名和 CL 选项之后。 **/Link** 和任何链接器选项之间需要有一个空格。 有关详细信息，请参阅 [MSVC 链接器引用](linking.md)。

## <a name="example"></a>示例

此示例命令行编译 *你好* ，并将其链接到现有对象文件 *。 .obj*。然后，它将其他 **/VERSION** 命令传递给链接器：

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

IDE 通常发送单独的命令来编译和链接代码。 您可以在项目属性页中设置链接器选项。

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**" 文件夹。

1. 修改一个或多个属性。 选择“确定”以保存更改  。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 不能以编程方式更改此编译器选项。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
