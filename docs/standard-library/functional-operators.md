---
title: '&lt;functional&gt; 演算子 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
dev_langs:
- C++
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9bc37213ed2e5690f85fca738d44e6eecfaa8c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962050"
---
# <a name="ltfunctionalgt-operators"></a>&lt;functional&gt; 演算子

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_eq_eq"></a>  operator==

呼び出し可能オブジェクトが空かどうかをテストします。

```cpp
template <class Fty>
bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
bool operator==(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>パラメーター

*Fty*をラップする関数の型。

*f*関数オブジェクト

*npc* null ポインター。

### <a name="remarks"></a>Remarks

どちらの演算子も、`function` オブジェクトへの参照である引数と null ポインター定数である引数を受け取ります。 `function` オブジェクトが空の場合にのみ、両方とも true を返します。

### <a name="example"></a>例

```cpp
// std__functional__operator_eq.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
{
    return (-val);
}

int main()
{
    std::function<int(int)> fn0;
    std::cout << std::boolalpha << "empty == "
        << (fn0 == 0) << std::endl;

    std::function<int(int)> fn1(neg);
    std::cout << std::boolalpha << "empty == "
        << (fn1 == 0) << std::endl;

    return (0);
}

```

```Output
empty == true
empty == false
```

## <a name="op_neq"></a>  operator!=

呼び出し可能オブジェクトが空かどうかをテストします。

```cpp
template <class Fty>
bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
bool operator!=(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>パラメーター

*Fty*をラップする関数の型。

*f*関数オブジェクト

*npc* null ポインター。

### <a name="remarks"></a>Remarks

どちらの演算子も、`function` オブジェクトへの参照である引数と null ポインター定数である引数を受け取ります。 `function` オブジェクトが空ではない場合にのみ、両方とも true を返します。

### <a name="example"></a>例

```cpp
// std__functional__operator_ne.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0;
    std::cout << std::boolalpha << "not empty == "
        << (fn0 != 0) << std::endl;

    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "not empty == "
        << (fn1 != 0) << std::endl;

    return (0);
    }

```

```Output
not empty == false
not empty == true
```

## <a name="see-also"></a>関連項目

[\<functional>](../standard-library/functional.md)<br/>
