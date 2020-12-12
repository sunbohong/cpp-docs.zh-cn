---
description: 了解详细信息： time_put_byname 类
title: time_put_byname 类
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: b519b28b7af8f5b54f9150d1d84f68cd6695bc49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167248"
---
# <a name="time_put_byname-class"></a>time_put_byname 类

派生类模板描述一个对象，该对象可充当类型的区域设置 facet `time_put` \< CharType, OutputIterator > 。

## <a name="syntax"></a>语法

```cpp
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```

### <a name="parameters"></a>parameters

*_Locname*\
区域设置名称。

*_Refs*\
初始引用计数。

## <a name="remarks"></a>备注

其行为由已 [命名](../standard-library/locale-class.md#name) 的区域设置 *_Locname* 确定。 每个构造函数都用[time_put](../standard-library/time-put-class.md#time_put) \<CharType, OutputIterator> () 初始化其基对象 `_Refs` 。

## <a name="requirements"></a>要求

**标头：**\<locale>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
