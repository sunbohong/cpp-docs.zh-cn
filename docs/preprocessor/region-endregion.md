---
description: pragma在 Microsoft c/c + + 中了解有关 region 和 endregion 指令的详细信息
title: 区域和 endregion pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragma, region
- pragma, endregion
- endregion pragma
- region pragma
no-loc:
- pragma
ms.openlocfilehash: 68964cd2cab4ff344a8319f970f7ee94be4d378d
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713280"
---
# <a name="region-and-endregion-no-locpragma"></a>`region` 和 `endregion` pragma

`#pragma region` 使用 Visual Studio 编辑器的 [大纲显示功能](/visualstudio/ide/outlining) ，您可以指定可展开或折叠的代码块。

## <a name="syntax"></a>语法

> **`#pragma region`***名称*\
> **`#pragma endregion`***注释*

### <a name="parameters"></a>Parameters

*条*\
 (可选) 要在代码编辑器中显示的注释。

*路径名*\
 (可选) 区域的名称。 此名称显示在代码编辑器中。

## <a name="remarks"></a>注解

`#pragma endregion` 标记块的结尾 `#pragma region` 。

`#pragma region`块必须由 `#pragma endregion` 指令终止。

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

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
