---
description: 了解详细信息： context_unblock_unbalanced 类
title: context_unblock_unbalanced 类
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: d262ff52a675935f95664d2f7ddd69aa159aa0bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188958"
---
# <a name="context_unblock_unbalanced-class"></a>context_unblock_unbalanced 类

此类描述对 `Context` 对象的 `Block` 和 `Unblock` 方法的调用未恰当配对时引发的异常。

## <a name="syntax"></a>语法

```cpp
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|已重载。 构造 `context_unblock_unbalanced` 对象。|

## <a name="remarks"></a>备注

对对象的 `Block` 和 `Unblock` 方法的调用 `Context` 必须始终正确配对。 并发运行时允许按照任意顺序执行操作。 例如，调用 `Block` 后可以调用 `Unblock`，反之亦然。 例如，如果 `Unblock` 在某一行中对未被阻止的对象执行了两次调用方法，则会引发此异常 `Context` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="context_unblock_unbalanced"></a><a name="ctor"></a> context_unblock_unbalanced

构造 `context_unblock_unbalanced` 对象。

```cpp
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
