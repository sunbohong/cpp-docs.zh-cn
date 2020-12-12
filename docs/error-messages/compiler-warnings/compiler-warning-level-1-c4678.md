---
description: 了解详细信息：编译器警告 (等级 1) C4678
title: 编译器警告（等级 1）C4678
ms.date: 11/04/2016
f1_keywords:
- C4678
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
ms.openlocfilehash: a590bd03ba73fc4f8d5421727e5e35ac1384ffaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285378"
---
# <a name="compiler-warning-level-1-c4678"></a>编译器警告（等级 1）C4678

基类“base_type”的可访问性比“derived_type”低

某个公共类型是从私有类型派生的。 如果在引用的程序集中实例化该公共类型，将无法访问私有基类型的成员。

只能使用过时的编译器选项 **/clr： oldSyntax** 来访问 C4678。 使用 **/clr** 时，它是一个错误，它的派生类的可访问性较低。
