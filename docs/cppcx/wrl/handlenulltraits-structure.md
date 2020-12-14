---
description: 了解详细信息： HANDLENullTraits 结构
title: HANDLENullTraits 结构
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
ms.openlocfilehash: 14d5eaab36be24b5450b66c35c9cf5cbba39ea4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229244"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits 结构

定义未初始化的句柄的常见特性。

## <a name="syntax"></a>语法

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称   | 描述
------ | ---------------------
`Type` | 句柄的同义词。

### <a name="public-methods"></a>公共方法

“属性”                                                  | 描述
----------------------------------------------------- | -----------------------------
[HANDLENullTraits：： Close](#close)                     | 关闭指定的句柄。
[HANDLENullTraits：： GetInvalidValue](#getinvalidvalue) | 表示无效的句柄。

## <a name="inheritance-hierarchy"></a>继承层次结构

`HANDLENullTraits`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装：： HandleTraits

## <a name="handlenulltraitsclose"></a><a name="close"></a> HANDLENullTraits：： Close

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

## <a name="handlenulltraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> HANDLENullTraits：： GetInvalidValue

表示无效的句柄。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>返回值

始终返回 **`nullptr`** 。
