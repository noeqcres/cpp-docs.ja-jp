---
title: レコード ビュー (MFC データ アクセス) のデータ交換 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 58bda2d9a712e38951b8201c08e5bbbe369537eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089416"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>レコード ビューのデータ交換 (MFC データ アクセス)
使用すると[クラスの追加](../mfc/reference/adding-an-mfc-odbc-consumer.md)フレームワークをレコード ビューのダイアログ テンプレート リソース内のコントロールをレコード セットのフィールドをマップするには、双方向のデータ交換を管理する: レコード セットとコントロールとレコード セットへのコントロールからです。 DDX 機構を使用すると、データを双方向で転送するコードを自分で記述する必要がなくなります。  
  
 レコード ビューの DDX はと共に動作[RFX](../data/odbc/record-field-exchange-rfx.md)クラスのレコード セット`CRecordset`(ODBC)。  Rfx 関数は、データ ソースの現在のレコードと、レコード セット オブジェクトのフィールド データ メンバーの間でデータを移動します。 DDX は、フィールド データ メンバーからフォーム内のコントロールにデータを移動します。 このように組み合わせると、フォーム コントロールに初期値が設定され、ユーザーがレコード間を移動したときにも値が設定されます。 更新されたデータをレコードセットに戻し、さらにデータ ソースまで移動することもできます。  
  
 次の図は、レコード ビュー用の DDX と RFX の間でリレーションシップを示します。  
  
 ![ダイアログ&#45;データ エクス チェンジとレコード&#45;フィールド エクス チェンジ](../data/media/vc37xt1.gif "vc37xt1")  
ダイアログ データ エクスチェンジ (DDX) とレコード フィールド エクスチェンジ (RFX)  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。 RFX の詳細については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../data/odbc/record-field-exchange-rfx.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)