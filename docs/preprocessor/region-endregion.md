---
description: 了解详细信息： region、endregion 杂注
title: region、endregion 杂注
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
ms.openlocfilehash: a12305240f0c05913d16c5f26fb64661fc08e736
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167417"
---
# <a name="region-endregion-pragmas"></a>region、endregion 杂注

`#pragma region` 允许你指定一个代码块，当使用 Visual Studio Code 编辑器的 [大纲显示功能](/visualstudio/ide/outlining) 时，可以展开或折叠该代码块。

## <a name="syntax"></a>语法

> **#pragma 区域** *名称*\
> **#pragma endregion** *注释*

### <a name="parameters"></a>parameters

*条*\
 (可选) 要在代码编辑器中显示的注释。

*路径名*\
 (可选) 区域的名称。 此名称显示在代码编辑器中。

## <a name="remarks"></a>备注

`#pragma endregion` 标记块的结尾 `#pragma region` 。

`#region`块必须由 `#pragma endregion` 指令终止。

## <a name="example"></a>示例

```cpp
// pragma_directives_region.cpp
#pragma region Region_1
void Test() {}
void Test2() {}
void Test3() {}
#pragma endregion Region_1

int main() {}
```

## <a name="see-also"></a>请参阅

[Pragma 指令和 __pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
