---
description: 了解详细信息：排除导入属性
title: 排除 import 特性
ms.date: 08/29/2019
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: e856544f812fd5d0b14676beb8423c4350e40da1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269310"
---
# <a name="exclude-import-attribute"></a>排除 import 特性

**C++ 专用**

从要生成的类型库标头文件中排除项。

## <a name="syntax"></a>语法

> **#import** *类型-库***排除 (** "*Name1*" [ **，** "*Name2*" ...]**)**

### <a name="parameters"></a>parameters

*Name1*\
要排除的第一项。

*Name2*\
如有必要， (可选) 要排除的第二个和更高版本。

## <a name="remarks"></a>备注

类型库可能包含在系统标头文件或其他类型库中定义的项的定义。 此特性可以采用任意数量的参数，其中每个参数都是要排除的顶级类型库项。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
