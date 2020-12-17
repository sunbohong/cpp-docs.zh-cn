---
description: 详细了解：复制源项目属性 (Linux C++)
title: 复制源项目属性 (Linux C++)
ms.date: 10/16/2019
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: 9c486519e1a37a08531dae82003504838f2032a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169796"
---
# <a name="copy-sources-project-properties-linux-c"></a>复制源项目属性 (Linux C++)

::: moniker range="msvc-140"

Linux 支持在 Visual Studio 2017 及更高版本中提供。

::: moniker-end

::: moniker range=">=msvc-150"

此属性页上设置的属性适用于项目中所有的文件，除设置了文件级属性的文件外。

| properties | 说明 |
|--|--|
| 要复制的源 | 指定要复制到远程系统的源。 更改此列表可能转变或者影响目录结构，文件将在其中被复制到远程系统。 |
| 复制源文件 | 指定是否要将源复制到远程系统。 |
| 要复制的其他源 | 指定要复制到远程系统的其他源。 根据需要，可使用类似 fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2 的语法指定本地到远程的映射对，其中可将本地文件复制到远程系统的指定远程位置。 |

@SourcesToCopyRemotely 和 @DataFilesToCopyRemotely 引用项目文件中的项组。 要修改远程复制的源或数据文件，请按如下所示编辑 vcxproj 文件：

```xml
<ItemGroup>
   <MyItems Include="foo.txt" />
   <MyItems Include="bar.txt" />
   <DataFilesToCopyRemotely Include="@(MyItems)" />
</ItemGroup>
```

::: moniker-end
