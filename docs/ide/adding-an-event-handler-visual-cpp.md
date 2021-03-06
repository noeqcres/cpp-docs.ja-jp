---
title: イベント ハンドラーの追加 (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 184161b22358f77845b5f7c4b6da0bb42f3ea15f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33324916"
---
# <a name="adding-an-event-handler-visual-c"></a>イベント ハンドラーの追加 (Visual C++)
リソース エディターで、[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)を使用するダイアログ ボックス コントロールで新しいイベント ハンドラーを追加したり、既存のイベント ハンドラーを編集したりできます。  
  
 [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)を使用すると、ダイアログ ボックスが実装されているクラスにイベントを追加できます。 ダイアログ ボックス クラス以外のクラスにイベントを追加する場合は、イベント ハンドラー ウィザードを使用します。  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>ダイアログ ボックス コントロールにイベント ハンドラーを追加するには  
  
1.  [[リソース ビュー]](../windows/resource-view-window.md) のダイアログ ボックス リソースをダブルクリックして、[ダイアログ エディター](../windows/dialog-editor.md)のコントロールが含まれるダイアログ ボックス リソースを開きます。  
  
2.  通知イベントを処理するコントロールを右クリックします。  
  
3.  ショートカット メニューの **[イベント ハンドラーの追加]** をクリックして、イベント ハンドラー ウィザードを表示します。  
  
4.  **[メッセージの種類]** ボックスでイベントを選択し、**[クラス] リスト** ボックスで選択されたクラスを追加します。  
  
5.  **[Function handler name]\(関数ハンドラー名\)** ボックスの既定の名前を受け入れるか、任意の名前を指定します。  
  
6.  **[Add and edit]\(追加と編集\)** をクリックして、プロジェクトにイベント ハンドラーを追加し、新しい関数に対してテキスト エディターを開き、適切なイベント ハンドラーのコードを追加します。  
  
     選択したメッセージの種類に選択したクラスのイベント ハンドラーが既にある場合、**[Add and edit]\(追加と編集\)** は使用できず、**[コードの編集]** を使用する必要があります。 **[コードの編集]** をクリックして、既存の関数に対してテキスト エディターを開きます。  
  
 または、[[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)からイベント ハンドラーを追加することも可能です。 詳細については、「[ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../ide/adding-a-class-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)