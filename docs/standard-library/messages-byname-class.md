---
description: 了解详细信息： messages_byname 类
title: messages_byname 类
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_byname
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
ms.openlocfilehash: 960db9dd411e4ac42f81a0027e91ae1001b7877d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230518"
---
# <a name="messages_byname-class"></a>messages_byname 类

派生类模板描述了一个对象，该对象可充当给定区域设置的消息方面，并支持检索本地化消息。

## <a name="syntax"></a>语法

```cpp
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```

### <a name="parameters"></a>parameters

*_Locname*\
已命名的区域设置。

*_Refs*\
初始引用计数。

## <a name="remarks"></a>备注

其行为由已命名的区域设置 *_Locname* 确定。 每个构造函数都将 () 的[消息](../standard-library/messages-class.md#messages)初始化其基对象 \<CharType> `_Refs` 。

## <a name="requirements"></a>要求

**标头：**\<locale>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
