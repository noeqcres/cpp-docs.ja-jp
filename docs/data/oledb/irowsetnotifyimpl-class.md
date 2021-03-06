---
title: IRowsetNotifyImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a20be1a92c93be38d901f58339bb02b24cf2661f
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339956"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl クラス
実装し、登録[IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx)コンシューマー (別名「シンク」) の通知を処理できるようにします。  
  
## <a name="syntax"></a>構文

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[OnFieldChange](#onfieldchange)|列の値の変更をコンシューマーに通知します。|  
|[OnRowChange](#onrowchange)|最初の行を変更または行全体に影響する変更のコンシューマーに通知します。|  
|[OnRowsetChange](#onrowsetchange)|行セット全体に影響を与える変更をコンシューマーに通知します。|  
  
## <a name="remarks"></a>Remarks  
 参照してください[通知の受信](../../data/oledb/receiving-notifications.md)コンシューマーのコネクション ポイントのインターフェイスを実装する方法。  
  
 `IRowsetNotifyImpl` ダミー実装を提供`IRowsetNotify`、空の関数を含む、`IRowsetNotify`メソッド[OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx)、 [OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx)、および[OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx). 実装する場合、このクラスから継承する場合、`IRowsetNotify`インターフェイスに必要なメソッドのみを実装することができます。 また、自分でその他のメソッドの空の実装を提供する必要があります。  

## <a name="onfieldchange"></a> Irowsetnotifyimpl::onfieldchange
列の値の変更をコンシューマーに通知します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(OnFieldChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ HROW /* hRow */,  
/* [in] */ DBORDINAL /* cColumns */,  
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](https://msdn.microsoft.com/library/ms715961.aspx)のパラメーターの説明。  
  
### <a name="return-value"></a>戻り値  
 参照してください[は、](https://msdn.microsoft.com/library/ms715961.aspx)値の説明を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドはラップ、[は、](https://msdn.microsoft.com/library/ms715961.aspx)メソッド。 詳細については、OLE DB プログラマーズ リファレンス、そのメソッドの説明を参照してください。  

## <a name="onrowchange"></a> Irowsetnotifyimpl::onrowchange
最初の行を変更または行全体に影響する変更のコンシューマーに通知します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(OnRowChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBCOUNTITEM /* cRows */,  
/* [size_is][in] */ const HROW /* rghRows*/ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](https://msdn.microsoft.com/library/ms722694.aspx)のパラメーターの説明。  
  
### <a name="return-value"></a>戻り値  
 参照してください[は、](https://msdn.microsoft.com/library/ms722694.aspx)値の説明を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドはラップ、[は、](https://msdn.microsoft.com/library/ms722694.aspx)メソッド。 詳細については、OLE DB プログラマーズ リファレンス、そのメソッドの説明を参照してください。 

## <a name="onrowsetchange"></a> Irowsetnotifyimpl::onrowsetchange
行セット全体に影響を与える変更をコンシューマーに通知します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(OnRowsetChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](https://msdn.microsoft.com/library/ms722669.aspx)のパラメーターの説明。  
  
### <a name="return-value"></a>戻り値  
 参照してください[は、](https://msdn.microsoft.com/library/ms722669.aspx)値の説明を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドはラップ、[は、](https://msdn.microsoft.com/library/ms722669.aspx)メソッド。 詳細については、OLE DB プログラマーズ リファレンス、そのメソッドの説明を参照してください。
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx)   
 [IRowsetNotifyCP クラス](../../data/oledb/irowsetnotifycp-class.md)