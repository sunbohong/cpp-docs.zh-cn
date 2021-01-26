---
title: '/Zc： hiddenFriend (强制实施标准 c + + 隐藏的 friend 规则) '
description: 了解适用于相容或宽松隐藏的 friend 兼容性的 Microsoft c + +/Zc： hiddenFriend 编译器选项。
ms.date: 01/23/2021
f1_keywords:
- /Zc:hiddenFriend
helpviewer_keywords:
- /Zc:hiddenFriend
- Zc:hiddenFriend
- -Zc:hiddenFriend
ms.openlocfilehash: 5a3487cc4899cf6a07e91dc5ce5b7cd8f8784737
ms.sourcegitcommit: 74e58bee5cffb30b66e17be6dbfde2544369638e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "98766864"
---
# <a name="zchiddenfriend-enforce-standard-c-hidden-friend-rules"></a>`/Zc:hiddenFriend` (强制实施标准 c + + 隐藏的 friend 规则) 

指定编译器符合隐藏的 friend 函数或函数模板的 c + + 标准处理方式。

## <a name="syntax"></a>语法

> **`/Zc:hiddenFriend`**\[**`-`**]

## <a name="remarks"></a>备注

**`/Zc:hiddenFriend`** 选项可启用部分 [`/permissive-`](permissive-standards-conformance.md) 选项行为。 它指示编译器符合隐藏的朋友的标准。 编译器仅在 [依赖于参数的查找](../../cpp/argument-dependent-name-koenig-lookup-on-functions.md) 中包括隐藏的朋友 (ADL) 用于显式实例或封闭类类型的模板参数。 此限制允许使用隐藏的好友来使类型上的操作不会应用于隐式转换。 此选项可以在无法以其他方式使用的代码中提高生成速度 [`/permissive-`](permissive-standards-conformance.md) 。

*隐藏的友元* 是 **`friend`** 仅在类或类模板定义中声明的函数或函数模板。 默认情况下，Microsoft c + + 编译器不会删除隐藏的友元声明作为重载决策应使用的候选项。 这种旧行为会使编译器降低，因为在多个上下文中将隐藏的友元函数作为可能的候选项。

默认情况下，在下启用标准 c + + 隐藏的 friend 行为 **`/permissive-`** 。 若要在指定选项时指定旧版隐藏的 friend 行为 **`/permissive-`** ，请使用 **`/Zc:hiddenFriend-`** 。 使用 c + + 20 模块需要标准隐藏的 friend 行为。

**`/Zc:hiddenFriend`** 从 Visual Studio 2019 版本16.4 开始，可以使用选项。

有关指定时编译器行为的示例 **`/Zc:hiddenFriend`** ，请参阅 [隐藏的好友名称查找规则](./permissive-standards-conformance.md#hidden-friend-name-lookup-rules)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以包含 *`/Zc:hiddenFriend`* 或 *`/Zc:hiddenFriend-`* ，然后选择 **"确定"**。

## <a name="see-also"></a>另请参阅

[`/Zc` (一致性) ](zc-conformance.md)\
[`/permissive-`](permissive-standards-conformance.md)
