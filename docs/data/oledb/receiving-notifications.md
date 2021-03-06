---
title: 通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fdef616456b98086bf9490297d68c98596b2dca4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338971"
---
# <a name="receiving-notifications"></a>通知の受信
OLE DB は、イベントが発生したときに通知を受信するためのインターフェイスを提供します。 後述[OLE DB オブジェクト通知](https://msdn.microsoft.com/library/ms725406.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 これらのイベントのセットアップでは、標準の COM 接続ポイントのメカニズムを使用します。 を介してイベントを取得する必要がある ATL オブジェクトなど、`IRowsetNotify`実装、`IRowsetNotify`インターフェイスを追加して`IRowsetNotify`クラスから派生したリストし、COM_INTERFACE_ENTRY マクロを通じて公開します。  
  
 `IRowsetNotify` さまざまな時点で呼び出すことができる、3 つのメソッドがあります。 これらのメソッドの 1 つだけに応答する場合は、使用、 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)クラスに興味がないメソッドの E_NOTIMPL を返します。  
  
 行セットを作成するときにする必要がありますプロバイダーに指示するサポートするために、返された行セット オブジェクト`IConnectionPointContainer`通知の設定が必要です。  
  
 次のコードは、ATL オブジェクトから行セットを開き、使用する方法、`AtlAdvise`通知シンクを設定する関数。 `AtlAdvise` 呼び出すときに使用されるクッキーを返します`AtlUnadvise`します。  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)