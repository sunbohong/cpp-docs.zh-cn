---
description: 了解详细信息：在 Rich Edit 控件中设置段落格式
title: Rich Edit 控件中的段落格式设置
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: 69c853c6b552b9950769fc9e3509bd4b5e55ea43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205910"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Rich Edit 控件中的段落格式设置

您可以使用 rich edit 控件 ([CRichEditCtrl](reference/cricheditctrl-class.md)) 的成员函数设置段落格式，并检索格式设置信息。 段落格式设置特性包括对齐、选项卡、缩进和编号。

您可以使用 [SetParaFormat](reference/cricheditctrl-class.md#setparaformat) 成员函数应用段落格式设置。 若要确定所选文本的当前段落格式，请使用 [GetParaFormat](reference/cricheditctrl-class.md#getparaformat) 成员函数。 [PARAFORMAT](/windows/win32/api/richedit/ns-richedit-paraformat)结构与这些成员函数结合使用来指定段落属性。 **PARAFORMAT** 的一个重要成员是 *dwMask*。 在中 `SetParaFormat` ， *dwMask* 指定将通过此函数调用设置的段落属性。 `GetParaFormat` 报告所选内容中第一个段落的属性; *dwMask* 指定在整个选定内容中一致的属性。

## <a name="see-also"></a>请参阅

[使用 CRichEditCtrl](using-cricheditctrl.md)<br/>
[控件](controls-mfc.md)
