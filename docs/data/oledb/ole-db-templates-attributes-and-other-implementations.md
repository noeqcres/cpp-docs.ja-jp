---
title: OLE DB テンプレート、属性、およびその他の実装 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 32d9356c5c223df723626cf6ac07a7b5fda368de
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340652"
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>OLE DB テンプレート、属性、およびその他の実装
## <a name="atl-ole-db-templates"></a>ATL OLE DB テンプレート  
 OLE DB テンプレート、ATL (Active Template Library) の一部である、高性能な OLE DB のデータベース テクノロジを使いやすく、一般的に使用される OLE DB インターフェイスの多くを実装するクラスを提供することで。 このテンプレートと共にライブラリは、OLE DB のスターター アプリケーションを作成するためのウィザード サポートです。  
  
 このテンプレート ライブラリには、2 つの部分が含まれています。  
  
-   **OLE DB コンシューマー テンプレート**OLE DB (コンシューマー) のクライアント アプリケーションを実装するために使用します。  
  
-   **OLE DB プロバイダー テンプレート**OLE DB サーバー (プロバイダー) アプリケーションを実装するために使用します。  
  
 OLE DB テンプレートを使用するには、C++ テンプレート、COM、および OLE DB インターフェイスに関する知識が必要です。 OLE DB に慣れていない場合は、次を参照してください。 [OLE DB プログラマーズ リファレンス](https://msdn.microsoft.com/library/ms713643.aspx)します。  
  
 詳細については、次の操作を実行できます。  
  
-   に関するトピックを参照して、 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)または[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)します。  
  
-   作成、 [OLE DB コンシューマー](../../data/oledb/creating-an-ole-db-consumer.md)または[OLE DB プロバイダー](../../data/oledb/creating-an-ole-db-provider.md)します。  
  
-   一覧を参照してください。 [OLE DB コンシューマー クラス](../../data/oledb/ole-db-consumer-templates-reference.md)または[OLE DB プロバイダー クラス](../../data/oledb/ole-db-provider-templates-reference.md)します。  
  
-   一覧を参照してください。 [OLE DB テンプレート サンプル](http://msdn.microsoft.com/08958863-0b5f-41ad-ae99-fca7440c553c)します。  
  
-   参照してください[OLE DB プログラマーズ リファレンス](https://msdn.microsoft.com/library/ms713643.aspx)(、Windows SDK) にします。  
  
## <a name="ole-db-attributes"></a>OLE DB 属性します。  
 [OLE DB コンシューマー属性](../../windows/ole-db-consumer-attributes.md)OLE DB コンシューマーを作成する便利な手段を提供します。 OLE DB 属性に基づくコードの挿入、 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-reference.md)して OLE DB コンシューマーとプロバイダーを作成します。 属性でサポートされていない機能を指定する必要がある場合は、コードで属性と組み合わせて OLE DB テンプレートを使用することができます。  
  
## <a name="mfc-ole-db-classes"></a>MFC の OLE DB クラス  
 MFC ライブラリの 1 つのクラス ライブラリが[COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)コントロールでのデータベース レコードを表示します。 ビューが、フォーム ビューに直接接続されている、`CRowset`オブジェクトし、のフィールドが表示されます、`CRowset`ダイアログ テンプレートのコントロール内のオブジェクト。 移動するための既定の実装も提供に、最初次、前、または最後のレコードとインターフェイス ビューで現在のレコードを更新します。 詳細については、「`COleDBRecordView`」を参照してください。  
  
## <a name="ole-db-sdk-interfaces"></a>OLE DB SDK インターフェイス  
 OLE DB テンプレートと OLE DB 機能がサポートして場合、OLE DB インターフェイス自体を使用する必要があります。 詳細については、次を参照してください。 [OLE DB プログラマーズ リファレンス](https://msdn.microsoft.com/library/ms713643.aspx)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)