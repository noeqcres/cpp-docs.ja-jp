---
title: CMFCColorPopupMenu クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b32317f4fd67a627a272ea8eefcc949d1b0e63c8
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852995"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu クラス
ユーザーが文書またはアプリケーションで色の選択に使用するポップアップ メニューを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|`CMFCColorPopupMenu` オブジェクトを構築します。|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|ドッキング可能なティアオフ カラー バーを作成します。 (上書き[CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar))。|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|返します、 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)ポップアップ メニュー内に埋め込まれています。 (上書き[CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar))。|  
|`CMFCColorPopupMenu::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|埋め込みのプロパティ グリッド コントロール オブジェクトを設定`CMFCColorBar`オブジェクト。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|name|説明|  
|`m_bEnabledInCustomizeMode`|カラー バーを表示するかどうかを決定するブール値。|  
|`m_wndColorBar`|`CMFCColorBar`色の選択を提供するオブジェクト。|  
  
### <a name="remarks"></a>Remarks  
 このクラスは継承のポップアップ メニュー機能、`CMFCPopupMenu`クラスし、管理、`CMFCColorBar`色の選択を提供するオブジェクト。 ツールバーのフレームワークがカスタマイズ モードの場合に、`m_bEnabledInCustomizeMode`メンバーが FALSE に設定、カラー バーのオブジェクトは表示されません。 カスタマイズ モードの詳細については、次を参照してください[CMFCToolBar::IsCustomizeMode。](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 詳細については`CMFCColorBar`を参照してください[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcolorpopupmenu.h  
  
##  <a name="cmfccolorpopupmenu"></a>  CMFCColorPopupMenu::CMFCColorPopupMenu  
 `CMFCColorPopupMenu` オブジェクトを構築します。  
  
```  
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);

 
CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic);

 
CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*色*  
 フレームワークは、ポップアップ メニューに表示する色の配列。  
  
 [in]*色*  
 選択されている既定の色。  
  
 [in]*lpszAutoColor*  
 テキスト ラベル、*自動*(既定値) の色のボタン、または NULL。  
  
 自動ボタンの標準的なラベルが**自動**します。  
  
 [in]*lpszOtherColor*  
 テキスト ラベル、*他*ボタンが表示されるより色の選択、または NULL。  
  
 その他のボタンの標準のラベルは**他の色**。  
  
 [in]*lpszDocColors*  
 ドキュメントの色のボタンのテキスト ラベル。 ドキュメントのカラー パレットには、ドキュメントが現在使用されているすべての色が一覧表示します。  
  
 [in]*lstDocColors*  
 ドキュメントが現在使用されている色の一覧。  
  
 [in]*nColumns*  
 色の配列を含む列の数。  
  
 [in]*nHorzDockRows*  
 カラー バーが水平方向にドッキングされている行の数。  
  
 [in]*nVertDockColumns*  
 カラー バーが垂直方向にドッキングされている列の数。  
  
 [in]*colorAutomatic*  
 自動ボタンをクリックすると、フレームワークが適用される既定の色。  
  
 [in]*uiCommandID*  
 カラー バーのコントロールのコマンド id。  
  
 [in]*bStdColorDlg*  
 標準のシステム カラーのダイアログ ボックスを表示するかどうかを示すブール値、または[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックス。  
  
 [in]*pParentBtn*  
 親ボタンへのポインター。  
  
 [in]*nID*  
 コマンド ID。  
  
### <a name="remarks"></a>Remarks  
 それぞれのオーバー ロードされたコンス トラクターのセット、`m_bEnabledInCustomizeMode`メンバーを FALSE にします。  
  
### <a name="example"></a>例  
 次の例は、構築する方法を示します、`CMFCColorPopupMenu`オブジェクト。  
  
 [!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar  
 ドッキング可能なティアオフ カラー バーを作成します。  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*pWndMain*|ティアオフ バーの親ウィンドウへのポインター。|  
|[in]*uiID*|ティアオフ バーのコマンド ID。|  
|[in]*lpszName*|ティアオフ バーのウィンドウのテキスト。|  
  
### <a name="return-value"></a>戻り値  
 新しいティアオフ コントロール バー オブジェクトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを作成、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクトおよびにキャスト、 [CPane クラス](../../mfc/reference/cpane-class.md)ポインター。 この値をキャストすることに、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)で説明するキャスト マクロのいずれかを使用してポインター [MFC クラス オブジェクトの型キャスト](../../mfc/reference/type-casting-of-mfc-class-objects.md)します。  
  
##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar  
 返します、 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)ポップアップ メニュー内に埋め込まれています。  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>戻り値  
 埋め込まれたへのポインター`CMFCPopupMenuBar`します。  
  
### <a name="remarks"></a>Remarks  
 色のポップアップ メニューが埋め込まれた[CMFCPopupMenuBar クラス](../../mfc/reference/cmfcpopupmenubar-class.md)オブジェクト。 アプリケーションが別の埋め込み型を使用する場合は、派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList  
 埋め込みのプロパティ グリッド コントロール オブジェクトを設定`CMFCColorBar`オブジェクト。  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndList*  
 プロパティ グリッド コントロール オブジェクトへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
