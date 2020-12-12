---
description: 了解详细信息： progress_reporter 类
title: progress_reporter 类
ms.date: 11/04/2016
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
ms.openlocfilehash: 40ae3dba0c804381478d8c32da4425b20a9825d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169354"
---
# <a name="progress_reporter-class"></a>progress_reporter 类

进度报告器类允许报告特定类型的进度通知。 每个 progress_reporter 对象都是绑定到特定异步动作或操作的。

## <a name="syntax"></a>语法

```cpp
template<typename _ProgressType>
class progress_reporter;
```

### <a name="parameters"></a>parameters

*_ProgressType*<br/>
通过进度报告器报告的每个进度通知的负载类型。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[report (报表)](#report)|向进度报告器绑定到的异步动作或操作发送进度报告。|

## <a name="remarks"></a>备注

此类型仅可用于 Windows 运行时应用。

## <a name="inheritance-hierarchy"></a>继承层次结构

`progress_reporter`

## <a name="requirements"></a>要求

**标头：** ppltasks。h

**命名空间：** 并发

## <a name="progress_reporter"></a><a name="ctor"></a> progress_reporter

```cpp
progress_reporter();
```

## <a name="report"></a><a name="report"></a> 报表

向进度报告器绑定到的异步动作或操作发送进度报告。

```cpp
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>parameters

*初始值*<br/>
要通过进度通知报告的有效负载。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
