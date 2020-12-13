---
description: 了解详细信息：演练：向 MFC 项目添加动画
title: 演练：向 MFC 项目添加动画
ms.date: 04/25/2019
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
ms.openlocfilehash: ef6d6fc8e17c8e6dc4c6f0f4e8d7407f2690927f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143112"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>演练：向 MFC 项目添加动画

本演练讲授如何将基本动画对象添加到 Visual C++，Microsoft 基础类库 (MFC) 项目。

本演练演示如何完成以下任务：

- 创建 MFC 应用程序。

- 添加菜单，然后添加命令以启动和停止动画。

- 为 start 和 stop 命令创建处理程序。

- 向项目中添加一个动画对象。

- 使动画对象在窗口中居中。

- 验证结果。

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>先决条件

若要完成本演练，您必须具有 Visual Studio。

### <a name="to-create-an-mfc-application"></a>创建 MFC 应用程序

1. 使用 **Mfc 应用程序向导** 创建 MFC 应用程序。 有关如何为你的 Visual Studio 版本打开向导的说明，请参阅 [演练：使用新的 MFC Shell 控件](walkthrough-using-the-new-mfc-shell-controls.md) 。

1. 在 " **名称** " 框中，键入 *MFCAnimationWalkthrough*。 单击 **“确定”** 。

1. 在 " **MFC 应用程序向导** " 对话框中，验证 **应用程序类型** 是否为 **多个文档**， **项目样式** 为 **Visual Studio**，并选择 " **文档/视图体系结构支持** " 选项。 单击“完成”。

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>添加菜单，然后添加命令以启动和停止动画

1. 在 " **视图** " 菜单上，指向 " **其他窗口** "，然后单击 " **资源视图**"。

1. 在 **资源视图** 中，导航到 " **Menu** " 文件夹并将其打开。 双击 **IDR_MFCAnimationWalkthroughTYPE** 资源，将其打开以进行修改。

1. 在菜单栏上的 " **类型** " 框中，键入 *&Nimation* 以创建动画菜单。

1. 在 " **动画**" 下的 " **类型** " 框中，键入 " *开始 &* " 以创建 "开始转发" 命令。

1. 在 " **开始** 之前" 下的 " **类型** " 框中，键入 *Start &向后*。

1. 在 " **开始后**" 下的 " **类型** " 框中，键入 *S&top* 以创建一个停止命令。

1. 保存 MFCAnimationWalkthrough 并关闭它。

1. 在 **解决方案资源管理器** 中，双击 "mainfrm.cpp" 将其打开以进行修改。 在 `CMainFrame::OnCreate` 方法中，找到具有多个调用的部分 `lstBasicCommands.AddTail` 。 在该部分的后面，添加以下代码。

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

1. 保存文件并将其关闭。

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>为 start 和 stop 命令创建处理程序

1. 在 " **项目** " 菜单上，单击 " **类向导**"。

1. 在 **MFC 类向导** 的 " **类名称**" 下，选择 **CMFCAnimationWalkthroughView**。

1. 在 " **命令** " 选项卡上的 " **对象 id** " 框中，选择 " **ID_ANIMATION_STARTFORWARD**"，然后在 " **消息** " 框中选择 " **命令**"。 单击 " **添加处理程序**"。

1. 在 " **添加成员函数** " 对话框中，单击 **"确定"**。

1. 在 " **对象 id** " 框中，选择 " **ID_ANIMATION_STARTBACKWARD**"，然后在 " **消息** " 框中选择 " **命令**"。 单击 " **添加处理程序**"。

1. 在 " **添加成员函数** " 对话框中，单击 **"确定"**。

1. 在 " **对象 id** " 框中，选择 " **ID_ANIMATION_STOP**"，然后在 " **消息** " 框中选择 " **命令**"。 单击 " **添加处理程序** "，然后单击 **"确定"**。

1. 在 " **添加成员函数** " 对话框中，单击 **"确定"**。

1. 在 **MFC 类向导** 中，单击 **"确定"**。

1. 保存在编辑器中打开的 MFCAnimationWalkthroughView，但不要将其关闭。

### <a name="to-add-an-animated-object-to-the-project"></a>向项目添加动画对象

1. 在 **解决方案资源管理器** 中，双击 "MFCAnimationWalkthroughView" 将其打开以进行修改。 在类的定义之前 `CMFCAnimationWalkthroughView` ，添加以下代码以创建一个自定义动画控制器，该控制器将处理与动画对象的计划冲突。

    ```cpp
    class CCustomAnimationController : public CAnimationController
    {
    public:
        CCustomAnimationController()
        {
        }

        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled,
            CAnimationGroup* pGroupNew,
            UI_ANIMATION_PRIORITY_EFFECT priorityEffect)
        {
            return TRUE;
        }
    };
    ```

1. 在类的末尾 `CMFCAnimationWalkthroughView` ，添加以下代码。

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

1. 在行的后面 `DECLARE_MESSAGE_MAP()` 添加以下代码。

    ```cpp
    void Animate(BOOL bDirection);
    ```

1. 保存文件并将其关闭。

1. 在 MFCAnimationWalkthroughView 中，在 `#include` 语句后面但在任何类方法之前，添加以下代码。

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

1. 在的构造函数的末尾 `CMFCAnimationWalkthroughView` ，添加以下代码。

    ```cpp
    m_animationController.EnableAnimationTimerEventHandler();
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);
    m_animationColor = RGB(255, 255, 255);
    m_animationRect = CRect(0, 0, 0, 0);
    m_animationColor.SetID(-1, nAnimationGroup);
    m_animationRect.SetID(-1, nAnimationGroup);
    m_animationController.AddAnimationObject(&m_animationColor);
    m_animationController.AddAnimationObject(&m_animationRect);
    ```

1. 找到 `CAnimationWalthroughView::PreCreateWindow` 方法，然后将其替换为以下代码。

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

1. 找到 `CAnimationWalkthroughView::OnDraw` 方法，然后将其替换为以下代码。

    ```cpp
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)
    {
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();
        ASSERT_VALID(pDoc);
        if (!pDoc)
            return;

        // TODO: add draw code for native data here
        CMemDC dcMem(*pDC, this);
        CDC& dc = dcMem.GetDC();
        CRect rect;
        GetClientRect(rect);

        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));

        CString strRGB;
        strRGB.Format(_T("Fill Color is: %d; %d; %d"),
            GetRValue(m_animationColor),
            GetGValue(m_animationColor),
            GetBValue(m_animationColor));

        dc.DrawText(strRGB, rect, DT_CENTER);
        rect.top += nInfoAreaHeight;

        CBrush br;
        br.CreateSolidBrush(m_animationColor);
        CBrush* pBrushOld = dc.SelectObject(&br);

        dc.Rectangle((CRect)m_animationRect);

        dc.SelectObject(pBrushOld);
    }
    ```

1. 在文件末尾，添加以下代码。

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;

        CLinearTransition* pRedTransition =
            new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

        CSmoothStopTransition* pGreenTransition =
            new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

        CLinearTransitionFromSpeed* pBlueTransition =
            new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

        m_animationColor.AddTransition(pRedTransition,
            pGreenTransition,
            pBlueTransition);

        CRect rectClient;
        GetClientRect(rectClient);

        rectClient.top += nInfoAreaHeight;

        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;

        CLinearTransition* pLeftTransition =
            new CLinearTransition(duration, nLeftFinal);

        CLinearTransition* pTopTransition =
            new CLinearTransition(duration, nTopFinal);

        CLinearTransition* pRightTransition =
            new CLinearTransition(duration, nRightFinal);

        CLinearTransition* pBottomTransition =
            new CLinearTransition(duration, nBottomFinal);

        m_animationRect.AddTransition(pLeftTransition,
            pTopTransition,
            pRightTransition,
            pBottomTransition);

        CBaseKeyFrame* pKeyframeStart =
            CAnimationController::GetKeyframeStoryboardStart();
        CKeyFrame* pKeyFrameEnd =
            m_animationController.CreateKeyframe(nAnimationGroup,
                pBlueTransition);

        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);

        m_animationController.AnimateGroup(nAnimationGroup);
    }
    ```

1. 在 " **项目** " 菜单上，单击 " **类向导**"。

1. 在 **MFC 类向导** 的 " **类名称**" 下，选择 **CMFCAnimationWalkthroughView**。

1. 在 " **消息** " 选项卡上的 " **消息** " 框中，选择 " **WM_ERASEBKGND**"，单击 " **添加处理程序**"，然后单击 **"确定"**。

1. 在 MFCAnimationWalkthroughView 中，将的实现替换为 `OnEraseBkgnd` 以下代码，以在重绘动画对象时减少它们的闪烁。

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

1. 将、和的实现替换 `CMFCAnimationWalkthroughView::OnAnimationStartforward` `CMFCAnimationWalkthroughView::OnAnimationStartbackward` `CMFCAnimationWalkthroughView::OnAnimationStop` 为以下代码。

    ```cpp
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()
    {
        Animate(TRUE);
    }

    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()
    {
        Animate(FALSE);
    }

    void CMFCAnimationWalkthroughView::OnAnimationStop()
    {
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();
        if (pManager != NULL)
        {
            pManager->AbandonAllStoryboards();

        }
    }
    ```

1. 保存文件并将其关闭。

### <a name="to-center-the-animated-object-in-the-window"></a>在窗口中使动画对象居中

1. 在 **解决方案资源管理器** 中，双击 "MFCAnimationWalkthroughView" 将其打开以进行修改。 在类的末尾 `CMFCAnimationWalkthroughView` ，在定义的后面， `m_animationRect` 添加以下代码。

    ```cpp
    BOOL m_bCurrentDirection;
    ```

1. 保存文件并将其关闭。

1. 在 " **项目** " 菜单上，单击 " **类向导**"。

1. 在 **MFC 类向导** 的 " **类名称**" 下，选择 **CMFCAnimationWalkthroughView**。

1. 在 " **消息** " 选项卡上的 " **消息** " 框中，选择 " **WM_SIZE**"，单击 " **添加处理程序**"，然后单击 **"确定"**。

1. 在 MFCAnimationWalkthroughView 中，将的代码替换为 `CMFCAnimationWalkthroughView::OnSize` 以下代码。

    ```cpp
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);
        CRect rect;
        GetClientRect(rect);

        rect.top += nInfoAreaHeight;

        CRect rectAnim = m_animationRect;
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,
        rect.CenterPoint().y - rectAnim.Height() / 2),
        rectAnim.Size());

        if (m_animationController.IsAnimationInProgress())
        {
            Animate(m_bCurrentDirection);
        }
    }
    ```

1. 在的构造函数开头 `CMFCAnimationWalkthroughView` 添加以下代码。

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

1. 在方法的开头 `CMFCAnimationWalkthroughView::Animate` ，添加以下代码。

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

1. 保存文件并将其关闭。

### <a name="to-verify-the-results"></a>验证结果

1. 生成并运行应用程序。 在 **动画** 菜单上，单击 " **开始转发**"。 应显示一个矩形，然后填充中心区域。 单击 " **开始" 后**，动画应反向，单击 " **停止**" 时，该动画应停止。 动画的填充颜色应随着动画的进展而变化，并且当前颜色应显示在动画窗口的顶部。

## <a name="see-also"></a>请参阅

[演练](../mfc/walkthroughs-mfc.md)
