---
description: 了解详细信息： AFX_EXTENSION_MODULE 结构
title: AFX_EXTENSION_MODULE 结构
ms.date: 11/04/2016
f1_keywords:
- AFX_EXTENSION_MODULE
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
ms.openlocfilehash: d3a5abd449f13a06aa5d7388b2dd2926a6011973
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248224"
---
# <a name="afx_extension_module-structure"></a>AFX_EXTENSION_MODULE 结构

在 `AFX_EXTENSION_MODULE` mfc 扩展 dll 的初始化过程中，用于保存 mfc 扩展 dll 模块的状态。

## <a name="syntax"></a>语法

```
struct AFX_EXTENSION_MODULE
{
    BOOL bInitialized;
    HMODULE hModule;
    HMODULE hResource;
    CRuntimeClass* pFirstSharedClass;
    COleObjectFactory* pFirstSharedFactory;
};
```

#### <a name="parameters"></a>parameters

*bInitialized*<br/>
如果 DLL 模块已用初始化，则为 TRUE `AfxInitExtensionModule` 。

*hModule*<br/>
指定 DLL 模块的句柄。

*hResource*<br/>
指定 DLL 自定义资源模块的句柄。

*pFirstSharedClass*<br/>
指向 (结构的信息的指针 `CRuntimeClass`) DLL 模块的第一个运行时类。 用于提供运行时类列表的开头。

*pFirstSharedFactory*<br/>
一个指针，指向 DLL 模块的第一个对象工厂 (`COleObjectFactory` 对象) 。 用于提供类工厂列表的开头。

## <a name="remarks"></a>备注

MFC 扩展 Dll 需要在其函数中执行两项操作 `DllMain` ：

- 调用 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) 并检查返回值。

- `CDynLinkLibrary`如果 DLL 将导出[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)对象或有其自己的自定义资源，请创建对象。

`AFX_EXTENSION_MODULE`结构用于保存 mfc 扩展 dll 模块状态的副本，包括已由 MFC 扩展 dll 初始化为输入之前执行的常规静态对象构造的一部分的运行时类对象的副本 `DllMain` 。 例如：

[!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]

可以将存储在结构中的模块信息 `AFX_EXTENSION_MODULE` 复制到 `CDynLinkLibrary` 对象中。 例如：

[!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]

## <a name="requirements"></a>要求

**标头：** afx

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)<br/>
[AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)
