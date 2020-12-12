---
description: 了解详细信息： inject_statement import 特性
title: inject_statement 导入属性
ms.date: 08/29/2019
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: b7ab8059e95ed3799857fe1b899ef2efff729ffb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236420"
---
# <a name="inject_statement-import-attribute"></a>inject_statement 导入属性

**C++ 专用**

将其自变量作为源文本插入类型库标头。

## <a name="syntax"></a>语法

> **#import** *类型库* **inject_statement (** "*源文本*" **)**

### <a name="parameters"></a>parameters

*源-文本*\
要插入类型库标头文件的源文本。

## <a name="remarks"></a>备注

文本位于命名空间声明的开头，该声明在标头文件中包装 *类型库* 内容。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
