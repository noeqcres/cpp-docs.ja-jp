---
title: サンプル コンテナー クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 004da50bf8d688f1d7b0432e5196094b878870cf
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955008"
---
# <a name="sample-container-class"></a>サンプル コンテナー クラス

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

型の通常の要素の可変長シーケンスを制御するオブジェクトについて説明します`Ty`します。 シーケンスは、実際のコンテナーに応じて、さまざまな方法で格納されます。

コンテナーのコンストラクターまたはメンバー関数がコンストラクター **Ty**(**const Ty&**) または関数 **Ty::operator=**(**const Ty&**) を呼び出す場合があります。 このような呼び出しで例外がスローされた場合、コンテナー オブジェクトは、その整合性を維持し、すべての例外をキャッチして再スローする必要があります。 コンテナー オブジェクトによっていずれか 1 つの例外がスローされた後に、コンテナー オブジェクトを安全にスワップ、消去、または破棄できます。 ただし、通常、それ以外の場合はコンテナー オブジェクトによって制御されるシーケンスの状態を予測できません。

その他の注意点:

- 場合、式`~Ty`例外をスローするには、コンテナー オブジェクトの結果の状態が定義されていません。

- コンテナーがアロケーター オブジェクトを格納する場合*al*、および*al*以外への呼び出しの結果として例外をスローします * al ***.allocate**コンテナーの結果の状態オブジェクトは定義されません。

- コンテナーが被制御シーケンスの順序付け方法を指定する関数オブジェクト *comp* を格納し、*comp* がいずれかの例外をスローする場合、コンテナー オブジェクトの結果の状態は未定義です。

C++ 標準ライブラリで定義されているコンテナー クラスは、次に説明するいくつかの追加要件を満たします。

コンテナーのテンプレート クラス [list](../standard-library/list-class.md) は、上記の例外が存在する場合でも、決定的かつ便利な動作を提供します。 たとえば、1 つまたは複数の要素の挿入時に例外がスローされた場合、コンテナーは変更されず、再度例外がスローされます。

*すべて*次のメンバー関数への呼び出し中に例外がスローされた場合、C++ 標準ライブラリによって定義されたコンテナー クラス`insert`、 `push_back`、または`push_front`コンテナーのまま変更されていないと、例外が再度スローされます。

*すべて*C++ 標準ライブラリで定義されているコンテナー クラス、例外がスローされない呼び出し中に次のメンバー関数: `pop_back`、`pop_front`します。

メンバー関数 [erase](../standard-library/container-class-erase.md) は、コピー操作 (割り当てまたはコピーの構築) が例外をスローする場合にのみ例外をスローします。

さらに、メンバー関数によって返される反復子のコピー中に例外はスローされません。

メンバー関数 [swap](../standard-library/container-class-swap.md) は、C++ 標準ライブラリで定義されている*すべての*コンテナー クラスに対する追加の確実性を実現します。

- コンテナーがアロケーター オブジェクト al を格納し、`al` がコピーされるときに例外をスローする場合にのみ、メンバー関数が例外をスローします。

- スワップされる被制御シーケンスの要素を指定する参照、ポインター、および反復子は有効なままです。

C++ 標準ライブラリで定義されたコンテナー クラスのオブジェクトが、`Alloc` 型の格納されているオブジェクトによって制御するシーケンスの記憶域の割り当ておよび解放を行います (これは通常、テンプレート パラメーターです)。 このアロケーター オブジェクトは、クラスのオブジェクトと同じ外部インターフェイスがあります`allocator<Ty>`します。 具体的には、`Alloc`と同じ型である必要があります `Alloc::rebind<value_type>::other`

*すべて*メンバー関数の C++ 標準ライブラリで定義されているコンテナー クラス`Alloc get_allocator const;`格納されたアロケーター オブジェクトのコピーを返します。 コンテナー オブジェクトを代入しても、格納されているアロケーター オブジェクトはコピー*されない*点に注意してください。 すべてのコンス トラクターに格納されている値の初期化`allocator`を`Alloc`コンス トラクターにアロケーターのパラメーターが含まれていない場合。

C++ 標準に従って、C++ 標準ライブラリで定義されたコンテナー クラスは次を想定できます。

- クラス `Alloc` のすべてのオブジェクトの比較結果が同じになります。

- 型`Alloc::const_pointer`と同じ`const Ty *`します。

- 型`Alloc::const_reference`と同じ`const Ty&`します。

- 型`Alloc::pointer`と同じ`Ty *`します。

- 型`Alloc::reference`と同じ`Ty&`します。

ただし、この実装では、コンテナーはこのような単純な想定を行いません。 このため、コンテナーはより意欲的なアロケーター オブジェクトと共に適切に動作します。

- クラス `Alloc` のすべてのオブジェクトの比較結果が同じである必要はありません。 (記憶域の複数のプールを維持することができます。)

- 型`Alloc::const_pointer`は同じである必要はありません`const Ty *`します。 (const ポインターには、クラスを指定できます。)

- 型`Alloc::pointer`は同じである必要はありません`Ty *`します。 (ポインターには、クラスを指定できます。)

## <a name="requirements"></a>必要条件

**ヘッダー**: \<sample container>

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)<br/>
