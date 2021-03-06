---
title: _com_error::ErrorMessage |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9367e92110ba7fb232e89b9d950e491e5e8da5c7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407170"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Microsoft 固有の仕様**  
  
 `_com_error` オブジェクトに格納された HRESULT の文字列メッセージを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
const TCHAR * ErrorMessage( ) const throw( );  
```  
  
## <a name="return-value"></a>戻り値  
 内に記録された HRESULT の文字列メッセージを返します、`_com_error`オブジェクト。 HRESULT がマップされた 16 ビット[wCode](../cpp/com-error-wcode.md)、汎用メッセージでは、"`IDispatch error #<wCode>`"が返されます。 メッセージがない場合、一般的なメッセージ "`Unknown error #<hresult>`" が返されます。 返される文字列とは、Unicode または _UNICODE マクロの状態に応じて、マルチバイト文字列です。  
  
## <a name="remarks"></a>Remarks  
 内に記録された HRESULT の適切なシステム メッセージのテキストを取得、`_com_error`オブジェクト。 システム メッセージのテキストは、Win32 を呼び出すことによって取得[FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351)関数。 返される文字列は `FormatMessage` API によって割り当てられ、`_com_error` オブジェクトが破棄されるときに解放されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)