---
title: CSettingsStoreSP クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cf84e2e7db6f829cb7afcd1831521b4f94535bd
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850784"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP クラス
`CSettingsStoreSP`クラスは、インスタンスの作成に使用できるヘルパー クラス、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|`CSettingsStoreSP` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|派生したクラスのインスタンスを作成します`CSettingsStore`します。|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|ランタイム クラスを設定します。 `Create`メソッドはランタイム クラスを使用して作成するオブジェクトのクラスを決定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|`m_dwUserData`|カスタム ユーザー データに格納されている、`CSettingsStoreSP`オブジェクト。 コンス トラクターでは、このデータを指定する、`CSettingsStoreSP`オブジェクト。|  
|`m_pRegistry`|`CSettingsStore`の派生オブジェクトを`Create`メソッドを作成します。|  
  
## <a name="remarks"></a>Remarks  
 使用することができます、 `CSettingsStoreSP` MFC レジストリのすべての操作を XML ファイルやデータベースなどの他の場所にリダイレクトするクラス。 その場合は、次の手順を実行します。  
  
1.  クラスを作成 (など`CMyStore`) から派生させます`CSettingsStore`します。  
  
2.  使用[DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)と[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)マクロは、カスタムで`CSettingsStore`動的な作成を有効にするクラス。  
  
3.  仮想関数をオーバーライドし、実装、`Read`と`Write`カスタム クラスの関数。 目的の場所にデータを読み書きする他の機能を実装します。  
  
4.  アプリケーションでは、呼び出す`CSettingsStoreSP::SetRuntimeClass`へのポインターを渡すと、 [CRuntimeClass 構造](../../mfc/reference/cruntimeclass-structure.md)クラスから取得します。  
  
 フレームワークは通常、レジストリ アクセス、たびにようになりました動的にカスタム クラスをインスタンス化され読み取りまたは書き込みに使用します。  
  
 `CSettingsStoreSP::SetRuntimeClass` グローバルな静的変数を使用します。 そのため、1 つだけのカスタム ストアは、時に使用できます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxsettingsstore.h  
  
##  <a name="create"></a>  CSettingsStoreSP::Create  
 派生したオブジェクトの新しいインスタンスを作成、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)します。  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bAdmin*  
 決定するブール値パラメーターかどうかを`CSettingsStore`管理者モードでオブジェクトを作成します。  
  
 [in]*bReadOnly*  
 決定するブール値パラメーターかどうかを`CSettingsStore`読み取り専用アクセスのオブジェクトを作成します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたへの参照を`CSettingsStore`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 メソッドを使用する[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)オブジェクトの種類を決定する`CSettingsStoreSP::Create`が作成されます。 既定では、このメソッドを作成、`CSettingsStore`オブジェクト。  
  
 作成する場合、`CSettingsStore`管理者モードでオブジェクトのすべてのレジストリへのアクセスの既定の場所は HKEY_LOCAL_MACHINE。 それ以外の場合、レジストリへのアクセスはすべての既定の場所は、HKEY_CURRENT_USER です。  
  
 場合*bAdmin*が true の場合、アプリケーションは、管理権限を持って必要があります。 それ以外の場合、レジストリのアクセスを試行するときに失敗になります。  
  
### <a name="example"></a>例  
 次の例では、使用する方法、`Create`のメソッド、`CSettingsStoreSP`クラス。  
  
 [!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="csettingsstoresp"></a>  CSettingsStoreSP::CSettingsStoreSP  
 構築、 [CSettingsStoreSP クラス](../../mfc/reference/csettingsstoresp-class.md)オブジェクト。  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwUserData*  
 ユーザー定義データを`CSettingsStoreSP`オブジェクト ストアです。  
  
### <a name="remarks"></a>Remarks  
 `CSettingsStoreSP`オブジェクトからデータを格納する*dwUserData*プロテクト メンバー変数に`m_dwUserData`します。  
  
##  <a name="setruntimeclass"></a>  CSettingsStoreSP::SetRuntimeClass  
 ランタイム クラスを設定します。 メソッド[CSettingsStoreSP::Create](#create)ランタイム クラスを使用して作成するオブジェクトの種類を決定します。  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pRTI*  
 派生したクラスのランタイム クラス情報へのポインター、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE。FALSE の場合、クラスがで識別される*pRTI*から派生していない`CSettingsStore`します。  
  
### <a name="remarks"></a>Remarks  
 使用することができます、 [CSettingsStoreSP クラス](../../mfc/reference/csettingsstoresp-class.md)からクラスを派生する`CSettingsStore`します。 メソッドを使用して`SetRuntimeClass`から派生したカスタム クラスのオブジェクトを作成したいかどうか`CSettingsStore`します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)
