---
description: 详细了解：编译器警告 (等级 3) C4635
title: 编译器警告（等级 3）C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: e885c501e4f10719618bb552c153dc13a481332d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168327"
---
# <a name="compiler-warning-level-3-c4635"></a>编译器警告（等级 3）C4635

XML 文档注释目标: XML 格式不正确: 原因

编译器发现此 XML 标记存在一些问题。  解决该问题并重新编译

下面的示例生成 C4635：

```cpp
// C4635.cpp
// compile with: /doc /clr /W3 /c
/// <summary>
/// The contents of the folder have changed.
/// <summary/>   // C4635

// try the following line instead
// /// </summary>
public ref class Test {};
```

请注意，此示例的输出显示： **结束标记“member”与开始标记“summary”不匹配。**

此示例的问题是，的结束标记的 \<summary> 格式不正确，编译器不会将其识别为 \<summary> 结束标记。  \<member>编译器将在每个/doc 编译中将标记嵌入到 .xdc 文件中。  因此，此处的问题是结束标记 \</member> 与编译器处理 (的上一个开始标记不匹配 \<summary> 。
