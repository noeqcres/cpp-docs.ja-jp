---
title: IDocHostUIHandlerDispatch インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
dev_langs:
- C++
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 936d9b30f18f5ef84c68c55a1607cfcd88d45525
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884614"
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch インターフェイス
Microsoft の HTML 解析およびレンダリング エンジンへのインターフェイス。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
interface IDocHostUIHandlerDispatch : IDispatch
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
> [!NOTE]
>  次の表のリンクがのメンバーの INet SDK リファレンスのトピックには、 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)インターフェイス。 `IDocHostUIHandlerDispatch` 同じ機能を持つ`IDocUIHostHandler`、いるに違い`IDocHostUIHandlerDispatch`はディスパッチ インターフェイスに対し`IDocUIHostHandler`は、カスタム インターフェイスです。  
  
|||  
|-|-|  
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|MSHTML の実装から呼び出されます[IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115)します。 MSHTML モーダル UI を表示するときとも呼ばれます。|  
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|MSHTML のデータ オブジェクトを置換するホストを許可する MSHTML によってホストで呼び出されます。|  
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|別の方法を指定するホストを許可する、ドロップ先として使用されている場合、MSHTML によって呼び出されます[IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)します。|  
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|ホストの IDispatch インターフェイスを取得する MSHTML によって呼び出されます。|  
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|MSHTML ホストの UI 機能を取得します。|  
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|MSHTML がユーザー設定を格納するレジストリ キーを返します。|  
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|MSHTML がメニューやツールバーを削除するときに呼び出されます。|  
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|MSHTML の実装から呼び出されます[::ondocwindowactivate](http://msdn.microsoft.com/library/windows/desktop/ms687281)します。|  
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|MSHTML の実装から呼び出されます[ioleinplaceactiveobject::onframewindowactivate](http://msdn.microsoft.com/library/windows/desktop/ms683969)します。|  
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|MSHTML の実装から呼び出されます[ioleinplaceactiveobject:](http://msdn.microsoft.com/library/windows/desktop/ms680053)します。|  
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|コンテキスト メニューを表示する MSHTML から呼び出されます。|  
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|MSHTML メニューおよびツールバーを置換するホストを使用します。|  
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|MSHTML によって呼び出されるときに[ioleinplaceactiveobject::translateaccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360)または[iolecontrolsite:](http://msdn.microsoft.com/library/windows/desktop/ms693756)が呼び出されます。|  
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|ホストに読み込まれる URL を変更することを許可する MSHTML によって呼び出されます。|  
|[Updateui という](https://msdn.microsoft.com/library/aa753268.aspx)|コマンドの状態が変化したことをホストに通知します。|  
  
## <a name="remarks"></a>Remarks  
 ホストは、メニューのツールバー、および Microsoft HTML 解析およびレンダリング エンジン (MSHTML) によってこのインターフェイスを実装するために使用するコンテキスト メニューに置き換えることができます。  
  
## <a name="requirements"></a>必要条件  
 このインターフェイスの定義は、次に示すように IDL または C++ では、使用可能です。  
  
|定義の種類|ファイル|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h にも含まれています)|  
  
## <a name="see-also"></a>関連項目  
 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)









