---
title: コンパイラ エラー C3118 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3118
dev_langs:
- C++
helpviewer_keywords:
- C3118
ms.assetid: 40fbe681-8868-4cb2-a2b2-4db4449319a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ecc3dc79cd52631f3dba5c204cabc02e7932bc1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244457"
---
# <a name="compiler-error-c3118"></a>コンパイラ エラー C3118
'interface': インターフェイスは仮想継承をサポートしていません  
  
 仮想インターフェイスから継承しようとするとします。 たとえば、オブジェクトに適用された  
  
```  
// C3118.cpp  
__interface I1 {  
};  
  
__interface I2 : virtual I1 {   // C3118  
};  
```  
  
 このエラーを生成します。