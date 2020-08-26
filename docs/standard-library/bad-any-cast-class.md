---
title: bad_any_cast 类
ms.date: 04/04/2019
f1_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
helpviewer_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
ms.openlocfilehash: b47ca4f615c6f317f17ce64e8388ae5d698185ea
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844582"
---
# <a name="bad_any_cast-class"></a>bad_any_cast 类

引发的对象失败 `any_cast` 。

## <a name="syntax"></a>语法

```cpp
class bad_any_cast
```

### <a name="member-functions"></a>成员函数

|名称|说明|
|-|-|
|[究竟](#what)|返回类型。|

## <a name="what"></a><a name="what"></a> 究竟

返回类型。

```cpp
const char* what() const noexcept override;
```
