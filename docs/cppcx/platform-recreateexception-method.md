---
description: 了解详细信息： Platform：： ReCreateException 方法
title: Platform：： RecreateException 方法
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 273f60055e4cf5a940558ba5dcaa4aa6a7c70bca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308050"
---
# <a name="platformrecreateexception-method"></a>Platform::ReCreateException 方法

此方法仅供内部使用，不用于用户代码。 请改用 Exception::CreateException 方法。

## <a name="syntax"></a>语法

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>parameters

*小时*

### <a name="property-valuereturn-value"></a>属性值/返回值

基于指定的 HRESULT 返回新的 Platform::Exception^。
