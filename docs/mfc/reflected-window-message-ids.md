---
title: ウィンドウ メッセージの Id を反映 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OCM_CTLCOLORBTN
- OCM_PARENTNOTIFY
- OCM_VKEYTOITEM
- OCM_CTLCOLORSTATIC
- OCM_HSCROLL
- OCM_CHARTOITEM
- OCM_DRAWITEM
- OCM_MEASUREITEM
- OCM_COMPAREITEM
- OCM_COMMAND
- OCM_NOTIFY
- OCM_CTLCOLORMSGBOX
- OCM_DELETEITEM
- OCM_CTLCOLORLISTBOX
- OCM_CTLCOLORDLG
- OCM_CTLCOLOREDIT
- OCM_CTLCOLORSCROLLBAR
- OCM_VSCROLL
- OCM_CTLCOLOR
dev_langs:
- C++
helpviewer_keywords:
- OCM_HSCROLL message [MFC]
- OCM_PARENTNOTIFY message [MFC]
- messages, reflected
- reflected messages, window message Ids
- OCM_CTLCOLORDLG message [MFC]
- OCM_COMMAND message [MFC]
- OCM_CTLCOLORMSGBOX message [MFC]
- OCM_COMPAREITEM message [MFC]
- OCM_DRAWITEM message [MFC]
- OCM_VSCROLL message [MFC]
- OCM_CTLCOLOREDIT message [MFC]
- OCM_VKEYTOITEM message [MFC]
- OCM_CHARTOITEM message [MFC]
- OCM_CTLCOLORBTN message [MFC]
- OCM_CTLCOLORSTATIC message [MFC]
- OCM_MEASUREITEM message [MFC]
- OCM_CTLCOLOR message [MFC]
- OCM_CTLCOLORSCROLLBAR message [MFC]
- OCM_ messages
- OCM_DELETEITEM message [MFC]
- OCM_CTLCOLORLISTBOX message [MFC]
- OCM_NOTIFY message [MFC]
- reflected messages
ms.assetid: 3417ff51-ff9f-458c-bff4-17c200f00d96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8746666c4b1eb48e4c54822f76328579b7ce8584
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928199"
---
# <a name="reflected-window-message-ids"></a>返送されたウィンドウ メッセージの ID
ActiveX コントロール、またはその他の特殊なコントロールを作成する簡単な方法では、ウィンドウをサブクラス化です。 詳細については、次を参照してください。 [MFC ActiveX コントロール: Windows コントロールのサブクラス化](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)です。  
  
 コントロールのコンテナーが、Windows コントロールのサブクラスによって送信されたウィンドウ メッセージを受信するを防ぐため[COleControl](../mfc/reference/colecontrol-class.md)を特定のウィンドウ メッセージを途中受信して、それらをコントロールに送信する"reflector という"ウィンドウを作成します。 コントロールのウィンドウ プロシージャでは、ActiveX コントロールの適切な操作を実行して返送されたメッセージを処理できます。  
  
 次の表は、途中で取得されたメッセージと reflector ウィンドウに送信される対応するメッセージを示します。  
  
|コントロールによって送信されたメッセージ|コントロールに反映されるメッセージ|  
|---------------------------------|--------------------------------------|  
|[WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)|OCM_COMMAND|  
|[WM_CTLCOLORBTN](http://msdn.microsoft.com/library/windows/desktop/bb761849)|OCM_CTLCOLORBTN|  
|[WM_CTLCOLOREDIT](http://msdn.microsoft.com/library/windows/desktop/bb761691)|OCM_CTLCOLOREDIT|  
|[WM_CTLCOLORDLG](http://msdn.microsoft.com/library/windows/desktop/ms645417)|OCM_CTLCOLORDLG|  
|[WM_CTLCOLORLISTBOX](http://msdn.microsoft.com/library/windows/desktop/bb761360)|OCM_CTLCOLORLISTBOX|  
|[WM_CTLCOLORSCROLLBAR](http://msdn.microsoft.com/library/windows/desktop/bb787573)|OCM_CTLCOLORSCROLLBAR|  
|[WM_CTLCOLORSTATIC](http://msdn.microsoft.com/library/windows/desktop/bb787524)|OCM_CTLCOLORSTATIC|  
|[WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923)|OCM_DRAWITEM|  
|[ため](http://msdn.microsoft.com/library/windows/desktop/bb775925)|OCM_MEASUREITEM|  
|[WM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb761362)|OCM_DELETEITEM|  
|[WM_VKEYTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761364)|OCM_VKEYTOITEM|  
|[WM_CHARTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761358)|OCM_CHARTOITEM|  
|[WM_COMPAREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775921)|OCM_COMPAREITEM|  
|[兄弟](http://msdn.microsoft.com/library/windows/desktop/bb787575)|OCM_HSCROLL|  
|[WM_VSCROLL](http://msdn.microsoft.com/library/windows/desktop/bb787577)|OCM_VSCROLL|  
|[WM_PARENTNOTIFY](https://msdn.microsoft.com/library/ms632638.aspx)|OCM_PARENTNOTIFY|  
|[WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)|OCM_NOTIFY|  
  
> [!NOTE]
>  WM_CTLCOLOR のいくつかの型がある場合、コントロールは、Win32 システムで実行される、\*メッセージがあります。 詳細については、WM_CTLCOLORBTN WM_CTLCOLORDLG、WM_CTLCOLOREDIT、WM_CTLCOLORLISTBOX、WM_CTLCOLORMSGBOX、WM_CTLCOLORSCROLLBAR WM_CTLCOLORSTATIC を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール: Windows コントロールのサブクラス化](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)   
 [テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション (メッセージ返送)](../mfc/tn062-message-reflection-for-windows-controls.md)

