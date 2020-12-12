---
description: 了解详细信息： codecvt_utf8_utf16
title: codecvt_utf8_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::cvt_utf8_utf16
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
ms.openlocfilehash: e80cdaa01ef77b9ce28a773eb4e05056220718a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325070"
---
# <a name="codecvt_utf8_utf16"></a>codecvt_utf8_utf16

表示在编码为 UTF-16 的宽字符和编码为 UTF-8 的字节流之间转换的 [区域设置](../standard-library/locale-class.md) facet。

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>parameters

*Elem*\
宽字符元素类型。

*Maxcode*\
区域设置 facet 的最大字符数。

*众*\
配置区域设置 facet 的信息。

## <a name="remarks"></a>备注

字节流可以写入二进制文件或文本文件。

## <a name="requirements"></a>要求

标头：\<codecvt>

命名空间: std
