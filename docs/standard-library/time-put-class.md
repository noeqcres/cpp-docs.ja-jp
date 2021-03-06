---
title: time_put クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::time_put [C++]
- std::time_put [C++], char_type
- std::time_put [C++], iter_type
- std::time_put [C++], do_put
- std::time_put [C++], put
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6c1c11a9c81123c518e3a0da3e56cc81d4cd5c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958930"
---
# <a name="timeput-class"></a>time_put クラス

このテンプレート クラスは、時刻値から `CharType` 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>パラメーター

*CharType*  
 文字をエンコードするためにプログラム内で使用される型。

*OutputIterator*  
 時刻の put 関数が出力を書き込む反復子の型。

## <a name="remarks"></a>Remarks

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[time_put](#time_put)|`time_put` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|出力反復子を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_put](#do_put)|時刻と日付の情報を `CharType` のシーケンスとして出力する仮想関数。|
|[put](#put)|時刻と日付の情報を `CharType` のシーケンスとして出力します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="char_type"></a>  time_put::char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `CharType` のシノニムです。

## <a name="do_put"></a>  time_put::do_put

時刻と日付の情報を `CharType` のシーケンスとして出力する仮想関数。

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>パラメーター

*next*  
 時刻と日付を表す文字のシーケンスが挿入される出力反復子。

*されている _Iosbase*  
 使用されません。

*_Pt*  
 出力される時刻と日付の情報。

*_Fmt*  
 出力の形式。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

*_Mod*  
 形式の修飾子。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

### <a name="return-value"></a>戻り値

最後に挿入された要素の後の最初の位置を指す反復子。

### <a name="remarks"></a>Remarks

プロテクト仮想メンバー関数から始まる連続した要素を生成する`next`オブジェクトに格納されている時刻値から\* `_Pt`、型の`tm`します。 関数は、生成された出力を超える、次に要素を挿入する場所を指定する反復子を返します。

使用される同じ規則によって、出力が生成`strftime`の最後の引数と *_Pt*、一連を生成するため**char**要素を配列にします。 これらの各**char**要素は型の同等の要素にマップすると見なされます`CharType`単純な一対一のマッピングでします。 場合 *_Mod*が 0 に等しい、有効な形式は"%f"で、F が置き換えられます *_Fmt*します。 それ以外、有効な形式は"%mf"で、M が置き換えられます *_Mod*します。

### <a name="example"></a>例

[put](#put) の例 (`do_put` を呼び出す) を参照してください。

## <a name="iter_type"></a>  time_put::iter_type

出力反復子を表す型。

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `OutputIterator` のシノニムです。

## <a name="put"></a>  time_put::put

時刻と日付の情報を `CharType` のシーケンスとして出力します。

```cpp
iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;

iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*next*  
 時刻と日付を表す文字のシーケンスが挿入される出力反復子。

*されている _Iosbase*  
 使用されません。

*_Fill*  
 型の文字`CharType`スペースに使用します。

*_Pt*  
 出力される時刻と日付の情報。

*_Fmt*  
 出力の形式。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

*_Mod*  
 形式の修飾子。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

*first*  
 出力の書式設定文字列の先頭。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

*last*  
 出力の書式設定文字列の末尾。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

### <a name="return-value"></a>戻り値

最後に挿入された要素の後の最初の位置を指す反復子。

### <a name="remarks"></a>Remarks

最初のメンバー関数を返します[do_put](#do_put)(`next`、 `_Iosbase`、 `_Fill`、 `_Pt`、 `_Fmt`、 `_Mod`)。 2 番目のメンバー関数は、\* `next` ++ に、間隔 [ `first`, `last`) のパーセント (%) 以外のすべての要素をコピーします。 間隔 [ `first`, `last`) 内の、文字 *C* の前のパーセントについては、関数は、代わりに、`next` = `do_put`( `next`, `_Iosbase`, `_Fill`, `_Pt`, *C*, 0) を評価し、*C* をスキップします。ただし、*C* が設定された EOQ# からの修飾子文字で、かつ、間隔 [ `first`, `last`) の中で文字 `C2` が続く場合、関数は、代わりに、`next` = `do_put`( `next`, `_Iosbase`, `_Fill`, `_Pt`, `C2`, *C*) を評価し、`C2` をスキップします。

### <a name="example"></a>例

```cpp
// time_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   t.tm_hour = 5;
   t.tm_min = 30;
   t.tm_sec = 40;
   t.tm_year = 00;
   t.tm_mday = 4;
   t.tm_mon = 6;

   pszPutI.imbue( loc );
   char *pattern = "x: %X %x";
   use_facet <time_put <char> >
   (loc).put(basic_ostream<char>::_Iter(pszPutI.rdbuf( )),
          pszPutI, ' ', &t, pattern, pattern+strlen(pattern));

      cout << "num_put( ) = " << pszPutI.rdbuf( )->str( ) << endl;

      char strftimebuf[255];
      strftime(&strftimebuf[0], 255, pattern, &t);
      cout << "strftime( ) = " << &strftimebuf[0] << endl;
}
```

```Output
num_put( ) = x: 05:30:40 07/04/00
strftime( ) = x: 05:30:40 07/04/00
```

## <a name="time_put"></a>  time_put::time_put

`time_put` 型のオブジェクトのコンストラクター。

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

*_Refs*オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>Remarks

使用可能な値を *_Refs*パラメーターとその重要性は。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \> 1: これらの値が定義されていません。

コンス トラクターを使用してその基本オブジェクトを初期化します[locale::facet](../standard-library/locale-class.md#facet_class)(*_Refs*)。

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)<br/>
[time_base クラス](../standard-library/time-base-class.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
