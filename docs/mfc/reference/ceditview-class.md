---
description: 了解详细信息： CEditView 类
title: CEditView 类
ms.date: 11/04/2016
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
ms.openlocfilehash: b83b83b90fe530d2615a507d80e2af771397d286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184707"
---
# <a name="ceditview-class"></a>CEditView 类

视图类的类型，提供 Windows 编辑控件功能并可用于实现简单的文本编辑器功能。

## <a name="syntax"></a>语法

```
class CEditView : public CCtrlView
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CEditView：： CEditView](#ceditview)|构造 `CEditView` 类型的对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CEditView：： FindText](#findtext)|搜索文本中的字符串。|
|[CEditView：： GetBufferLength](#getbufferlength)|获取字符缓冲区的长度。|
|[CEditView：： GetEditCtrl](#geteditctrl)|提供对 `CEdit` `CEditView` (Windows 编辑控件) 的对象部分的访问。|
|[CEditView：： GetPrinterFont](#getprinterfont)|检索当前打印机字体。|
|[CEditView：： GetSelectedText](#getselectedtext)|检索当前选定文本。|
|[CEditView：： LockBuffer](#lockbuffer)|锁定缓冲区。|
|[CEditView：:P rintInsideRect](#printinsiderect)|在给定矩形内呈现文本。|
|[CEditView：： SerializeRaw](#serializeraw)|`CEditView`将对象作为原始文本序列化到磁盘。|
|[CEditView：： SetPrinterFont](#setprinterfont)|设置新的打印机字体。|
|[CEditView：： SetTabStops](#settabstops)|为屏幕显示和打印设置制表位。|
|[CEditView：： UnlockBuffer](#unlockbuffer)|锁定缓冲区。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CEditView：： OnFindNext](#onfindnext)|查找文本字符串的下一个匹配项。|
|[CEditView：： OnReplaceAll](#onreplaceall)|将出现的所有给定字符串替换为新字符串。|
|[CEditView：： OnReplaceSel](#onreplacesel)|替换当前选定内容。|
|[CEditView：： OnTextNotFound](#ontextnotfound)|当查找操作无法匹配任何其他文本时调用。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CEditView：:d wStyleDefault](#dwstyledefault)|类型的对象的默认样式 `CEditView` 。|

## <a name="remarks"></a>备注

`CEditView`类提供以下附加函数：

- 打印。

- 查找和替换。

由于类 `CEditView` 是类的派生类 `CView` ，因此类的对象 `CEditView` 可与文档和文档模板一起使用。

每个 `CEditView` 控件的文本将保存在其自己的全局内存对象中。 应用程序可以具有任意数量的 `CEditView` 对象。

`CEditView`如果需要具有上面列出的已添加功能的编辑窗口，或者需要简单的文本编辑器功能，请创建类型的对象。 `CEditView`对象可以占据窗口的整个工作区。 从派生你自己的类 `CEditView` ，以添加或修改基本功能，或声明可添加到文档模板的类。

类的默认实现将 `CEditView` 处理以下命令： ID_EDIT_SELECT_ALL、ID_EDIT_FIND、ID_EDIT_REPLACE、ID_EDIT_REPEAT 和 ID_FILE_PRINT。

的默认字符限制 `CEditView` (1024 \* 1024-1 = 1048575) 。 这可以通过调用基础编辑控件的 EM_LIMITTEXT 函数进行更改。 但是，根据操作系统和编辑控件类型 (单个或多行) ，限制会有所不同。 有关这些限制的详细信息，请参阅 [EM_LIMITTEXT](/windows/win32/Controls/em-limittext)。

若要更改控件中的此限制，请重写 `OnCreate()` 类的函数 `CEditView` 并插入以下代码行：

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

类型 (类型 `CEditView` 或派生自) 的类型的对象 `CEditView` 具有以下限制：

- `CEditView` 不会实现 true，你所看到的内容是 (WYSIWYG) 编辑。 在屏幕上的可读性和打印输出之间进行选择时，选择 " `CEditView` 屏幕可读性"。

- `CEditView` 只能显示单个字体中的文本。 不支持特殊字符格式设置。 有关更多功能，请参阅类 [CRichEditView](../../mfc/reference/cricheditview-class.md) 。

- 可以包含的文本量 `CEditView` 受到限制。 此限制与控件的限制相同 `CEdit` 。

有关的详细信息 `CEditView` ，请参阅 [MFC 中可用的派生视图类](../../mfc/derived-view-classes-available-in-mfc.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>要求

**标头：** afxext。h

## <a name="ceditviewceditview"></a><a name="ceditview"></a> CEditView：： CEditView

构造 `CEditView` 类型的对象。

```
CEditView();
```

### <a name="remarks"></a>备注

构造对象之后，必须先调用 [CWnd：： Create](../../mfc/reference/cwnd-class.md#create) 函数，然后才能使用编辑控件。 如果从派生类 `CEditView` 并使用将其添加到模板 `CWinApp::AddDocTemplate` 中，则框架将调用此构造函数和 `Create` 函数。

## <a name="ceditviewdwstyledefault"></a><a name="dwstyledefault"></a> CEditView：:d wStyleDefault

包含对象的默认样式 `CEditView` 。

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>备注

将此静态成员作为函数的 *dwStyle* 参数传递 `Create` ，以获取该对象的默认样式 `CEditView` 。

## <a name="ceditviewfindtext"></a><a name="findtext"></a> CEditView：： FindText

调用 `FindText` 函数，搜索 `CEditView` 对象的文本缓冲区。

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>parameters

*lpszFind*<br/>
要查找的文本。

*bNext*<br/>
指定搜索的方向。 如果为 TRUE，则搜索方向朝向缓冲区的末尾。 如果为 FALSE，则搜索方向朝向缓冲区的开头。

*bCase*<br/>
指定搜索是否区分大小写。 如果为 TRUE，则搜索区分大小写。 如果为 FALSE，则搜索不区分大小写。

### <a name="return-value"></a>返回值

如果找到搜索文本，则为非零值;否则为0。

### <a name="remarks"></a>备注

此函数在缓冲区中的文本中搜索 *lpszFind* 指定的文本，从当前所选内容开始，按 *bNext* 指定的方向，并使用 *bCase* 指定的区分大小写。 如果找到文本，它会将所选内容设置为找到的文本并返回一个非零值。 如果未找到文本，则函数返回0。

通常不需要调用 `FindText` 函数，除非重写 `OnFindNext` ，这将调用 `FindText` 。

## <a name="ceditviewgetbufferlength"></a><a name="getbufferlength"></a> CEditView：： GetBufferLength

调用此成员函数以获取编辑控件缓冲区中当前包含的字符数，不包括 null 终止符。

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>返回值

缓冲区中的字符串的长度。

## <a name="ceditviewgeteditctrl"></a><a name="geteditctrl"></a> CEditView：： GetEditCtrl

调用 `GetEditCtrl` 以获取对 "编辑" 视图使用的编辑控件的引用。

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>返回值

对 `CEdit` 对象的引用。

### <a name="remarks"></a>备注

此控件的类型为 [CEdit](../../mfc/reference/cedit-class.md)，因此可以使用成员函数直接操作 Windows 编辑控件 `CEdit` 。

> [!CAUTION]
> 使用 `CEdit` 对象可以更改基本 Windows 编辑控件的状态。 例如，不应使用 [CEdit：： SetTabStops](../../mfc/reference/cedit-class.md#settabstops) 函数更改选项卡设置，因为 `CEditView` 缓存这些设置以在编辑控件和打印中使用两者。 改为使用 [CEditView：： SetTabStops](#settabstops)。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

## <a name="ceditviewgetprinterfont"></a><a name="getprinterfont"></a> CEditView：： GetPrinterFont

调用 `GetPrinterFont` 以获取指向描述当前打印机字体的 [CFont](../../mfc/reference/cfont-class.md) 对象的指针。

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>返回值

指向 `CFont` 对象的指针，该对象指定当前打印机字体;如果尚未设置打印机字体，则为 NULL。 该指针可能是暂时的，不应存储起来供将来使用。

### <a name="remarks"></a>备注

如果尚未设置打印机字体，则类的默认打印行为 `CEditView` 是使用用于显示的相同字体打印。

使用此函数可确定当前打印机的字体。 如果不是所需的打印机字体，请使用 [CEditView：： SetPrinterFont](#setprinterfont) 对其进行更改。

## <a name="ceditviewgetselectedtext"></a><a name="getselectedtext"></a> CEditView：： GetSelectedText

调用 `GetSelectedText` 可将所选文本复制到 `CString` 对象中，直至所选内容的末尾或第一个回车符前面的字符。

```cpp
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>parameters

*strResult*<br/>
对 `CString` 接收所选文本的对象的引用。

## <a name="ceditviewlockbuffer"></a><a name="lockbuffer"></a> CEditView：： LockBuffer

调用此成员函数以获取指向缓冲区的指针。 不应修改该缓冲区。

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>返回值

指向编辑控件缓冲区的指针。

## <a name="ceditviewonfindnext"></a><a name="onfindnext"></a> CEditView：： OnFindNext

在缓冲区中搜索 *lpszFind* 指定的文本的缓冲区中的文本，并在 *bNext* 指定的方向上按照 *bCase* 指定的区分大小写。

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>parameters

*lpszFind*<br/>
要查找的文本。

*bNext*<br/>
指定搜索的方向。 如果为 TRUE，则搜索方向朝向缓冲区的末尾。 如果为 FALSE，则搜索方向朝向缓冲区的开头。

*bCase*<br/>
指定搜索是否区分大小写。 如果为 TRUE，则搜索区分大小写。 如果为 FALSE，则搜索不区分大小写。

### <a name="remarks"></a>备注

搜索从当前所选内容的开头开始，并通过调用 [FindText](#findtext)来完成。 在默认实现中， `OnFindNext` 如果未找到文本，则调用 [OnTextNotFound](#ontextnotfound) 。

重写 `OnFindNext` 以更改 `CEditView` 派生对象搜索文本的方式。 `CEditView``OnFindNext`当用户选择 "标准查找" 对话框中的 "查找下一个" 按钮时调用。

## <a name="ceditviewonreplaceall"></a><a name="onreplaceall"></a> CEditView：： OnReplaceAll

`CEditView``OnReplaceAll`当用户选择 "标准替换" 对话框中的 "全部替换" 按钮时调用。

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>parameters

*lpszFind*<br/>
要查找的文本。

*lpszReplace*<br/>
要替换搜索文本的文本。

*bCase*<br/>
指定搜索是否区分大小写。 如果为 TRUE，则搜索区分大小写。 如果为 FALSE，则搜索不区分大小写。

### <a name="remarks"></a>备注

`OnReplaceAll` 在缓冲区中搜索 *lpszFind* 指定的文本，并在 *bCase* 指定的情况下区分大小写。 搜索从当前所选内容的开头开始。 每次找到搜索文本时，此函数就会将该文本的出现替换为 *lpszReplace* 指定的文本。 搜索是通过调用 [FindText](#findtext)来完成的。 在默认实现中，如果未找到文本，则会调用 [OnTextNotFound](#ontextnotfound) 。

如果当前所选内容与 *lpszFind* 不匹配，则会将所选内容更新为 *lpszFind* 指定的文本的第一个匹配项，并且不会执行 replace。 这允许用户确认在所选内容与要替换的文本不匹配时要执行的操作。

重写 `OnReplaceAll` 以更改 `CEditView` 派生对象替换文本的方式。

## <a name="ceditviewonreplacesel"></a><a name="onreplacesel"></a> CEditView：： OnReplaceSel

`CEditView``OnReplaceSel`当用户在 "标准替换" 对话框中选择 "替换" 按钮时调用。

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>parameters

*lpszFind*<br/>
要查找的文本。

*bNext*<br/>
指定搜索的方向。 如果为 TRUE，则搜索方向朝向缓冲区的末尾。 如果为 FALSE，则搜索方向朝向缓冲区的开头。

*bCase*<br/>
指定搜索是否区分大小写。 如果为 TRUE，则搜索区分大小写。 如果为 FALSE，则搜索不区分大小写。

*lpszReplace*<br/>
用于替换所找到文本的文本。

### <a name="remarks"></a>备注

替换所选内容后，此函数将在缓冲区中的文本中搜索 *lpszFind* 指定的文本的下一个匹配项，并 *以由* *bCase* 指定的区分大小写。 搜索是通过调用 [FindText](#findtext)来完成的。 如果未找到文本，则调用 [OnTextNotFound](#ontextnotfound) 。

重写 `OnReplaceSel` 以更改 `CEditView` 派生对象替换所选文本的方式。

## <a name="ceditviewontextnotfound"></a><a name="ontextnotfound"></a> CEditView：： OnTextNotFound

重写此函数以更改调用 Windows 函数的默认实现 `MessageBeep` 。

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>parameters

*lpszFind*<br/>
要查找的文本。

## <a name="ceditviewprintinsiderect"></a><a name="printinsiderect"></a> CEditView：:P rintInsideRect

调用 `PrintInsideRect` 以打印 *rectLayout* 指定的矩形中的文本。

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
指向打印机设备上下文的指针。

*rectLayout*<br/>
对 [CRect](../../atl-mfc-shared/reference/crect-class.md) 对象或 [RECT 结构](/windows/win32/api/windef/ns-windef-rect) 的引用，指定要在其中呈现文本的矩形。

*nIndexStart*<br/>
要呈现的第一个字符的缓冲区中的索引。

*nIndexStop*<br/>
在要呈现的最后一个字符之后的字符缓冲区中的索引。

### <a name="return-value"></a>返回值

要打印的下一个字符的索引 (即，最后一个呈现) 的字符后面的字符。

### <a name="remarks"></a>备注

如果 `CEditView` 控件没有 ES_AUTOHSCROLL 样式，则文本在呈现矩形内进行包装。 如果控件确实具有 ES_AUTOHSCROLL 样式，则将在矩形的右边缘剪切文本。

`rect.bottom`更改 *rectLayout* 对象的元素，以使矩形的维度定义由文本占用的原始矩形部分。

## <a name="ceditviewserializeraw"></a><a name="serializeraw"></a> CEditView：： SerializeRaw

调用 `SerializeRaw` 以使 `CArchive` 对象在对象中读取或写入文本文件中的文本 `CEditView` 。

```cpp
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>parameters

*ar*<br/>
对 `CArchive` 存储序列化文本的对象的引用。

### <a name="remarks"></a>备注

`SerializeRaw` 不同于 `CEditView` 的的内部实现， `Serialize` 因为它仅读取并写入文本，而不包含之前的对象说明数据。

## <a name="ceditviewsetprinterfont"></a><a name="setprinterfont"></a> CEditView：： SetPrinterFont

调用将 `SetPrinterFont` 打印机字体设置为 *pFont* 指定的字体。

```cpp
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>parameters

*pFont*<br/>
指向类型的对象的指针 `CFont` 。 如果为 NULL，则用于打印的字体基于显示字体。

### <a name="remarks"></a>备注

如果希望视图始终使用特定字体进行打印，请 `SetPrinterFont` 在类的函数中包含对的调用 `OnPreparePrinting` 。 此虚函数在打印之前被调用，因此，字体更改发生在视图内容打印之前。

## <a name="ceditviewsettabstops"></a><a name="settabstops"></a> CEditView：： SetTabStops

调用此函数可设置用于显示和打印的制表位。

```cpp
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>parameters

*nTabStops*<br/>
每个制表位的宽度（以对话框单位为单位）。

### <a name="remarks"></a>备注

仅支持单一的制表位宽度。  ( `CEdit` 对象支持多个制表符宽度。 ) 宽度采用对话单位，它们等于普通字符宽度的第四个 (，这等于在打印或显示时使用的字体) 的大写和小写字母字符。 不应使用， `CEdit::SetTabStops` 因为 `CEditView` 必须缓存制表位值。

此函数仅修改为其调用该函数的对象的选项卡。 若要更改应用程序中每个对象的制表位 `CEditView` ，请调用每个对象的 `SetTabStops` 函数。

### <a name="example"></a>示例

此代码片段通过仔细度量控件使用的字体，将控件中的制表位设置为每个第四个字符。

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

## <a name="ceditviewunlockbuffer"></a><a name="unlockbuffer"></a> CEditView：： UnlockBuffer

调用此成员函数以解锁缓冲区。

```cpp
void UnlockBuffer() const;
```

### <a name="remarks"></a>备注

`UnlockBuffer`使用[LockBuffer](#lockbuffer)返回的指针完成后调用。

## <a name="see-also"></a>请参阅

[MFC 示例 SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView 类](../../mfc/reference/cctrlview-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CEdit 类](../../mfc/reference/cedit-class.md)<br/>
[CDocument 类](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate 类](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView 类](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView 类](../../mfc/reference/cricheditview-class.md)
