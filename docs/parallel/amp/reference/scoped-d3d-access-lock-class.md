---
description: 了解详细信息： scoped_d3d_access_lock 类
title: scoped_d3d_access_lock 类
ms.date: 11/04/2016
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
ms.openlocfilehash: 1106673ba9ca095b33660f6a713a40ae8498d384
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329906"
---
# <a name="scoped_d3d_access_lock-class"></a>scoped_d3d_access_lock 类

Accelerator_view 对象上的 D3D 访问锁的 RAII 包装器。

## <a name="syntax"></a>语法

```cpp
class scoped_d3d_access_lock;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[scoped_d3d_access_lock 构造函数](#ctor)|已重载。 构造 `scoped_d3d_access_lock` 对象。 当此对象超出范围时，将释放该锁。|
|[~ scoped_d3d_access_lock 析构函数](#dtor)|释放关联对象上的 D3D 访问锁 `accelerator_view` 。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[operator =](#operator_eq)|获取来自另一个的锁的所有权 `scoped_d3d_access_lock` 。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`scoped_d3d_access_lock`

## <a name="requirements"></a>要求

**标头：** amprt

**命名空间：** concurrency：:d irect3d

## <a name="scoped_d3d_access_lock"></a><a name="ctor"></a> scoped_d3d_access_lock

构造 `scoped_d3d_access_lock` 对象。 当此对象超出范围时，将释放该锁。

```cpp
explicit scoped_d3d_access_lock(// [1] constructor
    accelerator_view& _Av);

explicit scoped_d3d_access_lock(// [2] constructor
    accelerator_view& _Av,
    adopt_d3d_access_lock_t _T);

scoped_d3d_access_lock(// [3] move constructor
    scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>parameters

*_Av*<br/>
`accelerator_view`要采用的锁的。

*_T*<br/>
`adopt_d3d_access_lock_t` 对象。

*_Other*<br/>
`scoped_d3d_access_lock`要从中移动现有锁的对象。

## <a name="construction"></a>建筑

[1] 构造函数获取给定 [accelerator_view](accelerator-view-class.md) 对象上的 D3D 访问锁。 构造块，直到获取锁。

[2] 构造函数采用来自给定 [accelerator_view](accelerator-view-class.md) 对象的 D3D 访问锁。

[3] 移动构造函数从另一个对象获取现有的 D3D 访问锁 `scoped_d3d_access_lock` 。 构造不会阻止。

## <a name="scoped_d3d_access_lock"></a><a name="dtor"></a> ~ scoped_d3d_access_lock

释放关联对象上的 D3D 访问锁 `accelerator_view` 。

```cpp
~scoped_d3d_access_lock();
```

## <a name="operator"></a><a name="operator_eq"></a> operator =

从另一个对象取得 D3D 访问锁的所有权 `scoped_d3d_access_lock` ，释放以前的锁。

```cpp
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>parameters

*_Other*<br/>
要从中移动 D3D 访问锁定的 accelerator_view。

### <a name="return-value"></a>返回值

对此的引用 `scoped_accelerator_view_lock` 。

## <a name="see-also"></a>请参阅

[Concurrency::direct3d 命名空间](concurrency-direct3d-namespace.md)
