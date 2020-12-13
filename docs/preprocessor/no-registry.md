---
description: 了解详细信息： no_registry import 特性
title: no_registry 导入属性
ms.date: 08/29/2019
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: fa33bf8096a92ec248b0a9d56e39fcc82f433206
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333298"
---
# <a name="no_registry-import-attribute"></a>no_registry 导入属性

**no_registry** 通知编译器不要在注册表中搜索导入的类型库 `#import` 。

## <a name="syntax"></a>语法

> **#import** *类型-库* **no_registry**

### <a name="parameters"></a>parameters

*类型库*\
类型库。

## <a name="remarks"></a>备注

如果在 include 目录中找不到引用的类型库，则即使类型库位于注册表中，编译也会失败。  **no_registry** 传播到用隐式导入的其他类型库 `auto_search` 。

编译器决不会在注册表中搜索由文件名指定并直接传递到的类型库 `#import` 。

`auto_search`指定时，将 `#import` 使用初始的 **no_registry** 设置生成其他指令 `#import` 。 如果 no_registry 初始 `#import` 指令， 则 `auto_search` `#import` 还会 **no_registry** 生成的。

如果要导入交叉引用的类型库， **no_registry** 会很有用。 它使编译器无法在注册表中查找文件的较旧版本。 如果未注册类型库， **no_registry** 也很有用。

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
