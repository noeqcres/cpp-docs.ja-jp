---
title: CObject からクラスを派生するときのオーバーヘッド | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ffff35cdef6cf2f730687334bbb56bc078371a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381678"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject からクラスを派生するときのオーバーヘッド
クラスから派生することで、オーバーヘッド[CObject](../mfc/reference/cobject-class.md)は最小限にします。 4 つだけの仮想関数と 1 つの派生クラスの継承[CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス: Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)
