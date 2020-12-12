---
description: '了解详细信息：节 (C/c + +) '
title: SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: aaebeb19c921dfb389c55209c7a371f49043cb56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224759"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)

在 `definitions` 项目输出文件的节中引入了一个或多个作为访问说明符的部分。

```
SECTIONS
definitions
```

## <a name="remarks"></a>备注

每个定义必须在单独一行上。 `SECTIONS`关键字可以与第一个定义位于同一行上，也可以位于前面的行上。 .Def 文件可以包含一个或多个 `SECTIONS` 语句。

此 `SECTIONS` 语句为图像文件中的一个或多个部分设置属性，可用于重写每种类型的节的默认属性。

的格式 `definitions` 为：

`.section_name specifier`

其中 `.section_name` ，是程序图像中某个部分的名称， `specifier` 是以下一个或多个访问修饰符：

|修饰符|说明|
|--------------|-----------------|
|`EXECUTE`|该部分是可执行文件|
|`READ`|允许对数据进行读操作|
|`SHARED`|共享所有加载映像的进程中的节|
|`WRITE`|允许对数据进行写操作|

用空格分隔说明符名称。 例如：

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` 标记部分列表的开头 `definitions` 。 每个 `definition` 必须在单独的行上。 `SECTIONS`关键字可以与第一个行位于同一行上， `definition` 也可以位于前面的行上。 .Def 文件可以包含一个或多个 `SECTIONS` 语句。 `SEGMENTS`关键字支持作为的同义词 `SECTIONS` 。

Visual C++ 支持的旧版本：

```
section [CLASS 'classname'] specifier
```

`CLASS`支持关键字以实现兼容性，但会被忽略。

指定节特性的等效方法是使用 [/SECTION](section-specify-section-attributes.md) 选项。

## <a name="see-also"></a>请参阅

[Module-Definition 语句的规则](rules-for-module-definition-statements.md)
