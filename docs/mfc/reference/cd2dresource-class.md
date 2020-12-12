---
description: 了解详细信息： CD2DResource 类
title: CD2DResource 类
ms.date: 03/27/2019
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
ms.openlocfilehash: a110732a7e2bde5ab2fb3b6025acf98d6a3278c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118727"
---
# <a name="cd2dresource-class"></a>CD2DResource 类

一个抽象类，它提供用于创建和管理 D2D 资源（如画笔、层和文本）的接口。

## <a name="syntax"></a>语法

```
class CD2DResource : public CObject;
```

## <a name="members"></a>成员

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[CD2DResource：： CD2DResource](#cd2dresource)|构造 CD2DResource 对象。|
|[CD2DResource：： ~ CD2DResource](#_dtorcd2dresource)|析构函数。 当 D2D 资源对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DResource：： Create](#create)|创建 CD2DResource。|
|[CD2DResource：:D estroy](#destroy)|销毁 CD2DResource 对象。|
|[CD2DResource：： IsValid](#isvalid)|检查资源有效性|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CD2DResource：： IsAutoDestroy](#isautodestroy)|检查自动销毁标志。|
|[CD2DResource：：重新创建](#recreate)|重新创建 CD2DResource。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DResource：： m_bIsAutoDestroy](#m_bisautodestroy)|资源将由所有者 (CRenderTarget) 销毁|
|[CD2DResource：： m_pParentTarget](#m_pparenttarget)|指向父 CRenderTarget) 的指针|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a> CD2DResource：： ~ CD2DResource

析构函数。 当 D2D 资源对象被销毁时调用。

```
virtual ~CD2DResource();
```

## <a name="cd2dresourcecd2dresource"></a><a name="cd2dresource"></a> CD2DResource：： CD2DResource

构造 CD2DResource 对象。

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dresourcecreate"></a><a name="create"></a> CD2DResource：： Create

创建 CD2DResource。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
指向呈现器目标的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dresourcedestroy"></a><a name="destroy"></a> CD2DResource：:D estroy

销毁 CD2DResource 对象。

```
virtual void Destroy() = 0;
```

## <a name="cd2dresourceisautodestroy"></a><a name="isautodestroy"></a> CD2DResource：： IsAutoDestroy

检查自动销毁标志。

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>返回值

如果对象将被其所有者销毁，则为 TRUE;否则为 FALSE。

## <a name="cd2dresourceisvalid"></a><a name="isvalid"></a> CD2DResource：： IsValid

检查资源有效性

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>返回值

如果资源有效，则为 TRUE;否则为 FALSE。

## <a name="cd2dresourcem_bisautodestroy"></a><a name="m_bisautodestroy"></a> CD2DResource：： m_bIsAutoDestroy

资源将由所有者 (CRenderTarget) 销毁

```
BOOL m_bIsAutoDestroy;
```

## <a name="cd2dresourcem_pparenttarget"></a><a name="m_pparenttarget"></a> CD2DResource：： m_pParentTarget

指向父 CRenderTarget) 的指针

```
CRenderTarget* m_pParentTarget;
```

## <a name="cd2dresourcerecreate"></a><a name="recreate"></a> CD2DResource：：重新创建

重新创建 CD2DResource。

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
指向呈现器目标的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
