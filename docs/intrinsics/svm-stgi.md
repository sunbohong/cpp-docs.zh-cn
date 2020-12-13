---
description: 了解详细信息： __svm_stgi
title: __svm_stgi
ms.date: 09/02/2019
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: 8a6c7c221ed0bbf71a00685e8a0545818dd507a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336855"
---
# <a name="__svm_stgi"></a>__svm_stgi

**Microsoft 专用**

设置全局中断标志。

## <a name="syntax"></a>语法

```C
void __svm_stgi(void);
```

## <a name="remarks"></a>备注

`__svm_stgi` 函数等同于 `STGI` 计算机指令。 全局中断标志确定微处理器是由于事件（如 i/o 完成、硬件温度警报或调试异常）而忽略、推迟还是处理中断。

此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，请在 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 站点搜索 "AMD64 体系结构程序员手册卷2：系统编程"。

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`__svm_stgi`|x86、x64|

**头文件** \<intrin.h>

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[__svm_clgi](../intrinsics/svm-clgi.md)
