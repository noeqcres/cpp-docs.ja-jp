---
title: コンパイラ エラー C3226 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3226
dev_langs:
- C++
helpviewer_keywords:
- C3226
ms.assetid: 636106ca-6f4e-4303-a6a0-8803221ec67d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2eb5fca95c876b1020a630f0ebe69e56a1dfa362
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250430"
---
# <a name="compiler-error-c3226"></a>コンパイラ エラー C3226
テンプレート宣言は、ジェネリック宣言の内部では使用できません  
  
 ジェネリック クラス内部のジェネリック宣言を使用します。  
  
 次の例では C3226 が生成されます。  
  
```  
// C3226.cpp  
// compile with: /clr  
generic <class T>  
ref class C {  
   template <class T1>   // C3226  
   ref struct S1 {};  
};  
```  
  
 次の例では、考えられる解決策を示しています。  
  
```  
// C3226b.cpp  
// compile with: /clr /c  
generic <class T>  
ref class C {  
   generic <class T1>  
   ref struct S1 {};  
};  
```