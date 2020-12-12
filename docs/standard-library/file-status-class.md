---
description: 了解详细信息： file_status 类
title: file_status 类
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.openlocfilehash: 8bc789d97f9b90b18214407fadab19e9644012a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324352"
---
# <a name="file_status-class"></a>file_status 类

包装 [file_type](../standard-library/filesystem-enumerations.md#file_type) 和文件 [perms](../standard-library/filesystem-enumerations.md#perms)。

## <a name="syntax"></a>语法

```cpp
class file_status;
```

### <a name="constructors"></a>构造函数

|构造函数|说明|
|-|-|
|[file_status](#file_status)|构造 [file_type](../standard-library/filesystem-enumerations.md#file_type) 和文件 [perms](../standard-library/filesystem-enumerations.md#perms)的包装。|

### <a name="member-functions"></a>成员函数

|成员函数|说明|
|-|-|
|type|获取或设置 `file_type`。|
|[权限](#permissions)|获取或设置文件权限。|

### <a name="operators"></a>运算符

|运算符|描述|
|-|-|
|[operator =](#op_as)|默认成员赋值运算符的行为符合预期。|

## <a name="requirements"></a>要求

**标头：**\<filesystem>

**命名空间：** std：：实验：： filesystem，std：：实验：： filesystem

## <a name="file_statusfile_status"></a><a name="file_status"></a> file_status：： file_status

构造 [file_type](../standard-library/filesystem-enumerations.md#file_type) 和文件 [perms](../standard-library/filesystem-enumerations.md#perms)的包装。

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

### <a name="parameters"></a>parameters

*ftype*\
指定 `file_type` ，则默认为 `file_type::none` 。

*掩盖*\
指定的文件 `perms` ，默认为 `perms::unknown` 。

*file_status*\
存储的对象。

## <a name="file_statusoperator"></a><a name="op_as"></a> file_status：： operator =

默认成员赋值运算符的行为符合预期。

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

### <a name="parameters"></a>parameters

*file_status*\
要[](../standard-library/file-status-class.md)复制到中的 file_status `file_status` 。

## <a name="type"></a><a name="type"></a> 类型

获取或设置 `file_type`。

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

### <a name="parameters"></a>parameters

*ftype*\
已指定 `file_type`。

## <a name="permissions"></a><a name="permissions"></a> 访问

获取或设置文件权限。

使用 setter 创建文件 `readonly` 或删除该 `readonly` 属性。

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

### <a name="parameters"></a>parameters

*掩盖*\
已指定 `perms`。

## <a name="see-also"></a>请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[path 类](../standard-library/path-class.md)\
[\<filesystem>](../standard-library/filesystem.md)
