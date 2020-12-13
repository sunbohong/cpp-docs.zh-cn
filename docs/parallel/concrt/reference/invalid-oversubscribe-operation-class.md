---
description: 了解详细信息： invalid_oversubscribe_operation 类
title: invalid_oversubscribe_operation 类
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 435e3ce0eba29188711c51aa9253060fc08ac62c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334524"
---
# <a name="invalid_oversubscribe_operation-class"></a>invalid_oversubscribe_operation 类

此类描述在以下情况下引发的异常：在 `Context::Oversubscribe` `_BeginOversubscription` 参数设置为的 **`false`** 情况下调用方法，且 `Context::Oversubscribe` `_BeginOversubscription` 参数设置为 **`true`** 。

## <a name="syntax"></a>语法

```cpp
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|已重载。 构造 `invalid_oversubscribe_operation` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="invalid_oversubscribe_operation"></a><a name="ctor"></a> invalid_oversubscribe_operation

构造 `invalid_oversubscribe_operation` 对象。

```cpp
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
