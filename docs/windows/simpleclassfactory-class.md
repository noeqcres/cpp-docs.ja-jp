---
title: SimpleClassFactory クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleClassFactory class
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c490e21717e44ec3e772c01f84a0f5adb08471fd
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012496"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory クラス
基底クラスを作成するための基本的なメカニズムを提供します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename Base>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
### <a name="parameters"></a>パラメーター  
 *ベース*  
 基本クラスです。  
  
## <a name="remarks"></a>Remarks  
 基底クラスには、既定のコンス トラクターを提供する必要があります。  
  
 次のコード例は、使用する方法を示します**SimpleClassFactory**で、 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)マクロ。  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SimpleClassFactory::CreateInstance メソッド](../windows/simpleclassfactory-createinstance-method.md)|指定したインターフェイスのインスタンスを作成します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)