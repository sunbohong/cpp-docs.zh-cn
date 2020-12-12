---
description: 了解详细信息：链接器工具错误 LNK1312
title: 链接器工具错误 LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: d861b6976f9b065e3a693e916164879a3311d3db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193625"
---
# <a name="linker-tools-error-lnk1312"></a>链接器工具错误 LNK1312

无效或损坏的文件：无法导入程序集

生成程序集时，不是使用 **/clr** 编译的模块或程序集的文件被传递到 **/ASSEMBLYMODULE** 链接器选项。  如果向 **/ASSEMBLYMODULE** 传递了对象文件，只需将对象直接传递给链接器，而不是传递到 **/ASSEMBLYMODULE**。

## <a name="examples"></a>示例

下面的示例创建了 .obj 文件。

```cpp
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

下面的示例生成 LNK1312。

```cpp
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```
