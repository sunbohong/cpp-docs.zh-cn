---
description: 了解详细信息： _stat 结构 st_mode 字段常量
title: _stat 结构 st_mode 字段常量
ms.date: 11/04/2016
f1_keywords:
- S_IFCHR
- S_IFDIR
- _S_IWRITE
- S_IFMT
- _S_IFDIR
- _S_IREAD
- S_IEXEC
- _S_IEXEC
- _S_IFMT
- S_IWRITE
- S_IFREG
- S_IREAD
- _S_IFCHR
- _S_IFREG
helpviewer_keywords:
- S_IFDIR constant
- stat structure
- S_IWRITE constant
- S_IEXEC constant
- _S_IFREG constant
- S_IREAD constant
- stat structure, constants
- _S_IFMT constant
- st_mode field constants
- S_IFMT constant
- _S_IEXEC constant
- _S_IWRITE constant
- _S_IFDIR constant
- S_IFREG constant
- S_IFCHR constant
- _S_IREAD constant
- _S_IFCHR constant
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
ms.openlocfilehash: bd304119c705196981342caf5a257cc113fed923
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235731"
---
# <a name="_stat-structure-st_mode-field-constants"></a>_stat 结构 st_mode 字段常量

## <a name="syntax"></a>语法

```
#include <sys/stat.h>
```

## <a name="remarks"></a>备注

这些常量用于指示 [_stat 结构](../c-runtime-library/standard-types.md)的 st_mode 字段中的文件类型。

下面描述了位掩码常量：

|返回的常量|含义|
|--------------|-------------|
|`_S_IFMT`|文件类型掩码|
|`_S_IFDIR`|Directory|
|`_S_IFCHR`|特殊字符（指示设备，如果已设置）|
|`_S_IFREG`|常规|
|`_S_IREAD`|读取权限，所有者|
|`_S_IWRITE`|写入权限，所有者|
|`_S_IEXEC`|执行/搜索权限，所有者|

## <a name="see-also"></a>请参阅

[_stat、_wstat 函数](../c-runtime-library/reference/stat-functions.md)<br/>
[_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[标准类型](../c-runtime-library/standard-types.md)<br/>
[全局常量](../c-runtime-library/global-constants.md)
