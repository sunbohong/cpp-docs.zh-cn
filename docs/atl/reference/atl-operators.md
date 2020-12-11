---
description: 了解详细信息： ATL 运算符
title: ATL 运算符
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 8c336732aeee9146b89e300580c0fbee506ec343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158681"
---
# <a name="atl-operators"></a>ATL 运算符

本部分包含 ATL 全局运算符的参考主题。

|运算符|描述|
|--------------|-----------------|
|[operator = =](#operator_eq_eq)|比较两个 `CSid` 对象或 `SID` 结构是否相等。|
|[operator！ =](#operator_neq)|比较两个 `CSid` 对象或 `SID` 结构是否不相等。|
|[运算符 <](#operator_lt)|测试 `CSid` 运算符左侧的对象或 `SID` 结构是否小于 `CSid` `SID` c + + 标准库兼容性) 右侧 (的对象或结构。|
|[运算符 >](#operator_gt)|测试 `CSid` 运算符左侧的对象或 `SID` 结构是否大于 `CSid` `SID` c + + 标准库兼容性) 右侧 (的对象或结构。|
|[运算符 <=](#operator_lt__eq)|测试 `CSid` 运算符左侧的对象或 `SID` 结构是否小于或等于 `CSid` `SID` c + + 标准库兼容性) 右侧 (的对象或结构。|
|[运算符 >=](#operator_gt__eq)|测试 `CSid` 运算符左侧的对象或 `SID` 结构是否大于或等于 `CSid` `SID` c + + 标准库兼容性) 右侧 (的对象或结构。|

## <a name="requirements"></a>要求

**标头：** atlsecurity.h。

## <a name="operator-"></a><a name="operator_eq_eq"></a> operator = =

比较 `CSid` 对象或 `SID` (安全标识符) 结构是否相等。

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>parameters

*lhs*<br/>
要比较的第一个 `CSid` 对象或 `SID` 结构。

*rhs*<br/>
要比较的第二个 `CSid` 对象或 `SID` 结构。

### <a name="return-value"></a>返回值

如果对象相等，则返回 TRUE，否则返回 FALSE。

## <a name="operator-"></a><a name="operator_neq"></a> operator！ =

比较 `CSid` 对象或 `SID` (安全标识符) 结构是否不相等。

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>parameters

*lhs*<br/>
要比较的第一个 `CSid` 对象或 `SID` 结构。

*rhs*<br/>
要比较的第二个 `CSid` 对象或 `SID` 结构。

### <a name="return-value"></a>返回值

如果对象不相等，则返回 TRUE，否则返回 FALSE。

## <a name="operator-"></a><a name="operator_lt"></a> 运算符 <

测试 `CSid` 运算符左侧的对象或 `SID` 结构是否小于 `CSid` `SID` c + + 标准库兼容性) 右侧 (的对象或结构。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>parameters

*lhs*<br/>
要比较的第一个 `CSid` 对象或 `SID` 结构。

*rhs*<br/>
要比较的第二个 `CSid` 对象或 `SID` 结构。

### <a name="return-value"></a>返回值

如果 *lhs* 对象的地址小于 *rhs* 对象的地址，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

此运算符作用于 `CSid` 对象或结构的地址 `SID` ，并实现以提供与 c + + 标准库集合类的兼容性。

## <a name="operator-"></a><a name="operator_gt"></a> 运算符 >

测试 `CSid` 运算符左侧的对象或 `SID` 结构是否大于 `CSid` `SID` c + + 标准库兼容性) 右侧 (的对象或结构。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>parameters

*lhs*<br/>
要比较的第一个 `CSid` 对象或 `SID` 结构。

*rhs*<br/>
要比较的第二个 `CSid` 对象或 `SID` 结构。

### <a name="return-value"></a>返回值

如果 *lhs* 的地址大于 *rhs* 的地址，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

此运算符作用于 `CSid` 对象或结构的地址 `SID` ，并实现以提供与 c + + 标准库集合类的兼容性。

## <a name="operator-"></a><a name="operator_lt__eq"></a> 运算符 <=

测试 `CSid` 运算符左侧的对象或 `SID` 结构是否小于或等于 `CSid` `SID` c + + 标准库兼容性) 右侧 (的对象或结构。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>parameters

*lhs*<br/>
要比较的第一个 `CSid` 对象或 `SID` 结构。

*rhs*<br/>
要比较的第二个 `CSid` 对象或 `SID` 结构。

### <a name="return-value"></a>返回值

如果 *lhs* 的地址小于或等于 *rhs* 的地址，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

此运算符作用于 `CSid` 对象或结构的地址 `SID` ，并实现以提供与 c + + 标准库集合类的兼容性。

## <a name="operator-"></a><a name="operator_gt__eq"></a> 运算符 >=

测试 `CSid` 运算符左侧的对象或 `SID` 结构是否大于或等于 `CSid` `SID` c + + 标准库兼容性) 右侧 (的对象或结构。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>parameters

*lhs*<br/>
要比较的第一个 `CSid` 对象或 `SID` 结构。

*rhs*<br/>
要比较的第二个 `CSid` 对象或 `SID` 结构。

### <a name="return-value"></a>返回值

如果 *lhs* 的地址大于或等于 *rhs* 的地址，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

此运算符作用于 `CSid` 对象或结构的地址 `SID` ，并实现以提供与 c + + 标准库集合类的兼容性。
