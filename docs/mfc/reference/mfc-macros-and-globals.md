---
description: 了解更多： MFC 宏和全局
title: MFC 宏和全局函数
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions [MFC]
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
ms.openlocfilehash: 9e3d3acd74d1cf6db5856432cdefd632e36185f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219143"
---
# <a name="mfc-macros-and-globals"></a>MFC 宏和全局函数

Microsoft 基础类库可以分为两个主要部分： (1) MFC 类和 (2) 宏和全局。 如果函数或变量不是类的成员，则它是全局函数或变量。

MFC 库和活动模板库 (ATL) 共享字符串转换宏。 有关详细信息，请参阅 ATL 文档中的 [字符串转换宏](../../atl/reference/string-conversion-macros.md) 。

MFC 宏和全局函数在以下类别中提供功能。

## <a name="general-mfc"></a>一般 MFC

- [数据类型](data-types-mfc.md)

- [MFC 类对象的类型强制转换](type-casting-of-mfc-class-objects.md)

- [运行时对象模型服务](run-time-object-model-services.md)

- [诊断服务](diagnostic-services.md)

- [异常处理](exception-processing.md)

- [CString 格式设置和消息框显示](cstring-formatting-and-message-box-display.md)

- [消息映射](message-map-macros-mfc.md)

- [委托和接口映射](delegate-and-interface-maps.md)

- [模块和 DLL](extension-dll-macros.md)

- [应用程序信息和管理](application-information-and-management.md)

- [标准命令和窗口 ID](standard-command-and-window-ids.md)

- [集合类帮助程序](collection-class-helpers.md)

- [灰色和抖色位图函数](gray-and-dithered-bitmap-functions.md)

- [标准对话框数据交换 (DDX) 例程](standard-dialog-data-exchange-routines.md)

- [标准对话框数据验证 (DDV) 例程](standard-dialog-data-validation-routines.md)

- [AFX 消息](afx-messages.md)

- [工具栏控件样式](toolbar-control-styles.md)

- [CMFCImagePaintArea：： IMAGE_EDIT_MODE 枚举](cmfcimagepaintarea-image-edit-mode-enumeration.md)

## <a name="database"></a>数据库

- [记录字段交换 (RFX) 函数](record-field-exchange-functions.md)和[批量记录字段交换 (MFC ODBC 类的批量 RFX) 函数](record-field-exchange-functions.md)

- 为 MFC DAO 类[ (DFX) 函数记录字段交换](record-field-exchange-functions.md)

- 用于 CRecordView 和 CDaoRecordView (MFC ODBC 和 DAO 类[的对话框数据交换 (DDX) 函数](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md)) 

- [OLE 控件的对话框数据交换 (DDX) 函数](dialog-data-exchange-functions-for-ole-controls.md)

- [用于帮助直接调用开放式数据库连接 (ODBC) API 函数的宏和全局函数](database-macros-and-globals.md)

- [DAO 数据库引擎初始化和终止](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>Internet

- [Internet URL 分析全局函数](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>DHTML/DHTML 事件映射

- [DHTML 对话框数据交换 (DDX) 帮助程序宏](ddx-dhtml-helper-macros.md)

- [DHTML 事件映射](dhtml-event-maps.md)

## <a name="ole"></a>OLE

- [OLE 初始化](ole-initialization.md)

- [应用程序控制](application-control.md)

- [调度映射](dispatch-maps.md)

此外，MFC 还提供了一个名为 [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) 的函数，该函数使使用 MFC 4.0 开发的任何 OLE 容器完全支持嵌入的 ole 控件。

## <a name="ole-controls"></a>OLE 控件

- [变量参数类型常量](variant-parameter-type-constants.md)

- [类型库访问](type-library-access.md)

- [属性页](property-pages-mfc.md)

- [事件映射](event-maps.md)

- [事件接收器映射](event-sink-maps.md)

- [连接映射](connection-maps.md)

- [注册 OLE 控件](registering-ole-controls.md)

- [类工厂和许可](class-factories-and-licensing.md)

- [暂留 OLE 控件](persistence-of-ole-controls.md)

本部分的第一部分简要介绍了上述每个类别，并列出了该类别中的全局和宏，以及功能的简要说明。 下面是 MFC 库中全局函数、全局变量和宏的说明。

> [!NOTE]
> 许多全局函数以前缀 "Afx" 开头，但有些函数（例如，对话框数据交换 (DDX) 函数和许多数据库函数）不遵循此约定。 所有全局变量都以 "afx" 开头作为前缀。 宏不以任何特定的前缀开头，但以大写字母编写。

## <a name="see-also"></a>请参阅

[类概述](../../mfc/class-library-overview.md)
