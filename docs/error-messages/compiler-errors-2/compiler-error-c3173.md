---
description: 了解更多：编译器错误 C3173
title: 编译器错误 C3173
ms.date: 11/04/2016
f1_keywords:
- C3173
helpviewer_keywords:
- C3173
ms.assetid: edf79e10-e8cf-4f76-8d33-ab9d05e974e9
ms.openlocfilehash: a398a42823e87b7f89f455ee20b6dc1cfc3a7f1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242153"
---
# <a name="compiler-error-c3173"></a>编译器错误 C3173

idl 合并中的版本不匹配

当对象文件包含使用以前版本的编译器生成的嵌入 idl 时，将出现此错误。 编译器对版本号进行编码，以确保用于生成嵌入到 .obj 文件中的 idl 内容的相同编译器也是用于合并嵌入 idl 的相同编译器。

更新 Visual C++ 安装，以便所有工具都来自最新的已发布版本。
