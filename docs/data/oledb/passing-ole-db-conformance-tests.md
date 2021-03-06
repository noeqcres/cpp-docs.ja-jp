---
title: OLE DB 準拠合致テストに合格 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0288e1517bf89ec6ff8a2067311c3641d8d7113c
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340917"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB 準拠合致テスト
プロバイダーはより一貫性のあるは、データ アクセスの SDK は、OLE DB 準拠合致テストのセットを提供します。 テストは、プロバイダーのすべての側面を確認し、こととして、プロバイダーの関数が想定されている妥当な保証を提供します。 Microsoft Data Access SDK では、OLE DB 準拠合致テストを確認できます。 このセクションでは、必要な手順への準拠テストに合格するについて説明します。 OLE DB 準拠合致テストの実行方法の詳細については、SDK を参照してください。  
  
## <a name="running-the-conformance-tests"></a>準拠テストを実行します。  
 Visual C 6.0 では、OLE DB プロバイダー テンプレートは、多数の値とプロパティを確認するためのフック関数を追加します。 これらの関数のほとんどは、準拠合致テストへの応答に追加されました。  
  
> [!NOTE]
>  OLE DB 準拠のテストに合格する、プロバイダーのいくつかの検証機能を追加する必要があります。  
  
 このプロバイダーでは、2 つの検証ルーチンが必要です。 最初のルーチン`CRowsetImpl::ValidateCommandID`は、行セット クラスの一部です。 プロバイダー テンプレートによって、行セットの作成時に呼び出されます。 このサンプルでは、このルーチンを使用してインデックスがサポートされていないことをコンシューマーに通知します。 最初の呼び出しが、 `CRowsetImpl::ValidateCommandID` (注、プロバイダーで使用される、`_RowsetBaseClass`に対するインターフェイス マップに追加された typedef`CMyProviderRowset`で[プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)テンプレートの長い行を入力する必要はありませんので、引数)。 Index パラメーターが NULL でない場合、次に、DB_E_NOINDEX を返します (コンシューマーが私たちのインデックスを使用することを示します)。 コマンド Id の詳細については、OLE DB 仕様を参照してくださいし、探して`IOpenRowset::OpenRowset`します。  
  
 次のコードは、`ValidateCommandID`検証ルーチン。  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)  
{  
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);  
   if (hr != S_OK)  
      return hr;  
  
   if (pIndexID != NULL)  
      return DB_E_NOINDEX;    // Doesn't support indexes  
  
   return S_OK;  
}  
```  
  
 プロバイダー テンプレートの呼び出し、`OnPropertyChanged`メソッドでプロパティが変更されるたびに、`DBPROPSET_ROWSET`グループ。 適切なオブジェクトに追加の他のグループのプロパティを処理する場合 (つまり、`DBPROPSET_SESSION`チェックが移動、`CMyProviderSession`クラス)。  
  
 コードは、まず、プロパティを別にリンクされているかどうかを確認します。 プロパティがチェーンされている場合、設定、`DBPROP_BOOKMARKS`プロパティを True にします。 OLE DB 仕様の「付録 C には、プロパティに関する情報が含まれていますいます。 この情報も示しますプロパティがもう 1 つにチェーンされているかどうか。  
  
 追加することも、`IsValidValue`ルーチンをコードにします。 テンプレートの呼び出し`IsValidValue`プロパティを設定しようとしています。 プロパティ値を設定するときに、追加の処理を必要とする場合は、このメソッドをオーバーライドします。 プロパティ セットごとにこれらのメソッドのいずれかがあることができます。  
  
## <a name="threading-issues"></a>スレッド処理の問題  
 既定では、OLE DB プロバイダー ウィザード ATL OLE DB プロバイダー ウィザードでは、アパートメント モデルで実行するプロバイダーのコードを生成します。 準拠合致テストでこのコードを実行しようとすると、最初にエラーが表示されます。 これは Ltm.exe、OLE DB 準拠合致テストを実行するために使用するツールの既定値を解放するため、スレッドします。 コードを OLE DB プロバイダー ウィザードでは、アパートメント モデルのパフォーマンスと使いやすさを既定値です。  
  
 この問題を解決するには、LTM を変更するか、プロバイダーを変更します。  
  
#### <a name="to-change-ltm-to-run-in-apartment-threaded-mode"></a>モードをスレッド アパートメントで実行する LTM を変更するには  
  
1.  LTM のメイン メニューで、次のようにクリックします。**ツール**、 をクリックし、**オプション**します。  
  
2.  **全般**からスレッド処理モデルの変更 タブで、**空きスレッド**に**Apartment Threaded**します。  
  
 空きスレッド モードで実行するには、プロバイダーを変更するには。  
  
-   プロバイダー プロジェクト内のすべてのインスタンスを検索します。`CComSingleThreadModel`置き換えます`CComMultiThreadModel`、、データ ソース、セッション、および行セットのヘッダーにある必要があります。  
  
-   .Rgs ファイルで変更からスレッド モデル**アパートメント**に**両方**します。  
  
-   フリー スレッドのプログラミング (つまり、書き込み時にロック) の規則に従って適切なプログラミングします。  
  
## <a name="see-also"></a>関連項目  
 [高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)