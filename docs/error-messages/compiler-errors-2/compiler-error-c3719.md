---
title: コンパイラ エラー C3719 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3719
dev_langs:
- C++
helpviewer_keywords:
- C3719
ms.assetid: d0d59d4e-babb-4480-9ef7-70cf1a28165c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a399b9ccdb8aefe9e566172c4dc2b566e4fa3ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277908"
---
# <a name="compiler-error-c3719"></a>コンパイラ エラー C3719
'interface': インターフェイス ベースのイベント ソースは、COM イベントにのみ使用できます  
  
 非 COM コンテキストのインターフェイスが宣言されています。  
  
 次の例では、C3719 が生成されます。  
  
```  
// C3719a.cpp  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
  
[object]  
__interface I {  
   HRESULT func1();  
};  
  
[event_source(native), coclass]  
struct A {  
   __event __interface I;   // C3719  
  
   // try the following line instead  
   // __event func2();  
};  
  
int main() {  
}  
```  
  
 このエラーを解決するには、適用、[オブジェクト](../../windows/object-cpp.md)、[コクラス](../../windows/coclass.md)、 [event_source](../../windows/event-source.md)、および[event_receiver](../../windows/event-receiver.md)属性を適切にする、クラス インターフェイス COM クラスを使用しています。 例えば:  
  
```  
// C3719b.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[module(name="xx")];  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f();  
};  
  
[coclass, event_source(com) , uuid("00000000-0000-0000-0000-000000000002")]  
struct MyStruct {  
   __event __interface I;  
};  
  
[event_receiver(com)]  
struct MyStruct2 {  
   void f() {  
   }  
   MyStruct2(I* pB) {  
      __hook(&I::f, pB, &MyStruct2::f);  
   }  
};  
  
int main()  
{  
}  
```