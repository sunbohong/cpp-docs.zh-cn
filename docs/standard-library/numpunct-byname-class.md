---
description: 了解详细信息： numpunct_byname 类
title: numpunct_byname 类
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: e4e6352f9f65b2a726acf3f8f5f8ede9bffe54f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338034"
---
# <a name="numpunct_byname-class"></a>numpunct_byname 类

派生类模板描述了一个对象，该对象可充当 `numpunct` 给定区域设置的 facet，启用数值和布尔表达式的格式和标点。

## <a name="syntax"></a>语法

```cpp
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

};
```

## <a name="remarks"></a>备注

其行为由[已命名的](../standard-library/locale-class.md#name)区域设置 `_Locname` 决定。 构造函数用[numpunct](../standard-library/numpunct-class.md#numpunct) () 初始化其基对象 \<CharType> `_Refs` 。

## <a name="requirements"></a>要求

**标头：**\<locale>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
