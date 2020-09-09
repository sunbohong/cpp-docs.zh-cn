---
title: 将静态链接设置为注册器代码（仅限 C++）
description: 如何将 c + + 代码静态链接到 ATL 注册器代码。
ms.date: 09/03/2020
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: f08f7d9433ae1344c7a98a5c52502d03bad21e91
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609163"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>设置与注册器代码的静态链接 (仅限 c + +) 

C + + 客户端可以创建指向注册器代码的静态链接。 注册器的分析程序的静态链接将大约在发布版本中添加了大量。

设置静态链接的最简单方法是 [`DECLARE_REGISTRY_RESOURCEID`](reference/registry-macros.md#declare_registry_resourceid) 在对象的声明中指定。  (它是 ATL 使用的默认规范。 ) 

## <a name="to-create-a-static-link-using-declare_registry_resourceid"></a>使用创建静态链接 `DECLARE_REGISTRY_RESOURCEID`

1. **`/D _ATL_STATIC_REGISTRY`** **`/D _ATL_DLL`** 在 CL 命令行上指定而不是。 有关详细信息，请参阅 [`/D`](../build/reference/d-preprocessor-definitions.md)。

1. 重新编译.

## <a name="see-also"></a>请参阅

[注册表组件 (注册器) ](../atl/atl-registry-component-registrar.md)
