---
title: A.29 使用の動作共有構築内 critical コンストラクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d5c8a83f-2f51-4f23-8ddf-d267e347507f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ccbb39a9067adf545339d02fe0c05e24fbcdb0a4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691353"
---
# <a name="a29---use-of-work-sharing-constructs-inside-a-critical-construct"></a>A.29 critical コンストラクト内での work-sharing コンストラクトの使用
次の例では、内部 work-sharing コンス トラクターの使用方法を示します、`critical`を構築します。 この例では準拠作業の共有を作成し、`critical`コンストラクトを同じ並列領域にバインドしないでください。  
  
```  
void f()  
{  
  int i = 1;  
  #pragma omp parallel sections  
  {  
    #pragma omp section  
    {  
      #pragma omp critical (name)  
      {  
        #pragma omp parallel  
        {  
          #pragma omp single  
          {  
            i++;  
          }  
        }  
      }  
    }  
  }  
}  
```