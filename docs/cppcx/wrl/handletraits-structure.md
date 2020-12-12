---
description: 了解详细信息： HANDLETraits 结构
title: HANDLETraits 结构
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
ms.openlocfilehash: c3eef03c724b1ba868ba67ed251acdb310d8b66f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250018"
---
# <a name="handletraits-structure"></a>HANDLETraits 结构

定义句柄的常见特性。

## <a name="syntax"></a>语法

```cpp
struct HANDLETraits;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称   | 描述
------ | ---------------------
`Type` | 句柄的同义词。

### <a name="public-methods"></a>公共方法

“属性”                                              | 描述
------------------------------------------------- | -----------------------------
[HANDLETraits：： Close](#close)                     | 关闭指定的句柄。
[HANDLETraits：： GetInvalidValue](#getinvalidvalue) | 表示无效的句柄。

## <a name="inheritance-hierarchy"></a>继承层次结构

`HANDLETraits`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装：： HandleTraits

## <a name="handletraitsclose"></a><a name="close"></a> HANDLETraits：： Close

关闭指定的句柄。

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
要关闭的句柄。

### <a name="return-value"></a>返回值

**`true`** 如果 handle *h* 成功关闭，则为;否则为 **`false`** 。

## <a name="handletraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> HANDLETraits：： GetInvalidValue

表示无效的句柄。

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>返回值

始终返回 INVALID_HANDLE_VALUE。  (INVALID_HANDLE_VALUE 由 Windows 定义。 ) 
