---
description: '了解详细信息：/DLL (生成 DLL) '
title: /DLL（生成 DLL）
ms.date: 11/04/2016
f1_keywords:
- /dll
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
ms.openlocfilehash: 42535fb15762e5c0f1691d5c28029c7368005f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201399"
---
# <a name="dll-build-a-dll"></a>/DLL（生成 DLL）

```
/DLL
```

## <a name="remarks"></a>备注

/DLL 选项将 DLL 作为主输出文件生成。 DLL 通常包含可以由其他程序使用的导出。 有三种方法可以指定导出，按建议使用顺序列出：

1. 在源代码中[__declspec (dllexport) ](../../cpp/dllexport-dllimport.md)

1. .Def 文件中的 [导出](exports.md) 语句

1. LINK 命令中的 [/export](export-exports-a-function.md) 规范

程序可以使用多种方法。

生成 DLL 的另一种方法是使用 **库** 模块定义语句。 /BASE 和/DLL 选项一起与 **LIBRARY** 语句等效。

不要在开发环境中指定此选项;此选项仅在命令行上使用。 使用应用程序向导创建 DLL 项目时，会设置此选项。

请注意，如果在初步步骤中创建了导入库，则在创建 .dll 之前，必须在生成 .dll 时传递相同的对象文件集，就像生成导入库时传递的一样。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 " **配置属性** " 文件夹。

1. 单击 " **常规** " 属性页。

1. 修改 " **配置类型** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
