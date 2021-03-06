---
title: IDBSchemaRowsetImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
dev_langs:
- C++
helpviewer_keywords:
- IDBSchemaRowsetImpl class
- CheckRestrictions method
- CreateSchemaRowset method
- SetRestrictions method
- GetRowset method
- GetSchemas method
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eaea6922f7755295535c0e81d6b9023a10c1317a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339615"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl クラス
スキーマ行セットの実装を提供します。  
  
## <a name="syntax"></a>構文

```cpp
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
### <a name="parameters"></a>パラメーター  
 *SessionClass*  
 `IDBSchemaRowsetImpl` が継承されるクラス。 通常、このクラスは、ユーザーのセッション クラスです。 

## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CheckRestrictions](#checkrestrictions)|スキーマ行セットに対して制限の妥当性をチェックします。|  
|[CreateSchemaRowset](#createschemarowset)|テンプレート パラメーターで指定されたオブジェクトの COM オブジェクトの作成関数を実装します。|  
|[SetRestrictions](#setrestrictions)|特定のスキーマ行セットでサポートする制限を指定します。|  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetRowset](#getrowset)|スキーマ行セットを返します。|  
|[GetSchemas](#getschemas)|[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)でアクセスできるスキーマ行セットの一覧を返します。|  
  
## <a name="remarks"></a>Remarks  
 このクラスは、実装、 [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)インターフェイスと、テンプレート化された作成関数[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)します。  
  
 OLE DB はスキーマ行セットを使用して、プロバイダーのデータに関するデータを返します。 このようなデータは、多くの場合、"メタデータ" と呼ばれます。 既定では、プロバイダーをサポートする必要があります常に`DBSCHEMA_TABLES`、 `DBSCHEMA_COLUMNS`、および`DBSCHEMA_PROVIDER_TYPES`」の説明に従って、 [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 スキーマ行セットはスキーマ マップで指定します。 スキーマ マップ エントリの詳細については、「 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)」を参照してください。  
  
 ATL オブジェクト ウィザードの OLE DB プロバイダー ウィザードでは、プロジェクトのスキーマ行セットのコードが自動的に生成されます (既定では、ウィザードは、以前説明した必須のスキーマ行セットをサポートしています)。ATL オブジェクト ウィザードでコンシューマーを作成すると、スキーマ行セットで正しいデータがプロバイダーにバインドされます。 正しいメタデータを提供するようにスキーマ行セットを実装していないと、正しいデータがバインドされません。  
  
 プロバイダーでスキーマ行セットをサポートする方法については、「 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)」を参照してください。  
  
 スキーマ行セットの詳細については、次を参照してください。[スキーマ行セット](https://msdn.microsoft.com/library/ms712921.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="checkrestrictions"></a> Idbschemarowsetimpl::checkrestrictions
スキーマ行セットに対して制限の妥当性をチェックします。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT CheckRestrictions(REFGUID rguidSchema,  
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rguidSchema*  
 [入力] 要求するスキーマ行セット GUID ( `DBSCHEMA_TABLES`など) への参照。  
  
 *cRestrictions*  
 [入力] コンシューマーがスキーマ行セットに渡した制限の数。  
  
 *で*  
 [入力] 設定する制限値の長さ *cRestrictions* の配列。 詳細については、の説明を参照して、*で*パラメーター [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)します。  
  
### <a name="remarks"></a>Remarks  
 `CheckRestrictions` を使用して、スキーマ行セットに対して制限の妥当性をチェックします。 適用される制限事項を確認します`DBSCHEMA_TABLES`、 `DBSCHEMA_COLUMNS`、および`DBSCHEMA_PROVIDER_TYPES`スキーマ行セット。 コンシューマーの場合を判断するために呼び出しを呼び出す`IDBSchemaRowset::GetRowset`が正しい。 上記以外のスキーマ行セットをサポートする場合は、このタスクを実行する独自の関数を作成する必要があります。  
  
 `CheckRestrictions` コンシューマーが呼び出すかどうかを決定します[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)正しい制限および制限の種類 (たとえば、文字列を VT_BSTR) プロバイダーがサポートするとします。 また、正しい制限数がサポートされているかどうかも判断します。 `CheckRestrictions` は、既定で [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) 呼び出しを通じて、任意の行セットについてプロバイダーがサポートしている制限の種類を確認します。 次に、コンシューマーが呼び出した制限とプロバイダーがサポートしている制限を比較することで、処理は成功または失敗します。  
  
 スキーマ行セットの詳細については、次を参照してください。 [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK に含まれています。  

## <a name="createschemarowset"></a> Idbschemarowsetimpl::createschemarowset
テンプレート パラメーターで指定されたオブジェクトの COM オブジェクトの作成関数を実装します。  
  
### <a name="syntax"></a>構文  
  
```cpp
template template <class SchemaRowsetClass>  
HRESULT CreateSchemaRowset(IUnknown *pUnkOuter,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   SchemaRowsetClass*& pSchemaRowset);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pUnkOuter*  
 [in]外部[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 、それ以外の場合 NULL を集計するときにします。  
  
 *cRestrictions*  
 [入力] スキーマ行セットに適用する制限の数。  
  
 *で*  
 [入力] 行セットに適用する `cRestrictions`**VARIANT**の配列。  
  
 *riid*  
 [in]インターフェイスを[QueryInterface](../../atl/queryinterface.md)の出力に`IUnknown`します。  
  
 *cPropertySets*  
 [入力] 設定するプロパティ セットの数。  
  
 *rgPropertySets*  
 [in]配列の[DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx)設定されているプロパティを指定する構造体。  
  
 *ppRowset*  
 [out]送信`IUnknown`によって要求された*riid*します。 これは、`IUnknown`は、スキーマ行セット オブジェクトのインターフェイスです。  
  
 *pSchemaRowset*  
 [出力] スキーマ行セット クラスのインスタンスへのポインター。 通常、このパラメーターは使用されません。使用できるのは、スキーマ行セットを COM オブジェクトに渡す前に、その行セットで多くの作業を実行する必要があるときです。 有効期間*pSchemaRowset*連結された*ppRowset*します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 この関数は、あらゆる種類のスキーマ行セットに対する汎用作成関数を実装します。 通常、この関数は、ユーザーからは呼び出されません。 これはスキーマ マップの実装によって呼び出されます。 

## <a name="setrestrictions"></a> Idbschemarowsetimpl::setrestrictions
特定のスキーマ行セットでサポートする制限を指定します。  
  
### <a name="syntax"></a>構文  
  
```cpp
void SetRestrictions(ULONG cRestrictions,  
   GUID* /* rguidSchema */,  
   ULONG* rgRestrictions);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *cRestrictions*  
 [in]制限の数、*で*配列と Guid の番号、 *rguidSchema*配列。  
  
 *rguidSchema*  
 [入力] 制限をフェッチするスキーマ行セットの GUID の配列。 配列の各要素は、1 つのスキーマ行セットの GUID ( `DBSCHEMA_TABLES`など) を保持します。  
  
 *で*  
 [入力] 設定する制限値の長さ *cRestrictions* の配列。 各要素は、GUID によって識別されるスキーマ行セットの制限に対応します。 スキーマ行セットがプロバイダーによってサポートされていない場合、その要素は 0 に設定されます。 それ以外の場合、 **ULONG** 値は、そのスキーマ行セットでサポートされている制限を表すビット マスクを保持します。 特定のスキーマ行セットに対応する制限の詳細については、スキーマ行セット Guid の表を参照してくださいで[IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows でSDK があります。  
  
### <a name="remarks"></a>Remarks  
 `IDBSchemaRowset`オブジェクト呼び出し`SetRestrictions`で特定のスキーマ行セットをサポートする制限を判断する (を呼び出して[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)アップ キャストされたポインターを通じて)。 制限により、コンシューマーは一致する行だけをフェッチできます (たとえば、テーブル "MyTable" 内のすべての列を検索します)。 制限は省略可能であり、制限がサポートされていない場合 (既定)、常にすべてのデータが返されます。  
  
 このメソッドの既定の実装の設定、*で*配列の要素が 0 にします。 既定以外の制限を設定する場合は、セッション クラスで既定値をオーバーライドします。  
  
 スキーマ行セットのサポートの実装については、「 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)」を参照してください。  
  
 スキーマ行セットをサポートするプロバイダーの例については、 [UpdatePV](../../visual-cpp-samples.md) サンプルを参照してください。  
  
 スキーマ行セットの詳細については、次を参照してください。 [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK に含まれています。 
  
## <a name="getrowset"></a> Idbschemarowsetimpl::getrowset
スキーマ行セットを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetRowset)(IUnknown *pUnkOuter,  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown **ppRowset);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pUnkOuter*  
 [in]外部`IUnknown`集計は NULL それ以外の場合とします。  
  
 *rguidSchema*  
 [入力] 要求するスキーマ行セット GUID ( `DBSCHEMA_TABLES`など) への参照。  
  
 *cRestrictions*  
 [入力] 行セットに適用する制限の数。  
  
 *で*  
 [入力] 制限を表す `cRestrictions`**VARIANT**の配列。  
  
 *riid*  
 [入力] 新しく作成されたスキーマ行セットに対して要求する IID。  
  
 *cPropertySets*  
 [入力] 設定するプロパティ セットの数。  
  
 *rgPropertySets*  
 [入力/出力]配列の[DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx)構造を新しく作成されたスキーマ行セットに対して設定します。  
  
 *ppRowset*  
 [出力] 新しく作成されたスキーマ行セットに対して要求するインターフェイスへのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用するには、ユーザーはセッション クラスにスキーマ マップを持っている必要があります。 スキーマ マップ情報を使用して`GetRowset`特定の行セット オブジェクトを作成する場合、 *rguidSchema*パラメーターが 1 つのマップ エントリの Guid に等しい。 マップ エントリについては、「 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) 」を参照してください。  
  
 参照してください[idbschemarowset::getrowset](https://msdn.microsoft.com/library/ms722634.aspx) Windows SDK にします。  

## <a name="getschemas"></a> Idbschemarowsetimpl::getschemas
[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)でアクセスできるスキーマ行セットの一覧を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetSchema s )(ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pcSchemas*  
 [出力] スキーマの数が格納される **ULONG** へのポインター。  
  
 *prgSchemas*  
 [出力] スキーマ行セット GUID の配列へのポインターが格納される GUID の配列へのポインター。  
  
 *prgRest*  
 [出力] 制限配列が格納される **ULONG**の配列へのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、プロバイダーによってサポートされるすべてのスキーマ行セットの配列を返します。 参照してください[idbschemarowset::getschemas](https://msdn.microsoft.com/library/ms719605.aspx) Windows SDK にします。  
  
 この関数の実装では、セッション クラスでスキーマ マップを持っている必要があります。 スキーマ マップ情報を使用して、マップ内のスキーマの GUID の配列で応答します。 これは、プロバイダーによってサポートされるスキーマを表します。  

## <a name="see-also"></a>関連項目  
 [IDBSchemaRowsetImpl クラス メンバー](http://msdn.microsoft.com/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)    
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)    
 [UpdatePV](../../visual-cpp-samples.md)