---
title: デュアル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dual
dev_langs:
- C++
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60a4326975f60455e6d2ef90575f5c940287042a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644113"
---
# <a name="dual"></a>dual
.Idl ファイルにデュアル インターフェイスとしてインターフェイスを配置します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[dual]  
```  
  
## <a name="remarks"></a>Remarks  
 ときに、**デュアル**C++ 属性をインターフェイスの前と、インターフェイス、生成された .idl ファイルのライブラリ ブロック内に配置されます。  
  
## <a name="example"></a>例  
 次のコードは、属性ブロックを使用する**デュアル**インターフェイス定義の前に。  
  
```cpp  
// cpp_attr_ref_dual.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]  
  
__interface IStatic : IDispatch   
{  
   HRESULT Func1(int i);  
   [   propget,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([out, retval] long *nSize);  
   [   propput,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([in] long nSize);      
};  
  
[cpp_quote("#include file.h")];  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**interface**|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|`dispinterface`|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [使用法別の属性](../windows/attributes-by-usage.md)   
 [カスタム](../windows/custom-cpp.md)   
 [ディスパッチ インターフェイス](../windows/dispinterface.md)   
 [object](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   