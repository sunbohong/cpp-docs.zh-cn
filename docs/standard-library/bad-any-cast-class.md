---
description: 了解详细信息： bad_any_cast 类
title: bad_any_cast 类
ms.date: 04/04/2019
f1_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
helpviewer_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
ms.openlocfilehash: 5b38405bf1fc826592995df4037c5853e88ad9eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321622"
---
# <a name="bad_any_cast-class"></a>bad_any_cast 类

引发的对象失败 `any_cast` 。

## <a name="syntax"></a>语法

```cpp
class bad_any_cast
```

### <a name="member-functions"></a>成员函数

|名称|描述|
|-|-|
|[究竟](#what)|返回类型。|

## <a name="what"></a><a name="what"></a> 究竟

返回类型。

```cpp
const char* what() const noexcept override;
```
