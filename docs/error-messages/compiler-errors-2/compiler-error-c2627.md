---
title: コンパイラ エラー C2627 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2627
dev_langs:
- C++
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67123349dd782beb9b547d3497d6c71d4390e434
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231375"
---
# <a name="compiler-error-c2627"></a>コンパイラ エラー C2627
'function': メンバー関数が匿名共用体では使用できません  
  
 [匿名共用体](../../cpp/unions.md#anonymous_unions)メンバー関数を持つことはできません。  
  
 次の例では、C2627 が生成されます。  
  
```  
// C2627.cpp  
int main() {  
   union { void f(){} };   // C2627  
   union X { void f(){} };  
}  
```