---
title: asctime、_wasctime |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wasctime
- asctime
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tasctime
- asctime
- _wasctime
dev_langs:
- C++
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b18edc9e61f7065fcac1fe6231012bd232ccc18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396197"
---
# <a name="asctime-wasctime"></a>asctime、_wasctime

変換、 **tm**時刻の文字列に構造体。 これらの関数のセキュリティを強化したバージョンを使用できます。「[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *asctime(
   const struct tm *timeptr
);
wchar_t *_wasctime(
   const struct tm *timeptr
);
```

### <a name="parameters"></a>パラメーター

*timeptr*<br/>
時刻/日付の構造体。

## <a name="return-value"></a>戻り値

**asctime**結果の文字列以外のポインターを返します **_wasctime**ワイド文字の文字列の結果のポインターを返します。 エラーの戻り値はありません。

## <a name="remarks"></a>コメント

これらの関数のセキュリティを強化したバージョンを使用できます。「[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)」を参照してください。

**Asctime**関数が、構造体を文字の文字列として格納されている時刻に変換します。 *Timeptr*への呼び出しから値が取得した通常**gmtime**または**localtime**へのポインターを返す両方が、 **tm**構造体時間で定義されます。H.

|timeptr メンバー|[値]|
|--------------------|-----------|
|**tm_hour**|午前 0 時 (0 ~ 23) 以降の時間|
|**tm_isdst**|夏時間が有効な場合は正、夏時間が無効な場合は 0、夏時間かどうかが不明な場合は負。 C ランタイム ライブラリでは、アメリカ合衆国の規則を前提に夏時間 (DST) を計算します。|
|**tm_mday**|(1 ~ 31) の月の日|
|**未満**|分 (0 ~ 59)|
|**表します。**|月 (0 ~ 11 です。年 1 月 = 0)|
|**tm_sec**|秒 (0 ~ 59)|
|**tm_wday**|曜日 (0 ~ 6 です。日曜日 = 0)|
|**tm_yday**|年 (0 ~ 365; の日付1 月 1 日 = 0)|
|**tm_year**|年 (実際の西暦から 1900 を引いた数)|

変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 ローカル タイムの設定の詳細については、[time](time-time32-time64.md)、[_ftime](ftime-ftime32-ftime64.md)、および [localtime](localtime-localtime32-localtime64.md) の関数を参照してください。また、タイム ゾーン環境とグローバル変数の定義の詳細については、[_tzset](tzset.md) 関数を参照してください。

によって生成される結果の文字列**asctime** 26 文字が含まれていて、フォーム`Wed Jan 02 02:03:55 1980\n\0`です。 24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字と null 文字が入ります。 **asctime**戻り値の文字列を保持するために、静的に割り当てられた 1 つのバッファーを使用します。 この関数を呼び出すたびに、前の呼び出しの結果は破棄されます。

**_wasctime**のワイド文字バージョンは、 **asctime**です。 **_wasctime**と**asctime**それ以外の場合の動作は同じです。

これらの関数では、パラメーターの検証が行われます。 場合*timeptr* null ポインター、または範囲外の値がある場合、無効なパラメーター ハンドラーが呼び出される、」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行は継続許可されたかどうか、関数を返します**NULL**設定と**errno**に**EINVAL**です。

### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime**|**asctime**|**asctime**|**_wasctime**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**asctime**|\<time.h>|
|**_wasctime**|\<time.h> または \<wchar.h>|

## <a name="example"></a>例

このプログラムは、長整数型のシステム時刻を配置**時計**、構造に変換され**newtime**し、その文字列の形式に変換の出力を使用して、および、 **asctime**関数。

```C
// crt_asctime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
    struct tm   *newTime;
    time_t      szClock;

    // Get time in seconds
    time( &szClock );

    // Convert time to struct tm form
    newTime = localtime( &szClock );

    // Print local time as a string.
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996
    // Note: asctime is deprecated; consider using asctime_s instead
}
```

```Output
Current date and time: Sun Feb 03 11:38:58 2002
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)<br/>
