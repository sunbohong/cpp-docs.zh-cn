---
description: 了解详细信息： CD2DMesh 类
title: CD2DMesh 类
ms.date: 11/04/2016
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
ms.openlocfilehash: fbdb941d04b87df5c136f1925445564caab63443
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193365"
---
# <a name="cd2dmesh-class"></a>CD2DMesh 类

ID2D1Mesh 的包装器。

## <a name="syntax"></a>语法

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DMesh：： CD2DMesh](#cd2dmesh)|构造 CD2DMesh 对象。|
|[CD2DMesh：： ~ CD2DMesh](#_dtorcd2dmesh)|析构函数。 当 D2D 网格对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DMesh：： Attach](#attach)|将现有资源接口附加到对象|
|[CD2DMesh：： Create](#create)|创建 CD2DMesh。  (重写 [CD2DResource：： Create](../../mfc/reference/cd2dresource-class.md#create). ) |
|[CD2DMesh：:D estroy](#destroy)|销毁 CD2DMesh 对象。  (重写 [CD2DResource：:D estroy](../../mfc/reference/cd2dresource-class.md#destroy)。 ) |
|[CD2DMesh：:D etach](#detach)|从对象分离资源接口|
|[CD2DMesh：： Get](#get)|返回 ID2D1Mesh 接口|
|[CD2DMesh：： IsValid](#isvalid)|检查资源有效性 (重写 [CD2DResource：： IsValid](../../mfc/reference/cd2dresource-class.md#isvalid). ) |
|[CD2DMesh：： Open](#open)|打开用于填充的网格。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DMesh：： operator ID2D1Mesh *](#operator_id2d1mesh_star)|返回 ID2D1Mesh 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DMesh：： m_pMesh](#m_pmesh)|指向 ID2D1Mesh 的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dmeshcd2dmesh"></a><a name="_dtorcd2dmesh"></a> CD2DMesh：： ~ CD2DMesh

析构函数。 当 D2D 网格对象被销毁时调用。

```
virtual ~CD2DMesh();
```

## <a name="cd2dmeshattach"></a><a name="attach"></a> CD2DMesh：： Attach

将现有资源接口附加到对象

```cpp
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>parameters

*pResource*<br/>
现有的资源接口。 不能为 NULL

## <a name="cd2dmeshcd2dmesh"></a><a name="cd2dmesh"></a> CD2DMesh：： CD2DMesh

构造 CD2DMesh 对象。

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dmeshcreate"></a><a name="create"></a> CD2DMesh：： Create

创建 CD2DMesh。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
指向呈现器目标的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dmeshdestroy"></a><a name="destroy"></a> CD2DMesh：:D estroy

销毁 CD2DMesh 对象。

```
virtual void Destroy();
```

## <a name="cd2dmeshdetach"></a><a name="detach"></a> CD2DMesh：:D etach

从对象分离资源接口

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>返回值

指向已分离资源接口的指针。

## <a name="cd2dmeshget"></a><a name="get"></a> CD2DMesh：： Get

返回 ID2D1Mesh 接口

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>返回值

指向 ID2D1Mesh 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dmeshisvalid"></a><a name="isvalid"></a> CD2DMesh：： IsValid

检查资源有效性

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>返回值

如果资源有效，则为 TRUE;否则为 FALSE。

## <a name="cd2dmeshm_pmesh"></a><a name="m_pmesh"></a> CD2DMesh：： m_pMesh

指向 ID2D1Mesh 的指针。

```
ID2D1Mesh* m_pMesh;
```

## <a name="cd2dmeshopen"></a><a name="open"></a> CD2DMesh：： Open

打开用于填充的网格。

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>返回值

指向用于填充网格的 ID2D1TessellationSink 的指针。

## <a name="cd2dmeshoperator-id2d1mesh"></a><a name="operator_id2d1mesh_star"></a> CD2DMesh：： operator ID2D1Mesh *

返回 ID2D1Mesh 接口

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>返回值

指向 ID2D1Mesh 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
