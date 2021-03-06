---
title: CComSimpleThreadAllocator クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2c571733aca48ddbfd881a294786d1de334c7c3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884666"
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator クラス
このクラスは、クラスのスレッドの選択を管理`CComAutoThreadModule`します。  
  
## <a name="syntax"></a>構文  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|スレッドを選択します。|  
  
## <a name="remarks"></a>Remarks  
 `CComSimpleThreadAllocator` スレッドの選択を管理[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。 `CComSimpleThreadAllocator::GetThread` 単に各スレッドが繰り返しし、シーケンス内の次の 1 つ返されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
  
##  <a name="getthread"></a>  CComSimpleThreadAllocator::GetThread  
 シーケンス内の次のスレッドを指定することによって、スレッドを選択します。  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>パラメーター  
 *pApt*  
 ATL の既定の実装では使用されません。  
  
 *nThreads*  
 EXE モジュール内のスレッドの最大数。  
  
### <a name="return-value"></a>戻り値  
 0 までの整数と (*nThreads* - 1)。 EXE モジュール内のスレッドのいずれかを識別します。  
  
### <a name="remarks"></a>Remarks  
 オーバーライドできます`GetThread`選択範囲のさまざまなメソッドを提供したりの使用、 *pApt*パラメーター。  
  
 `GetThread` によって呼び出される[CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance)します。  
  
## <a name="see-also"></a>関連項目  
 [CComApartment クラス](../../atl/reference/ccomapartment-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
