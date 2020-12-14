---
description: 了解详细信息： collate_byname 类
title: collate_byname 类
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate_byname
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
ms.openlocfilehash: 8e5ee60a2415fe6fede6db387c774151b97396dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233950"
---
# <a name="collate_byname-class"></a>collate_byname 类

一个派生类模板，用于描述一个对象，该对象可充当给定区域设置的排序规则 facet，从而能够检索特定于涉及字符串排序约定的区域性区域的信息。

## <a name="syntax"></a>语法

```cpp
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```

### <a name="parameters"></a>parameters

*_Locname*\
已命名的区域设置。

*_Refs*\
初始引用计数。

## <a name="remarks"></a>备注

类模板描述一个对象，该对象可充当类型为[collate](../standard-library/collate-class.md#collate)的[区域设置 facet](../standard-library/locale-class.md#facet_class) \<CharType> 。 其行为由已 [命名](../standard-library/locale-class.md#name) 的区域设置 *_Locname* 确定。 每个构造函数都通过[collate](../standard-library/collate-class.md#collate) \<CharType> () 初始化其基对象 `_Refs` 。

## <a name="requirements"></a>要求

**标头：**\<locale>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
