---
description: 了解更多相关信息： ATL 项目中的 MFC 支持
title: ATL 项目中的 MFC 支持
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 8614bfdd5320e0ecdf34cc96251fa8a20f2dede9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157914"
---
# <a name="mfc-support-in-atl-projects"></a>ATL 项目中的 MFC 支持

如果在 ATL 项目向导中选择 " **支持 mfc** "，则项目会将应用程序声明为 mfc 应用程序对象 (类) 。 项目初始化 MFC 库，并实例化派生自 [CWinApp](../../mfc/reference/cwinapp-class.md)的类 (类 *ProjName*) 。

此选项仅适用于非特性化 ATL DLL 项目。

```
class CProjNameApp : public CWinApp
{
public:

// Overrides
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)
END_MESSAGE_MAP()

CProjNameApp theApp;

BOOL CProjNameApp::InitInstance()
{
    return CWinApp::InitInstance();

}

int CProjNameApp::ExitInstance()
{
    return CWinApp::ExitInstance();

}
```

可以在类视图中查看应用程序对象类及其 `InitInstance` 和 `ExitInstance` 函数。

## <a name="see-also"></a>请参阅

[添加类](../../ide/adding-a-class-visual-cpp.md)<br/>
[创建 ATL 项目](../../atl/reference/creating-an-atl-project.md)<br/>
[默认 ATL 项目配置](../../atl/reference/default-atl-project-configurations.md)
