---
description: 了解详细信息： CMFCMaskedEdit 类
title: CMFCMaskedEdit 类
ms.date: 11/04/2016
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
helpviewer_keywords:
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
ms.openlocfilehash: 7ac61240e2941eafbbac3cbb03a4884e282cbca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265150"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit 类

`CMFCMaskedEdit`类支持掩码编辑控件，该控件根据掩码验证用户输入，并根据模板显示验证的结果。

## <a name="syntax"></a>语法

```
class CMFCMaskedEdit : public CEdit
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCMaskedEdit::CMFCMaskedEdit`|默认构造函数。|
|`CMFCMaskedEdit::~CMFCMaskedEdit`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCMaskedEdit：:D isableMask](#disablemask)|禁用验证用户输入。|
|[CMFCMaskedEdit：： EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|指定方法是否 `GetWindowText` 只检索掩码字符。|
|[CMFCMaskedEdit：： EnableMask](#enablemask)|初始化掩码编辑控件。|
|[CMFCMaskedEdit：： EnableSelectByGroup](#enableselectbygroup)|指定掩码编辑控件是否选择特定组的用户输入或所有用户输入。|
|[CMFCMaskedEdit：： EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|指定是仅针对掩码字符还是对整个掩码验证文本。|
|`CMFCMaskedEdit::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCMaskedEdit：： GetWindowText](#getwindowtext)|从掩码编辑控件中检索验证的文本。|
|[CMFCMaskedEdit：： SetValidChars](#setvalidchars)|指定用户可输入的有效字符的字符串。|
|[CMFCMaskedEdit：： SetWindowText](#setwindowtext)|显示掩码编辑控件中的提示。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCMaskedEdit：： IsMaskedChar](#ismaskedchar)|由框架调用，以根据相应的掩码字符验证指定的字符。|

## <a name="remarks"></a>备注

执行以下步骤以 `CMFCMaskedEdit` 在应用程序中使用控件：

1. 将 `CMFCMaskedEdit` 对象嵌入窗口类中。

2. 调用 [CMFCMaskedEdit：： EnableMask](#enablemask) 方法以指定掩码。

3. 调用 [CMFCMaskedEdit：： SetValidChars](#setvalidchars) 方法来指定有效字符的列表。

4. 调用 [CMFCMaskedEdit：： SetWindowText](#setwindowtext) 方法以指定掩码编辑控件的默认文本。

5. 调用 [CMFCMaskedEdit：： GetWindowText](#getwindowtext) 方法以检索已验证的文本。

如果未调用一个或多个方法来初始化掩码、有效字符和默认文本，则掩码编辑控件的行为就像标准编辑控件的行为一样。

## <a name="example"></a>示例

下面的示例演示如何设置掩码 (例如，通过使用 `EnableMask` 方法创建掩码编辑控件的掩码) 的电话号码、 `SetValidChars` 用于指定用户可输入的有效字符字符串的方法，以及用于在 `SetWindowText` 掩码编辑控件中显示提示的方法。 此示例是 [新控件示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)

## <a name="requirements"></a>要求

**标头：** afxmaskededit

## <a name="cmfcmaskededitdisablemask"></a><a name="disablemask"></a> CMFCMaskedEdit：:D isableMask

禁用验证用户输入。

```cpp
void DisableMask();
```

### <a name="remarks"></a>备注

如果禁用用户输入验证，则掩码编辑控件的行为类似于标准编辑控件。

## <a name="cmfcmaskededitenablegetmaskedcharsonly"></a><a name="enablegetmaskedcharsonly"></a> CMFCMaskedEdit：： EnableGetMaskedCharsOnly

指定方法是否 `GetWindowText` 只检索掩码字符。

```cpp
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中若要指定 [CMFCMaskedEdit：： GetWindowText](#getwindowtext) 方法只检索掩码字符，则为 TRUE;若为 FALSE，则指定方法检索整个文本。 默认值为 TRUE。

### <a name="remarks"></a>备注

使用此方法可以检索屏蔽字符。 然后创建对应于电话号码的掩码编辑控件，如 (425) 555-0187。 如果调用 `GetWindowText` 方法，它将返回 "4255550187"。 如果禁用检索掩码字符，该 `GetWindowText` 方法将返回在编辑控件中显示的文本，例如 " (425) 555-0187"。

## <a name="cmfcmaskededitenablemask"></a><a name="enablemask"></a> CMFCMaskedEdit：： EnableMask

初始化掩码编辑控件。

```cpp
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>parameters

*lpszMask*<br/>
中一个掩码字符串，指定可在用户输入的每个位置显示的字符类型。 *LpszInputTemplate* 和 *lpszMask* 参数字符串的长度必须相同。 有关掩码字符的详细信息，请参阅 "备注" 部分。

*lpszInputTemplate*<br/>
中屏蔽模板字符串，指定可在用户输入的每个位置显示的文本字符。 使用下划线字符 ( "_" ) 作为字符占位符。 *LpszInputTemplate* 和 *lpszMask* 参数字符串的长度必须相同。

*chMaskInputTemplate*<br/>
中框架为用户输入中的每个无效字符替换的默认字符。 此参数的默认值为下划线 ( "_" ) 。

*lpszValid*<br/>
中包含一组有效字符的字符串。 NULL 表示所有字符都有效。 此参数的默认值为 NULL。

### <a name="remarks"></a>备注

使用此方法可为掩码编辑控件创建掩码。 从类派生一个类 `CMFCMaskedEdit` ，并重写 [CMFCMaskedEdit：： IsMaskedChar](#ismaskedchar) 方法，以便为自定义掩码处理使用自己的代码。

下表列出了默认掩码字符：

|掩码字符|定义|
|--------------------|----------------|
|D|年份.|
|d|数字或空格。|
|+|加 ( "+" ) ，减 ( "-" ) 或空格。|
|C|字母字符。|
|c|字母字符或空格。|
|A|字母数字字符。|
|a|字母数字字符或空格。|
|*|可打印字符。|

## <a name="cmfcmaskededitenableselectbygroup"></a><a name="enableselectbygroup"></a> CMFCMaskedEdit：： EnableSelectByGroup

指定掩码编辑控件是否允许用户选择特定的组输入或所有输入。

```cpp
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中如果仅选择组，则为 TRUE;若要选择整个文本，则为 FALSE。 默认值为 TRUE。

### <a name="remarks"></a>备注

使用此函数指定掩码编辑控件是否允许用户按组或整个文本进行选择。

默认情况下，启用 "按组进行选择"。 在这种情况下，用户只能选择连续的有效字符组。

例如，你可以使用以下掩码编辑控件验证电话号码：

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

如果启用了 "按组进行选择"，则用户只能检索 "425"、"555" 或 "0187" 字符串组。 如果禁用了组选择，则用户可以检索电话号码的整个文本： " (425) 555-0187"。

## <a name="cmfcmaskededitenablesetmaskedcharsonly"></a><a name="enablesetmaskedcharsonly"></a> CMFCMaskedEdit：： EnableSetMaskedCharsOnly

指定是仅针对掩码字符还是对整个掩码验证文本。

```cpp
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中如果仅针对掩码字符验证用户输入，则为 TRUE;若要对整个掩码进行验证，则为 FALSE。 默认值为 TRUE。

## <a name="cmfcmaskededitgetwindowtext"></a><a name="getwindowtext"></a> CMFCMaskedEdit：： GetWindowText

从掩码编辑控件中检索验证的文本。

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>parameters

*lpszStringBuf*<br/>
弄指向缓冲区的指针，该缓冲区接收编辑控件中的文本。

*nMaxCount*<br/>
中要接收的最大字符数。

*rstrString*<br/>
弄对从编辑控件接收文本的字符串对象的引用。

### <a name="return-value"></a>返回值

第一种方法重载返回复制到 *lpszStringBuf* 参数缓冲区的字符串的字节数;如果掩码编辑控件没有文本，则为0。

### <a name="remarks"></a>备注

此方法会将掩码编辑控件中的文本复制到 *lpszStringBuf* 缓冲区或 *rstrString* 字符串。

此方法重新定义 [CWnd：： GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext)。

## <a name="cmfcmaskededitismaskedchar"></a><a name="ismaskedchar"></a> CMFCMaskedEdit：： IsMaskedChar

由框架调用，以根据相应的掩码字符验证指定的字符。

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>parameters

*chChar*<br/>
中要验证的字符。

*chMaskChar*<br/>
中掩码字符串中的相应字符。

### <a name="return-value"></a>返回值

如果 *chChar* 参数是 *chMaskChar* 参数允许的字符类型，则为 TRUE; 否则为 false。否则为 FALSE。

### <a name="remarks"></a>备注

重写此方法以验证您自己的输入字符。 有关掩码字符的详细信息，请参阅 [CMFCMaskedEdit：： EnableMask](#enablemask) 方法。

## <a name="cmfcmaskededitsetvalidchars"></a><a name="setvalidchars"></a> CMFCMaskedEdit：： SetValidChars

指定用户可输入的有效字符的字符串。

```cpp
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>parameters

*lpszValid*<br/>
中包含有效输入字符集的字符串。 NULL 表示所有字符都有效。 此参数的默认值为 NULL。

### <a name="remarks"></a>备注

使用此方法可定义有效字符的列表。 如果输入字符不在此列表中，则掩码编辑控件将不接受该字符。

下面的代码示例只接受十六进制数字。

```cpp
//Mask: 0xFFFF
m_wndMaskEdit.EnableMask(
    _T(" AAAA"),                // The mask string.
    _T("0x____"),               // The literal template string.
    _T('_'));                   // The default character that
                                // replaces the backspace character.
// Valid string characters
m_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));
```

## <a name="cmfcmaskededitsetwindowtext"></a><a name="setwindowtext"></a> CMFCMaskedEdit：： SetWindowText

显示掩码编辑控件中的提示。

```cpp
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>parameters

*lpszString*<br/>
中指向以 null 结尾的字符串，该字符串将用作提示。

### <a name="remarks"></a>备注

此方法设置控件文本。

此方法重新定义 [CWnd：： SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CEdit 类](../../mfc/reference/cedit-class.md)
