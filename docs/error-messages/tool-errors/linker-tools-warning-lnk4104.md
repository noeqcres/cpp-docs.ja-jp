---
title: リンカー ツールの警告 LNK4104 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9ea3e074cc0db9591cd0ffe9329ff7f1936563f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300954"
---
# <a name="linker-tools-warning-lnk4104"></a>リンカー ツールの警告 LNK4104
シンボル 'symbol' のエクスポートがプライベートにする必要があります。  
  
 `symbol`次のいずれかになります。  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 この警告では、dll インポート ライブラリを構築するときに出力し、上記の関数のいずれかのモジュール定義ファイルでプライベートとしてを指定せずにエクスポートします。 一般に、これらの関数は、OLE でのみ使用するエクスポートされます。 リンクされているライブラリを正しくプログラムがそれらへの呼び出しを行うときに、インポート ライブラリ内に配置することは異常な動作につながります。 PRIVATE キーワードの詳細については、次を参照してください。[エクスポート](../../build/reference/exports.md)です。