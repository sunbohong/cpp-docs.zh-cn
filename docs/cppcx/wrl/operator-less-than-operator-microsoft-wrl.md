---
description: '了解有关以下方面的详细信息：运算符 &lt; 运算符 (Microsoft：： WRL) '
title: '运算符 &lt; 运算符 (Microsoft：： WRL) '
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 1edbb8218ef07355040bd05ab99db8f97be1cb59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330770"
---
# <a name="operatorlt-operator-microsoftwrl"></a>运算符 &lt; 运算符 (Microsoft：： WRL) 

确定一个对象的地址是否小于另一个对象的地址。

## <a name="syntax"></a>语法

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>parameters

*的*<br/>
左对象。

*b*<br/>
右对象。

## <a name="return-value"></a>返回值

**`true`** 如果 *的地址* 小于 *b* 的地址，则为;否则为 **`false`** 。

## <a name="requirements"></a>要求

**标头：** client.h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
