---
title: リンカー ツールの警告 LNK4071 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4071
dev_langs:
- C++
helpviewer_keywords:
- LNK4071
ms.assetid: 803f8c34-8219-4f55-a4ae-7133ceff2ba3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cb0d4b8d78eb8c7cf1812abb1a7981c605f2c4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299901"
---
# <a name="linker-tools-warning-lnk4071"></a>リンカー ツールの警告 LNK4071
以降のリンクではインクリメンタル リンクすることはできません。  
  
 リンクが 1 つまたは複数のシンボルに対して複数の定義が見つかりましたが、 [/force](../../build/reference/force-force-file-output.md)または **/FORCE:MULTIPLE**エラーに関係なく、出力ファイルの作成に使用します。 リンクは、インクリメンタル ステータス (.ilk) ファイルを削除します。