---
title: コンパイラ エラー C3734 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3734
dev_langs:
- C++
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af0b27f449e61d6b80ad2d19eb09a3a55c5f3ad1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264195"
---
# <a name="compiler-error-c3734"></a>コンパイラ エラー C3734
'class': マネージまたは WinRT クラスは、コクラスにすることはできません  
  
 [コクラス](../../windows/coclass.md)で属性は使用できませんマネージまたは WinRT クラスです。  
  
 次の例では C3734 が生成され、その修正方法が示されています。  
  
```  
// C3734.cpp  
// compile with: /clr /c  
[module(name="x")];  
  
[coclass]  
ref class CMyClass {   // C3734 remove the ref keyword to resolve  
};  
```  
