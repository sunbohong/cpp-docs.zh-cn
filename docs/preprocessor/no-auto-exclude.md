---
description: 了解详细信息： no_auto_exclude import 特性
title: no_auto_exclude 导入属性
ms.date: 08/29/2019
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 81e4d7e7f9295a4ed983e2a5024d891e30fe1361
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333347"
---
# <a name="no_auto_exclude-import-attribute"></a>no_auto_exclude 导入属性

**C++ 专用**

禁用自动排除。

## <a name="syntax"></a>语法

> **#import** *类型-库* **no_auto_exclude**

## <a name="remarks"></a>备注

类型库可能包含在系统标头文件或其他类型库中定义的项的定义。 `#import` 尝试通过自动排除此类项来避免多个定义错误。 这会导致为要排除的每个项发出 [编译器警告 (级别 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) 。 您可以使用此属性禁用自动排除。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
