---
title: '&lt;limits&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66f9401bed0a6c9d0b1ffa09a10f98afa258069d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964757"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

テンプレート クラス `numeric_limits`、および浮動小数点表現と丸め処理に関する 2 種類の列挙体を定義します。

## <a name="syntax"></a>構文

```cpp
#include <limits>

```

## <a name="remarks"></a>Remarks

明示的な特殊化、`numeric_limits`クラスは、文字、整数、浮動小数点型など、基本的な型の多数のプロパティを記述および**bool**実装によって固定するのではなく、定義されています。C++ 言語の規則。 \<limits> に記述されたプロパティには、精度、表現の最小と最大サイズ、丸め処理、およびシグナリングに関するエラーが含まれます。

### <a name="enumerations"></a>列挙

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|この列挙体では、小さすぎて、正規化された値としては表現できない非正規化された浮動小数点値を表現するために、実装で選択できるさまざまなメソッドを記述します。|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|この列挙体では、浮動小数点値を整数値に丸めるために、実装で選択できるさまざまなメソッドを記述します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[numeric_limits クラス](../standard-library/numeric-limits-class.md)|このテンプレート クラスでは、組み込みの数値型の算術プロパティについて記述します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
