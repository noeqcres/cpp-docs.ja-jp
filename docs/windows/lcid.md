---
title: lcid |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.lcid
dev_langs:
- C++
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 803b4652d4a6482e9e7615121d3a85f0bee309f7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013666"
---
# <a name="lcid"></a>lcid
ロケール識別子を関数に渡すことができます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[lcid]  
```  
  
## <a name="remarks"></a>Remarks  
 **Lcid**の機能を実装する C++ 属性、 [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) MIDL 属性。 ライブラリ ブロックのロケールを実装する場合は、使用、 **lcid =** `lcid`パラメーターを[モジュール](../windows/module-cpp.md)属性。  
  
## <a name="example"></a>例  
  
```cpp  
// cpp_attr_ref_lcid.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
typedef long HRESULT;  
  
[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]  
__interface IStatic {  
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス パラメーター|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   