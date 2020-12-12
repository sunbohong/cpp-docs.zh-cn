---
description: 了解详细信息： TN026： DDX 和 DDV 例程
title: TN026：DDX 和 DDV 例程
ms.date: 06/28/2018
f1_keywords:
- DDX
- DDV
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
ms.openlocfilehash: 1e5c8d3679b7e91ad7f356c1e6f6badc61cdd46f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215698"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026：DDX 和 DDV 例程

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

此注释描述了对话框数据交换 (DDX) 和对话框数据验证 (DDV) 体系结构。 还介绍了如何编写 DDX_ 或 DDV_ 过程，以及如何扩展 ClassWizard 以使用您的例程。

## <a name="overview-of-dialog-data-exchange"></a>对话框数据交换概述

所有对话框数据函数都是用 c + + 代码完成的。 没有特殊的资源或神奇的宏。 机制的核心是一种虚拟函数，它在执行对话框数据交换和验证的每个对话框类中被重写。 它始终按以下形式找到：

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

特殊格式 AFX 注释允许 ClassWizard 查找和编辑此函数中的代码。 与 ClassWizard 不兼容的代码应置于特殊格式注释之外。

在上面的示例中，的 \<data_exchange_function_call> 格式为：

```cpp
DDX_Custom(pDX, nIDC, field);
```

和 \<data_validation_function_call> 是可选的，其形式如下：

```cpp
DDV_Custom(pDX, field, ...);
```

每个函数中可能包含多个 DDX_/DDV_ 对 `DoDataExchange` 。

有关随 MFC 一起提供的所有对话框数据交换例程和对话框数据验证例程的列表，请参阅 "afxdd_ .h"。

对话框数据就是：类中的成员数据 `CMyDialog` 。 它不会存储在结构中或类似的任何内容中。

## <a name="notes"></a>注释

尽管我们称之为 "对话框数据"，但所有功能都可用于派生自的任何类 `CWnd` ，但并不局限于只是对话框。

数据的初始值在标准 c + + 构造函数中设置，通常在带有 and 注释的块中 `//{{AFX_DATA_INIT` `//}}AFX_DATA_INIT` 。

`CWnd::UpdateData` 在调用时执行初始化和错误处理的操作 `DoDataExchange` 。

你可以随时调用 `CWnd::UpdateData` 来执行数据交换和验证。 默认情况下 `UpdateData` (TRUE) 在默认 `CDialog::OnOK` 处理程序中调用， (为) FALSE，则默认情况下将 `UpdateData` 调用 `CDialog::OnInitDialog` 。

DDV_ 例程应紧跟在该 *字段* 的 DDX_ 例程之后。

## <a name="how-does-it-work"></a>工作原理

您无需了解以下各项即可使用对话框数据。 但是，了解这种情况如何在幕后工作会有助于您编写自己的 exchange 或验证过程。

`DoDataExchange`成员函数非常类似于 `Serialize` 成员函数-它负责获取或设置外部窗体中的数据 (在此示例中，此示例中的控件) 类中的成员数据。 *PDX* 参数是用于进行数据交换的上下文，类似于的 `CArchive` 参数 `CObject::Serialize` 。 *PDX* (某个 `CDataExchange` 对象) 具有方向标志，这一点非常类似于 `CArchive` 具有方向标志：

- 如果 `!m_bSaveAndValidate` 为，则将数据状态加载到控件中。

- 如果为 `m_bSaveAndValidate` ，则从控件设置数据状态。

仅当设置了时才会进行验证 `m_bSaveAndValidate` 。 的值由的 `m_bSaveAndValidate` 布尔参数确定 `CWnd::UpdateData` 。

还有其他三个有趣的 `CDataExchange` 成员：

- `m_pDlgWnd`：窗口 (通常是包含控件) 的对话框。 这是为了防止 DDX_ 的调用方和 DDV_ 全局函数必须将 "this" 传递到每个 DDX/DDV 例程。

- `PrepareCtrl`和 `PrepareEditCtrl` ：准备用于数据交换的对话框控件。 如果验证失败，则存储控件的用于设置焦点的句柄。 `PrepareCtrl` 用于非编辑控件，并 `PrepareEditCtrl` 用于编辑控件。

- `Fail`：在弹出消息框后调用，以向用户发出输入错误警报。 此例程会将焦点还原到最后一个控件 (最后一次调用 `PrepareCtrl` 或 `PrepareEditCtrl`) 并引发异常。 可以从 DDX_ 和 DDV_ 例程调用此成员函数。

## <a name="user-extensions"></a>用户扩展

可以通过多种方式来扩展默认的 DDX/DDV 机制。 方法：

- 添加新的数据类型。

    ```cpp
    CTime
    ```

- DDX_) 中添加新的 exchange 过程 (。

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

-  (DDV_) 中添加新的验证过程。

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- 将任意表达式传递到验证过程。

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > 此类任意表达式不能通过 ClassWizard 编辑，因此应移到特殊格式注释之外 (//{{AFX_DATA_MAP (CMyClass) # A3。

让 `DoDialogExchange` 成员函数包含带有混合交换和验证函数调用的条件或任何其他有效 c + + 语句。

```cpp
//{{AFX_DATA_MAP(CMyClass)
DDX_Check(pDX, IDC_SEX, m_bFemale);
DDX_Text(pDX, IDC_EDIT1, m_age);
//}}AFX_DATA_MAP
if (m_bFemale)
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);
else
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);
```

> [!NOTE]
> 如上所示，ClassWizard 不能编辑此类代码，只能在特殊格式注释之外使用。

## <a name="classwizard-support"></a>ClassWizard 支持

ClassWizard 通过使你能够将自己的 DDX_ 和 DDV_ 例程集成到 ClassWizard 用户界面，来支持 DDX/DDV 自定义的子集。 如果你计划在项目中或在多个项目中重复使用特定的 DDX 和 DDV 例程，则这样做只是成本优势。

为此，请在 CLW (早期版本的 Visual C++ 将此信息存储在 APSTUDIO.INI) 或项目的中。CLW 文件。 可以在项目的 [常规信息] 部分输入特殊条目。CLW 文件或 ExtraDDX 中的 CLW 文件的 [] 部分中的文件。 如果它尚不存在，可能需要创建 CLW 文件。 如果计划仅在特定项目中使用自定义 DDX_/DDV_ 例程，请将这些项添加到项目的 [常规信息] 部分。CLW 文件。 如果计划在多个项目上使用这些例程，请将这些项添加到 CLW 的 [ExtraDDX] 部分。

这些特殊条目的常规格式为：

> ExtraDDXCount =*n*

其中， *n* 是 ExtraDDX 的数目？要遵循的行，形式

> ExtraDDX？ =*keys*; *vb-键*; *prompt*; *键入*; *initValue*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

其中? 是数字 1- *n* ，指示列表中正在定义的 DDX 类型。

每个字段由 ";" 字符分隔。 下面介绍了字段及其目的。

- *键*

  单个字符的列表，该列表指示允许哪个对话框控制此变量类型。

  |字符|允许的控件|
  |-|-|
  E | 编辑
  C | 双状态复选框
  c | 三态复选框
  R | 组中的第一个单选按钮
  L | 非排序列表框
  l | 排序列表框
  M | 带有编辑项的组合框 () 
  N | 非排序下拉列表
  n | 排序的下拉列表
  1 | 如果应将 DDX insert 添加到列表头 (默认值为 "添加到尾部") 此属性通常用于传输 "Control" 属性的 DDX 例程。

- *vb 密钥*

  此字段仅用于 VBX 控件的16位产品中 (VBX 控件在32位产品中不受支持) 

- *prompt*

  要放置在属性组合框中的字符串，不 (引号) 

- type

  要在标头文件中发出的类型的单个标识符。 在上面带有 DDX_Time 的示例中，此项设置为 CTime。

- *vb 密钥*

  未在此版本中使用并且应始终为空

- *initValue*

  初始值-0 或空白。 如果为空，则不会在实现文件的//{{AFX_DATA_INIT 部分中写入初始化行。 空项应用于 c + + 对象 (例如 `CString` 、等， `CTime`) 具有可保证正确初始化的构造函数。

- *DDX_Proc*

  DDX_ 过程的单个标识符。 C + + 函数名称必须以 "DDX_" 开头，但标识符中不能包含 "DDX_" \<DDX_Proc> 。 在上面的示例中， \<DDX_Proc> 标识符是时间。 当 ClassWizard 将函数调用写入 {{AFX_DATA_MAP 节中的实现文件时，它会将此名称附加到 DDX_，从而到达 DDX_Time。

- *comment*

  用于在带有此 DDX 的变量的对话框中显示的注释。 将你想要的任何文本放在此处，通常会提供描述 DDX/DDV 对所执行操作的内容。

- *DDV_Proc*

  项的 DDV 部分是可选的。 并非所有的 DDX 例程都具有相应的 DDV 例程。 通常，将验证阶段包含为传输的一个有机组成部分更为便利。 如果 DDV 例程不需要任何参数，则通常会出现这种情况，因为 ClassWizard 不支持没有任何参数的 DDV 例程。

- *与我们联系*

  DDV_ 过程的单个标识符。 C + + 函数名称必须以 "DDV_" 开头，但不包括标识符中的 "DDX_" \<DDX_Proc> 。

  *arg* 后跟1个或2个 DDV 参数：

  - *promptN*

      要放置在编辑项上方的字符串 (用于快捷键) 的 &。

  - *fmtN*

      Arg 类型的格式字符，其中之一：

      |字符|类型|
      |-|-|
      |d | int|
      |u | unsigned int|
      |D | 长整型 (即 long) |
      |U | 长的无符号 (，即 DWORD) |
      |F | float|
      |F | double|
      |s | 字符串|

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
