---
title: 読み取り専用プロバイダーのテスト |Microsoft Docs
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
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4e8df26063a8d854f643b78fa127d1c17ef43589
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339465"
---
# <a name="testing-the-read-only-provider"></a>読み取り専用プロバイダーのテスト
プロバイダーをテストするには、コンシューマーが必要です。 コンシューマーがプロバイダーと一致できる場合に役立ちます。 OLE DB コンシューマー テンプレートは、OLE DB の thin ラッパーでプロバイダーの COM オブジェクトと一致します。 ソースは、コンシューマー テンプレートに含まれる、ために、それらのプロバイダーのデバッグが容易になります。 コンシューマー テンプレートも非常に小さく、高速のコンシューマー アプリケーションを開発する方法。  
  
 このトピックの例では、テストのコンシューマーの MFC アプリケーション ウィザードの既定のアプリケーションを作成します。 テスト アプリケーションは、OLE DB コンシューマー テンプレート コードが追加された単純なダイアログです。  
  
### <a name="to-create-the-test-application"></a>テスト アプリケーションを作成するには  
  
1.  **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
2.  [プロジェクトの種類] ペインで、**[Visual C++ プロジェクト]** フォルダーを選択します。 [テンプレート] ペインで選択**MFC アプリケーション**します。  
  
3.  プロジェクト名を入力**TestProv**、順にクリックします**OK**します。  
  
     MFC アプリケーション ウィザードが表示されます。  
  
4.  **アプリケーションの種類**] ページで、[**ダイアログ ベース**します。  
  
5.  **高度な機能**] ページで、[ **Automation**、順にクリックします**完了**します。  
  
> [!NOTE]
>  追加する場合に、アプリケーションでオートメーションのサポートが必要ありません**CoInitialize**で**CTestProvApp::InitInstance**します。  
  
 表示および TestProv ダイアログ ボックス (IDD_TESTPROV_DIALOG) を編集するには、リソース ビューで選択することができます。 ダイアログ ボックスで、行セット内の各文字列に 1 つずつ、2 つのリスト ボックスを配置します。 並べ替えプロパティのクリックしてのリスト ボックスを選択すると、ALT + Enter を押して両方のリスト ボックスをオフにする、**スタイル**タブをクリックし、オフにすると、**並べ替え**チェック ボックスをオンします。 また、配置、**実行**ファイルをフェッチするダイアログ ボックスのボタン。 完成した TestProv ダイアログ ボックスは「文字列 1」と「2 を文字列」をそれぞれ; という 2 つのリスト ボックスが必要**OK**、**キャンセル**と**実行**ボタン。  
  
 (このケース TestProvDlg.h) で、ダイアログ クラスのヘッダー ファイルを開きます。 (、クラス宣言の外部のヘッダー ファイルに次のコードを追加します。  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// TestProvDlg.h  
  
class CProvider   
{  
// Attributes  
public:  
   char   szField1[16];  
   char   szField2[16];  
  
   // Binding Maps  
BEGIN_COLUMN_MAP(CProvider)  
   COLUMN_ENTRY(1, szField1)  
   COLUMN_ENTRY(2, szField2)  
END_COLUMN_MAP()  
};  
```  
  
 コードでは、行セット内になります列を定義するユーザー レコードを表します。 クライアントを呼び出すと`IAccessor::CreateAccessor`、これらのエントリを使用してバインドする列を指定します。 OLE DB コンシューマー テンプレートでは、列を動的にバインドすることもできます。 COLUMN_ENTRY マクロは、PROVIDER_COLUMN_ENTRY マクロのクライアント側バージョンです。 2 つの COLUMN_ENTRY マクロでは、序数、2 つの文字列型、長さ、およびデータ メンバーを指定します。  
  
 ハンドラー関数を追加、**実行**ボタンをダブルクリックして、CTRL キーを押し、**実行**ボタンをクリックします。 関数では、次のコードを配置します。  
  
```cpp
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider>> table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
      return;  
  
   while (table.MoveNext() == S_OK)  
   {  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
   }  
}  
```  
  
 `CCommand`、 `CDataSource`、および`CSession`OLE DB コンシューマー テンプレートに属しているすべてのクラス。 各クラスは、プロバイダーでの COM オブジェクトを模倣します。 `CCommand`オブジェクトは、`CProvider`クラス、テンプレート パラメーターとして、ヘッダー ファイルで宣言します。 `CProvider`パラメーターは、プロバイダーからデータにアクセスするために使用するバインドを表します。 ここでは、`Open`データ ソース、セッション、およびコマンドのコード。  
  
```cpp  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 各クラスを開く行では、プロバイダーの各 COM オブジェクトを作成します。 プロバイダーを特定するには、プロバイダーの ProgID を使用します。 ProgID を取得するには、システム レジストリからか MyProvider.rgs ファイルで (プロバイダーの ProgID のキーを検索してディレクトリを開きます)。  
  
 MyData.txt ファイルでは、MyProv サンプルに含まれています。 独自のファイルを作成するには、エディターを使用して各文字列の間で ENTER キーを押して、文字列の偶数を入力します。 ファイルを移動する場合は、パス名を変更します。  
  
 文字列を渡す"c:\\\samples\\\myprov\\\MyData.txt"で、`table.Open`行。 ステップ インする場合、`Open`にこの文字列が渡されることを確認する呼び出し、`SetCommandText`プロバイダーのメソッド。 なお、`ICommandText::Execute`メソッドは、その文字列を使用します。  
  
 データをフェッチする呼び出す`MoveNext`テーブルにします。 `MoveNext` 呼び出し、 `IRowset::GetNextRows`、 `GetRowCount`、および`GetData`関数。 これ以上の行がある場合 (つまり、行セット内の現在位置がより大きい`GetRowCount`)、ループを終了します。  
  
```cpp  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 これ以上の行が存在する場合、プロバイダーが DB_S_ENDOFROWSET を返すことに注意してください。 DB_S_ENDOFROWSET 値は、エラーではありません。 データのフェッチのループをキャンセルし、SUCCEEDED マクロを使用しない S_OK に対して常に確認する必要があります。  
  
 ビルドし、プログラムをテストできるようになりましたにします。  
  
## <a name="see-also"></a>関連項目  
 [単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)