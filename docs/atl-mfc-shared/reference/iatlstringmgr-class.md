---
title: IAtlStringMgr クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a69b2667b92b27f7310bbc70087331acd4aefaa5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880649"
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr クラス
このクラスにインターフェイスを表します、`CStringT`メモリ マネージャー。  
  
## <a name="syntax"></a>構文  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[割り当てる](#allocate)|新しい文字列データ構造を割り当てるには、このメソッドを呼び出します。|  
|[Clone](#clone)|別のインスタンスで使用するための新しい文字列マネージャーへのポインターを返すには、このメソッドを呼び出す`CSimpleStringT`します。|  
|[無料](#free)|文字列データの構造体を解放するには、このメソッドを呼び出します。|  
|[GetNilString](#getnilstring)|ポインターを返します、`CStringData`空の文字列オブジェクトによって使用されるオブジェクト。|  
|[再割り当てください。](#reallocate)|文字列データの構造を再割り当てするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスは、MFC に依存しない文字列クラスで使用されるメモリを管理します。など[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)、 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、および[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)します。  
  
 カスタムの文字列クラスのカスタム メモリ マネージャーを実装するために、このクラスを使用することもできます。 詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlsimpstr.h  
  
##  <a name="allocate"></a>  IAtlStringMgr::Allocate  
 新しい文字列のデータ構造体を割り当てます。  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nAllocLength*  
 新しいメモリ ブロック内の文字の数。  
  
 *nCharSize*  
 文字列マネージャーによって使用される文字型のサイズをバイト単位で。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
> [!NOTE]
>  例外をスローして失敗した割り当てを通知できません。 代わりに、NULL を返すことによって、失敗した割り当てを通知する必要があります。  
  
### <a name="remarks"></a>Remarks  
 呼び出す[IAtlStringMgr::Free](#free)または[IAtlStringMgr::ReAllocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="clone"></a>  IAtlStringMgr::Clone  
 別のインスタンスで使用するための新しい文字列マネージャーへのポインターを返します`CSimpleStringT`します。  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>戻り値  
 コピーを返します、`IAtlStringMgr`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 新しい文字列の文字列のマネージャーが必要なときにフレームワークによって呼び出さ一般的です。 ほとんどの場合、**この**ポインターが返されます。  
  
 ただし、メモリ マネージャーでの複数のインスタンスで使用されているがサポートされていない場合`CSimpleStringT`、共有可能な文字列のマネージャーへのポインターが返される必要があります。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="free"></a>  IAtlStringMgr::Free  
 文字列データの構造体を解放します。  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pData*  
 解放するメモリ ブロックへのポインター。  
  
### <a name="remarks"></a>Remarks  
 割り当てられている指定されたメモリ ブロックを解放[Allocate](#allocate)または[再割り当て](../../atl/reference/iatlmemmgr-class.md#reallocate)します。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="getnilstring"></a>  IAtlStringMgr::GetNilString  
 空の文字列の文字列データの構造体へのポインターを返します。  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CStringData`オブジェクトが空の文字列を表すために使用します。  
  
### <a name="remarks"></a>Remarks  
 この関数では、空の文字列表現を返します。  
  
> [!NOTE]
>  カスタム文字列マネージャーを実装するときにこの関数が失敗しない必要があります。 インスタンスを埋め込むことでこのことを確認できる`CNilStringData`文字列マネージャーのクラスとそのインスタンスへのポインターを返す。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="reallocate"></a>  IAtlStringMgr::Reallocate  
 文字列データの構造を再割り当ています。  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pData*  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
 *nAllocLength*  
 新しいメモリ ブロック内の文字の数。  
  
 *nCharSize*  
 文字列マネージャーによって使用される文字型のサイズをバイト単位で。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>Remarks  
 指定された既存のメモリ ブロックのサイズを変更するには、この関数を呼び出す*pData*します。  
  
 呼び出す[IAtlStringMgr::Free](#free)このメソッドによって割り当てられたメモリを解放します。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)


