---
description: 了解详细信息： ctype_byname 类
title: ctype_byname 类
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: cc5f44e1c544d2088030621b684c9e070175d695
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233131"
---
# <a name="ctype_byname-class"></a>ctype_byname 类

派生类模板描述了一个对象，该对象可充当给定区域设置的 ctype facet，启用字符分类以及区分大小写和本地和区域设置指定字符集之间的字符的转换。

## <a name="syntax"></a>语法

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>备注

其行为由已命名的区域设置 `_Locname` 决定。 每个构造函数都将其基本对象[初始化为](../standard-library/ctype-class.md) \<CharType> ( `_Refs`) 或等效的基类 `ctype<char>` 。

## <a name="requirements"></a>要求

**标头：**\<locale>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
