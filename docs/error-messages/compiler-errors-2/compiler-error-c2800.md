---
title: コンパイラ エラー C2800 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2800
dev_langs:
- C++
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dd9723513042ae7ef6d63914f5abecd63192e37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235598"
---
# <a name="compiler-error-c2800"></a>コンパイラ エラー C2800
'operator 演算子' をオーバー ロードできません。  
  
 次の演算子はオーバー ロードできません: クラス メンバーに対するアクセス (`.`)、メンバーへのポインター (`.*`)、スコープ解決 (`::`)、条件式 (`? :`)、および`sizeof`です。  
  
 次の例では、C2800 が生成されます。  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```