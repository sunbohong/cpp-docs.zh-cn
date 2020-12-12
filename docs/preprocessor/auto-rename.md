---
description: 了解详细信息： auto_rename import 特性
title: auto_rename 导入属性
ms.date: 08/29/2019
f1_keywords:
- auto_rename
helpviewer_keywords:
- auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
ms.openlocfilehash: 57406b1f64b3e5e484556ae15600cc30f1e931dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301030"
---
# <a name="auto_rename-import-attribute"></a>auto_rename 导入属性

**C++ 专用**

通过将两个下划线 (__) 追加到变量名称来重命名 C++ 保留字，从而解决可能的名称冲突。

## <a name="syntax"></a>语法

> **#import** *类型-库* **auto_rename**

## <a name="remarks"></a>备注

当导入将一个或多个 C++ 保留字（关键字或宏）用作变量名称的类型库时，使用此特性。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
