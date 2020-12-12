---
description: 了解详细信息： Container Class：： erase
title: Container Class::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 7e9d7747237a38c42bfb7a39c5d5e66cc8a44608
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324862"
---
# <a name="container-classerase"></a>Container Class::erase

> [!NOTE]
> 本主题在 Microsoft c + + 文档中作为 c + + 标准库中使用的容器的非功能性示例。 有关详细信息，请参阅 [C++ 标准库容器](../standard-library/stl-containers.md)。

删除元素。

## <a name="syntax"></a>语法

```cpp
iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>备注

第一个成员函数通过 *_Where* 删除受控序列的元素。 第二个成员函数将移除范围 [`first`、`last`) 中的受控序列的元素。 两者都返回一个迭代器，指定已移除的任何元素之外保留的第一个元素或 [end](../standard-library/container-class-end.md)（若此类元素不存在）。

成员函数仅在复制操作引发异常时才引发异常。

## <a name="see-also"></a>请参阅

[示例容器类](../standard-library/sample-container-class.md)
