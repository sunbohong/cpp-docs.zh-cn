---
description: 了解详细信息： piecewise_contruct_t 结构
title: piecewise_contruct_t 结构
ms.date: 11/04/2016
f1_keywords:
- utility/std::piecewise_contruct_t
helpviewer_keywords:
- piecewise_contruct_t class
- piecewise_contruct_t structure
ms.openlocfilehash: 7fefacff75b47c25cb9ae07cc894498eadb551df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340744"
---
# <a name="piecewise_contruct_t-structure"></a>piecewise_contruct_t 结构

结构 `piecewise_construct_t` 是一个空结构类型，用于保留单独的构造函数和函数重载。 具体而言， `pair` 有一个构造函数 `piecewise_construct_t` 作为第一个参数，后跟两个 `tuple` 自变量。

## <a name="syntax"></a>语法

```cpp
struct piecewise_construct_t { explicit piecewise_construct_t() = default; };

inline constexpr piecewise_construct_t piecewise_construct{};
```
