---
title: コンパイラの警告 C4956 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be92eb948e31a0a5367f92f5c2ed59baac2bd39b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703705"
---
# <a name="compiler-warning-c4956"></a>コンパイラの警告 C4956

> '*型*': この型は、検証できません

## <a name="remarks"></a>コメント

この警告は、 [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) が指定され、コードに検証不可能な型が含まれている場合に生成されます。 **/Clr:safe**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。

この警告は、エラーとして表示されます。無効にするには、 [warning](../../preprocessor/warning.md) プラグマ、または [/wd](../../build/reference/compiler-option-warning-level.md) コンパイラ オプションを使用します。

## <a name="example"></a>例

次の例では C4956 が生成されます。

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```