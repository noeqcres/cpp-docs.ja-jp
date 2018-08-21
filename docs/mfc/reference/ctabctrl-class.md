---
title: CTabCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 561f407fc651c08d46fe97486e2f9201cfe17333
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123176"
---
# <a name="ctabctrl-class"></a>CTabCtrl クラス
Windows のコモン タブ コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CTabCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](#ctabctrl)|`CTabCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](#adjustrect)|ウィンドウの四角形を指定、タブ コントロールの表示領域を計算または特定の表示領域に対応するウィンドウ四角形を計算します。|  
|[CTabCtrl::Create](#create)|タブ コントロールを作成しのインスタンスにアタッチ、`CTabCtrl`オブジェクト。|  
|[CTabCtrl::CreateEx](#createex)|指定された Windows 拡張スタイルでタブ コントロールを作成しのインスタンスにアタッチ、`CTabCtrl`オブジェクト。|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|タブ コントロールからすべての項目を削除します。|  
|[CTabCtrl::DeleteItem](#deleteitem)|タブ コントロールから項目を削除します。|  
|[CTabCtrl::DeselectAll](#deselectall)|押されたをオフにすると、タブ コントロール内の項目をリセットします。|  
|[CTabCtrl::DrawItem](#drawitem)|タブ コントロールの指定した項目を描画します。|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|タブ コントロールの現在のフォーカスを持つタブを取得します。|  
|[CTabCtrl::GetCurSel](#getcursel)|タブ コントロールで現在選択されているタブを決定します。|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|タブ コントロールで使用されている拡張スタイルを取得します。|  
|[CTabCtrl::GetImageList](#getimagelist)|タブ コントロールに関連付けられているイメージ リストを取得します。|  
|[CTabCtrl::GetItem](#getitem)|タブ コントロールのタブについての情報を取得します。|  
|[CTabCtrl::GetItemCount](#getitemcount)|タブ コントロールのタブの数を取得します。|  
|[CTabCtrl::GetItemRect](#getitemrect)|タブ コントロールにタブの外接する四角形を取得します。|  
|[CTabCtrl::GetItemState](#getitemstate)|指定されたタブ コントロール項目の状態を取得します。|  
|[CTabCtrl::GetRowCount](#getrowcount)|タブ コントロールのタブの行の現在の数を取得します。|  
|[CTabCtrl::GetToolTips](#gettooltips)|タブ コントロールに関連付けられているツール ヒント コントロールのハンドルを取得します。|  
|[CTabCtrl::HighlightItem](#highlightitem)|タブ項目の強調表示状態を設定します。|  
|[CTabCtrl::HitTest](#hittest)|どのタブ存在する場合は、指定した画面位置を決定します。|  
|[CTabCtrl::InsertItem](#insertitem)|タブ コントロールに新しいタブを挿入します。|  
|[CTabCtrl::RemoveImage](#removeimage)|タブ コントロールのイメージ リストのイメージを削除します。|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|タブ コントロール内の指定したタブにフォーカスを設定します。|  
|[CTabCtrl::SetCurSel](#setcursel)|タブ コントロールのタブを選択します。|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|タブ コントロールの拡張スタイルを設定します。|  
|[CTabCtrl::SetImageList](#setimagelist)|タブ コントロールにイメージ リストを割り当てます。|  
|[CTabCtrl::SetItem](#setitem)|一部またはすべてのタブの属性を設定します。|  
|[CTabCtrl::SetItemExtra](#setitemextra)|タブ コントロール内のアプリケーションで定義されたデータ用に予約されてタブごとのバイト数を設定します。|  
|[CTabCtrl::SetItemSize](#setitemsize)|項目の高さと幅を設定します。|  
|[CTabCtrl::SetItemState](#setitemstate)|指定されたタブ コントロール項目の状態を設定します。|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|タブ コントロールの項目の幅の最小値を設定します。|  
|[CTabCtrl::SetPadding](#setpadding)|各タブのアイコンとタブ コントロールのラベルの周りには、(埋め込み) 領域の量を設定します。|  
|[CTabCtrl::SetToolTips](#settooltips)|タブ コントロールに、ツール ヒント コントロールを割り当てます。|  
  
## <a name="remarks"></a>Remarks  
 [タブ コントロール] は、ノートの仕切りやファイル キャビネットのラベルに似ています。 タブ コントロールを使用すると、アプリケーションでウィンドウまたはダイアログ ボックスの同じ領域に複数のページを定義できます。 各ページは、一連の情報や、ユーザーが、対応するタブを選択したときに、アプリケーションで表示するコントロールのグループで構成されます。特殊な種類のタブ コントロールは、ボタンのようなタブを表示します。 ボタンをクリックしてページを表示する代わりにコマンドが実行されます。  
  
 このコントロール (したがって、`CTabCtrl`クラス) は、Windows 95/98 および Windows NT 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 使用する方法についての`CTabCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CTabCtrl](../../mfc/using-ctabctrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="adjustrect"></a>  CTabCtrl::AdjustRect  
 ウィンドウの四角形を指定、タブ コントロールの表示領域を計算または特定の表示領域に対応するウィンドウ四角形を計算します。  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *き*  
 実行する操作を示します。 このパラメーターが true の場合場合、 *lpRect*表示長方形を指定し、対応するウィンドウの四角形を受け取る。 このパラメーターが FALSE の場合*lpRect*ウィンドウ四角形を指定し、対応する表示する四角形を受け取る。  
  
 *lpRect*  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)指定された四角形を指定し、計算される四角形を受け取る。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="create"></a>  CTabCtrl::Create  
 タブ コントロールを作成しのインスタンスにアタッチ、`CTabCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 タブ コントロールのスタイルを指定します。 任意の組み合わせを適用[タブ コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760549)Windows SDK に記述されている。 参照してください**解説**コントロールに適用することもできます。 ウィンドウ スタイルの一覧についてはします。  
  
 *rect*  
 タブ コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 *pParentWnd*  
 タブ コントロールの親ウィンドウを通常を指定します、`CDialog`です。 NULL は指定できません。  
  
 *nID*  
 タブ コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 オブジェクトの初期化が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CTabCtrl` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出しておよびを呼び出す`Create`、タブ コントロールを作成しにアタッチする、`CTabCtrl`オブジェクト。  
  
 タブ コントロールのスタイルに加え、タブ コントロールに次のウィンドウ スタイルを適用できます。  
  
- WS_CHILD では、タブ コントロールを表す子ウィンドウを作成します。 WS_POPUP スタイルでは使用できません。  
  
- WS_VISIBLE では、最初に表示されているタブ コントロールを作成します。  
  
- WS_DISABLED は、最初に無効になっているウィンドウを作成します。  
  
- WS_GROUP では、ユーザーことができますに移動する 1 つのコントロールから、[次へ] 矢印キーを持つコントロールのグループの最初のコントロールを指定します。 最初のコントロールが、同じグループに属している後に WS_GROUP スタイルで定義されているすべてのコントロールです。 WS_GROUP スタイルを使用して、次のコントロールは、スタイルのグループを終了し、次のグループ (つまり、1 つのグループの末尾が次の開始位置) を開始します。  
  
- WS_TABSTOP 任意の数のいずれかのコントロールを指定する、ユーザーが TAB キーを使用して移動できます。 TAB キーでは、ユーザーが WS_TABSTOP スタイルで指定された次のコントロールを移動します。  
  
 拡張ウィンドウ スタイルを使用して、タブ コントロールを作成するには、呼び出す[CTabCtrl::CreateEx](#createex)の代わりに`Create`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  CTabCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成しに関連付けます、`CTabCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwExStyle*  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 *dwStyle*  
 タブ コントロールのスタイルを指定します。 任意の組み合わせを適用[タブ コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760549)Windows SDK に記述されている。 参照してください**解説**で[作成](#create)コントロールに適用することもできます。 ウィンドウ スタイルの一覧についてはします。  
  
 *rect*  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体*pParentWnd*です。  
  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *nID*  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用して`CreateEx`の代わりに[作成](#create)Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
 `CreateEx` 指定された拡張ウィンドウ スタイルでコントロールが作成され*dwExStyle*です。 拡張を使用してコントロールに固有のスタイル セット[拡張](#setextendedstyle)です。 たとえば、使用して`CreateEx`WS_EX_CONTEXTHELP、としてこのようなスタイルの設定が使用する`SetExtendedStyle`TCS_EX_FLATSEPARATORS としてこのようなスタイルを設定します。 詳細についてで説明されているスタイルを参照してください。[タブ コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760546)Windows SDK に含まれています。  
  
##  <a name="ctabctrl"></a>  CTabCtrl::CTabCtrl  
 `CTabCtrl` オブジェクトを構築します。  
  
```  
CTabCtrl();
```  
  
##  <a name="deleteallitems"></a>  CTabCtrl::DeleteAllItems  
 タブ コントロールからすべての項目を削除します。  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="deleteitem"></a>  CTabCtrl::DeleteItem  
 タブ コントロールから、指定した項目を削除します。  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 削除する項目の 0 から始まる値です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="deselectall"></a>  CTabCtrl::DeselectAll  
 押されたをオフにすると、タブ コントロール内の項目をリセットします。  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>パラメーター  
 *fExcludeFocus*  
 項目選択解除のスコープを指定するフラグ。 このパラメーターが FALSE に設定されている場合は、すべてのタブ ボタンがリセットされます。 現在選択されている 1 つを除く、項目を [すべて] タブ、TRUE に設定されている場合はリセットされます。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579)Windows SDK で説明されている。  
  
##  <a name="drawitem"></a>  CTabCtrl::DrawItem  
 オーナー描画タブ コントロールの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDrawItemStruct*  
 ポインター、 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802)描画する項目を記述します。  
  
### <a name="remarks"></a>Remarks  
 `itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。  
  
 既定では、このメンバー関数では何も行いません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CTabCtrl`オブジェクト。  
  
 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*関数はこのメンバーの前に終了します。  
  
##  <a name="getcurfocus"></a>  CTabCtrl::GetCurFocus  
 現在のフォーカスをタブのインデックスを取得します。  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のフォーカスを持つタブの 0 から始まるインデックス。  
  
##  <a name="getcursel"></a>  CTabCtrl::GetCurSel  
 タブ コントロールで現在選択されているタブを取得します。  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、選択されているタブまたはタブが選択されていない場合は 1 から始まるインデックス。  
  
##  <a name="getextendedstyle"></a>  CTabCtrl::GetExtendedStyle  
 タブ コントロールで使用されている拡張スタイルを取得します。  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールで使用されている拡張スタイルを表します。 この値の組み合わせである[ タブのコントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760546)Windows SDK で説明されている。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585)Windows SDK で説明されている。  
  
##  <a name="getimagelist"></a>  CTabCtrl::GetImageList  
 タブ コントロールに関連付けられているイメージ リストを取得します。  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、タブのイメージ リストへのポインターを制御します。それ以外の場合は NULL です。  
  
##  <a name="getitem"></a>  CTabCtrl::GetItem  
 タブ コントロールのタブについての情報を取得します。  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 タブの 0 から始まるインデックス。  
  
 *pTabCtrlItem*  
 ポインター、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)構造体を取得する情報を指定するために使用します。 タブの情報を受信するも使用されます。この構造体を使用、 `InsertItem`、 `GetItem`、および`SetItem`メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますFALSE それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 メッセージが送信されるときに、`mask`メンバーを返す属性を指定します。 場合、`mask`メンバー TCIF_TEXT 値を指定する、`pszText`メンバーは、項目のテキストを受け取るバッファーのアドレスを含める必要があります、`cchTextMax`メンバーは、バッファーのサイズを指定する必要があります。  
  
 `mask`  
 これを指定する値`TCITEM`構造体メンバーを取得または設定します。 このメンバーは、0、または、次の値の組み合わせを指定できます。  
  
- TCIF_TEXT、`pszText`メンバーは無効です。  
  
- TCIF_IMAGE、`iImage`メンバーは無効です。  
  
- TCIF_PARAM、`lParam`メンバーは無効です。  
  
- TCIF_RTLREADING テキストの`pszText`ヘブライ語やアラビア語のシステムで右から左への読み取り順序を使用して表示されます。  
  
- TCIF_STATE、`dwState`メンバーは無効です。  
  
 `pszText`  
 構造体には、タブについての情報が含まれている場合、タブのテキストを含む null で終わる文字列へのポインター。構造体の情報を受信は、このメンバーは、タブのテキストを受け取るバッファーのアドレスを指定します。  
  
 `cchTextMax`  
 バッファーのサイズを指す`pszText`です。 このメンバーには、構造体は、情報を受信していない場合は無視されます。  
  
 `iImage`  
 タブの画像がない場合は、タブ コントロールのイメージ リスト、または 1 をインデックスです。  
  
 lParam  
 タブに関連付けられているアプリケーション定義のデータ。4 バイトを超えるタブごとのアプリケーション定義のデータがある場合は、アプリケーションする必要があります構造体を定義しの代わりに使用、`TCITEM`構造体。 アプリケーション定義の構造体の最初のメンバーである必要があります、[アプリケーション定義](http://msdn.microsoft.com/library/windows/desktop/bb760556)構造体。 `TCITEMHEADER`構造体と同じ、`TCITEM`構造体がない、`lParam`メンバー。 構造のサイズとのサイズの違い、`TCITEMHEADER`構造体は、タブごとの追加のバイトの数を一致する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="getitemcount"></a>  CTabCtrl::GetItemCount  
 タブ コントロールのタブの数を取得します。  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロール内の項目の数です。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)です。  
  
##  <a name="getitemrect"></a>  CTabCtrl::GetItemRect  
 タブ コントロールに指定したタブの外接する四角形を取得します。  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 タブ項目の 0 から始まるインデックス。  
  
 *lpRect*  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)  タブの外接する四角形を受け取る。これらの座標は、ビューポートの現在のマップ モードを使用します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)です。  
  
##  <a name="getitemstate"></a>  CTabCtrl::GetItemState  
 によって識別されるタブ コントロール項目の状態を取得*nItem*です。  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 状態情報を取得する対象の項目の 0 から始まるインデックス番号します。  
  
 *dwMask*  
 返されるアイテムの状態のうちフラグを指定するマスクです。 値の一覧は、のマスク メンバーを参照してください、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows SDK」の説明に従って、構造体します。  
  
### <a name="return-value"></a>戻り値  
 状態情報を受け取る DWORD 値への参照。 次のいずれかの値になります。  
  
|[値]|説明|  
|-----------|-----------------|  
|TCIS_BUTTONPRESSED|タブ コントロール項目が選択されます。|  
|TCIS_HIGHLIGHTED|タブ コントロール項目が強調表示されているし、タブとテキストは現在強調表示色を使用して描画します。 強調表示色を使用する場合は true。 補間、ディザリングされた色ではないになります。|  
  
### <a name="remarks"></a>Remarks  
 項目の状態がで指定された、`dwState`のメンバー、`TCITEM`構造体。  
  
##  <a name="getrowcount"></a>  CTabCtrl::GetRowCount  
 タブ コントロール内の行の現在の数を取得します。  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールのタブの行の数。  
  
### <a name="remarks"></a>Remarks  
 TCS_MULTILINE スタイルを持つタブ コントロールのみでは、複数行のタブを持つことができます。  
  
##  <a name="gettooltips"></a>  CTabCtrl::GetToolTips  
 タブ コントロールに関連付けられているツール ヒント コントロールのハンドルを取得します。  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、ツール ヒント コントロールのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 タブ コントロールは、TCS_TOOLTIPS スタイルがある場合に、ツール ヒント コントロールを作成します。 使用して、タブ コントロールに、ツール ヒント コントロールを割り当てることができますも、`SetToolTips`メンバー関数。  
  
##  <a name="highlightitem"></a>  CTabCtrl::HighlightItem  
 タブ項目の強調表示状態を設定します。  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *idItem*  
 タブ コントロール項目の 0 から始まるインデックス。  
  
 *fHighlight*  
 設定する、強調表示状態を指定する値。 この値が TRUE の場合、タブが強調表示されます。FALSE の場合、タブは既定の状態に設定されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージを実装して[TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602)Windows SDK で説明されている。  
  
##  <a name="hittest"></a>  CTabCtrl::HitTest  
 どのタブ存在する場合は、指定した画面位置を決定します。  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pHitTestInfo*  
 ポインター、 [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553)をテストする画面上の位置を指定する Windows SDK」の説明に従って、構造体します。  
  
### <a name="return-value"></a>戻り値  
 指定した位置にタブがない場合は、タブまたは 1 の 0 から始まるインデックスを返します。  
  
##  <a name="insertitem"></a>  として  
 既存のタブ コントロールに新しいタブを挿入します。  
  
```  
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

 
LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

 
LONG InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage,  
    LPARAM lParam,  
    DWORD dwState,  
    DWORD dwStateMask);
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 新しいタブの 0 から始まるインデックス。  
  
 *pTabCtrlItem*  
 ポインター、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)構造 タブの属性を指定します。  
  
 *lpszItem*  
 タブのテキストを表す null で終わる文字列のアドレスです。  
  
 *あり*  
 イメージ リストから挿入するイメージの 0 から始まるインデックス。  
  
 *いる*  
 指定する`TCITEM`を設定する属性を構成します。 0 または次の値の組み合わせを指定できます。  
  
- TCIF_TEXT、`pszText`メンバーは無効です。  
  
- TCIF_IMAGE、`iImage`メンバーは無効です。  
  
- TCIF_PARAM、 *lParam*メンバーは無効です。  
  
- TCIF_RTLREADING テキストの`pszText`ヘブライ語やアラビア語のシステムで右から左への読み取り順序を使用して表示されます。  
  
- TCIF_STATE、 *dwState*メンバーは無効です。  
  
 *lParam*  
 タブに関連付けられているアプリケーション定義のデータ。  
  
 *dwState*  
 項目の状態の値を指定します。 詳細については、次を参照してください。 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows SDK に含まれています。  
  
 *dwStateMask*  
 設定する状態を指定します。 詳細については、次を参照してください。 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、新しいタブの 0 から始まるインデックスそれ以外の場合 - 1。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="removeimage"></a>  CTabCtrl::RemoveImage  
 タブ コントロールのイメージ リストから、指定されたイメージを削除します。  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>パラメーター  
 *あり*  
 削除するイメージの 0 から始まるインデックス。  
  
### <a name="remarks"></a>Remarks  
 タブ コントロールは、各タブは、同じイメージに関連付けできるように、各タブのイメージのインデックスを更新します。  
  
##  <a name="setcurfocus"></a>  CTabCtrl::SetCurFocus  
 タブ コントロール内の指定したタブにフォーカスを設定します。  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 フォーカスをタブのインデックスを指定します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610)Windows SDK で説明されている。  
  
##  <a name="setcursel"></a>  CTabCtrl::SetCurSel  
 タブ コントロールのタブを選択します。  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 選択する項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、以前に選択したタブの 0 から始まるインデックスそれ以外の場合 - 1。  
  
### <a name="remarks"></a>Remarks  
 タブ コントロールでは、この関数を使用して、タブを選択した場合は、または TCN_SELCHANGE 通知メッセージを送信しません。 WM_NOTIFY を使用して、ユーザーがクリックするか、キーボードを使用して、タブを変更するときにこれらの通知が送信されます。  
  
##  <a name="setextendedstyle"></a>  CTabCtrl::SetExtendedStyle  
 タブ コントロールの拡張スタイルを設定します。  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwNewStyle*  
 タブの組み合わせを指定する値は、拡張スタイルを制御します。  
  
 *dwExMask*  
 スタイルを示す DWORD 値*dwNewStyle*影響を受けるには、します。 拡張スタイルのみ*dwExMask*変更されます。 他のすべてのスタイルが保持されます。 このパラメーターが 0、すべてのスタイルの場合*dwNewStyle*を受けます。  
  
### <a name="return-value"></a>戻り値  
 DWORD 値を含む、以前[ タブのコントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760546)Windows SDK で説明されている。  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627)Windows SDK で説明されている。  
  
##  <a name="setimagelist"></a>  CTabCtrl::SetImageList  
 タブ コントロールにイメージ リストを割り当てます。  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 *pImageList*  
 タブ コントロールに割り当てられるイメージ リストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 直前のイメージ リストが存在しない場合、直前のイメージ リストまたは NULL へのポインターを返します。  
  
##  <a name="setitem"></a>  CTabCtrl::SetItem  
 一部またはすべてのタブの属性を設定します。  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 項目の 0 から始まるインデックス。  
  
 *pTabCtrlItem*  
 ポインター、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)新しいアイテムの属性を格納する構造体。 `mask`メンバーを設定する属性を指定します。 場合、`mask`メンバー TCIF_TEXT 値を指定する、`pszText`メンバーは、null で終わる文字列のアドレスと`cchTextMax`メンバーは無視されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照して[GetItem](#getitem)です。  
  
##  <a name="setitemextra"></a>  CTabCtrl::SetItemExtra  
 タブ コントロール内のアプリケーションで定義されたデータ用に予約されてタブごとのバイト数を設定します。  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBytes*  
 設定する追加のバイト数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633)Windows SDK で説明されている。  
  
##  <a name="setitemsize"></a>  CTabCtrl::SetItemSize  
 タブ コントロール項目の幅と高さを設定します。  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>パラメーター  
 *size*  
 タブ コントロール項目の新しい幅と高さ (ピクセル単位)。  
  
### <a name="return-value"></a>戻り値  
 タブ コントロール項目の古い幅と高さを返します。  
  
##  <a name="setitemstate"></a>  CTabCtrl::SetItemState  
 によって識別されるタブ コントロール項目の状態を設定*nItem*です。  
  
```  
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```  
  
### <a name="parameters"></a>パラメーター  
 *nItem*  
 状態情報を設定する対象の項目の 0 から始まるインデックス番号します。  
  
 *dwMask*  
 アイテムの状態のうちフラグ設定を指定するマスクです。 値の一覧は、のマスク メンバーを参照してください、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows SDK」の説明に従って、構造体します。  
  
 *dwState*  
 状態情報を含む DWORD 値への参照。 次のいずれかの値になります。  
  
|[値]|説明|  
|-----------|-----------------|  
|TCIS_BUTTONPRESSED|タブ コントロール項目が選択されます。|  
|TCIS_HIGHLIGHTED|タブ コントロール項目が強調表示されているし、タブとテキストは現在強調表示色を使用して描画します。 強調表示色を使用する場合は true。 補間、ディザリングされた色ではないになります。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="setmintabwidth"></a>  CTabCtrl::SetMinTabWidth  
 タブ コントロールの項目の幅の最小値を設定します。  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>パラメーター  
 *cx*  
 タブ コントロール項目用に設定する最小の幅。 このパラメーターが-1 に設定されている場合、コントロールは既定のタブ幅を使用します。  
  
### <a name="return-value"></a>戻り値  
 前の最小値 タブの幅。  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637)Windows SDK で説明されている。  
  
##  <a name="setpadding"></a>  CTabCtrl::SetPadding  
 各タブのアイコンとタブ コントロールのラベルの周りには、(埋め込み) 領域の量を設定します。  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>パラメーター  
 *size*  
 各タブのアイコンとタブ コントロールのラベルの周りには、(埋め込み) 領域の量を設定します。  
  
##  <a name="settooltips"></a>  CTabCtrl::SetToolTips  
 タブ コントロールに、ツール ヒント コントロールを割り当てます。  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndTip*  
 ツール ヒント コントロールのハンドルです。  
  
### <a name="remarks"></a>Remarks  
 呼び出すことによって、タブ コントロールに関連付けられているツール ヒント コントロールを取得する`GetToolTips`です。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)です。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl クラス](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl クラス](../../mfc/reference/clistctrl-class.md)
