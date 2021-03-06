---
title: 構造体 UNWIND_INFO |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6046dffd74824b05c7b7b10be57bb0b2274ffdc
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207573"
---
# <a name="struct-unwindinfo"></a>構造体 UNWIND_INFO
アンワインド データ情報構造体を使用して、関数のスタック ポインターと不揮発性レジスタがスタックに保存されているが及ぼす影響を記録します。  
  
|||  
|-|-|  
|UBYTE: 3|Version|  
|UBYTE: 5|フラグ|  
|UBYTE|プロローグのサイズ|  
|UBYTE|アンワインド コードの数|  
|UBYTE: 4|フレームの登録|  
|UBYTE: 4|フレーム (スケール) レジスタのオフセット|  
|USHORT \* n|アンワインド コード配列|  
|変数|いずれかの形式の (1) またはできます (2) 以下|  
  
 (1) 例外ハンドラー  
  
|||  
|-|-|  
|ULONG|例外ハンドラーのアドレス|  
|変数|言語固有のハンドラーのデータ (省略可能)|  
  
 (2) チェーン アンワインド情報  
  
|||  
|-|-|  
|ULONG|関数の開始アドレス|  
|ULONG|関数の終了アドレス|  
|ULONG|アンワインド情報のアドレス|  
  
 UNWIND_INFO 構造体は、メモリに配置するか DWORD である必要があります。 各フィールドの意味は次のとおりです。  
  
 **Version**  
 1 現在、アンワインド データのバージョン番号です。  
  
 **フラグ**  
 現在、3 つのフラグが定義されています。  
  
 存在する UNW_FLAG_EHANDLER 関数が、例外ハンドラーが例外を確認する必要がある関数を検索するときに呼び出す必要があります。  
  
 UNW_FLAG_UHANDLER 関数には、終了ハンドラーが例外のアンワインド時に呼び出される必要があります。  
  
 UNW_FLAG_CHAININFO これのアンワインド情報の構造は、プロシージャの主なものではありません。 代わりに、チェーン アンワインド情報エントリは、前の RUNTIME_FUNCTION エントリの内容とします。 詳細については、次のテキストを参照してください。 チェーン アンワインド情報の構造。 このフラグを設定するが存在する UNW_FLAG_EHANDLER と UNW_FLAG_UHANDLER フラグをクリアする必要があります。 また、フレームの登録と固定スタック割り当てフィールドには、プライマリ アンワインド情報と同じ値が必要です。  
  
 **プロローグのサイズ**  
 (バイト単位)、関数プロローグの長さ。  
  
 **アンワインド コードの数**  
 これは、アンワインド コード配列のスロットの数です。 いくつかアンワインド コード (たとえば、UWOP_SAVE_NONVOL) であることに注意してくださいでは、配列内の 1 つ以上のスロットが必要です。  
  
 **フレームの登録**  
 関数は、フレーム ポインターを使用し、0 以外の場合は、このフィールドが UNWIND_CODE ノードの操作情報フィールドに同じエンコーディングを使用して、フレーム ポインターとして使用される不揮発性レジスタの数です。  
  
 **フレーム (スケール) オフセットを登録します。**  
 フレームのレジスタのフィールドが 0 以外の場合は、これが確立されるときに、FP レジスタに適用される RSP からスケールのオフセットです。 実際の FP レジスタが RSP + 16 に設定されている\*この番号は、240 の 0 からのオフセットします。 これにより、動的スタック フレームを短い手順 (詳細な手順については、8 ビット符号付きオフセット形式を使用できます) より優れたコードの密度を許可するローカル スタック割り当ての中央に FP レジスタをポイントします。  
  
 **アンワインド コード配列**  
 これは、不揮発性レジスタと RSP プロローグの効果を説明する項目の配列です。 個々 の項目の意味について UNWIND_CODE のセクションを参照してください。 配置のために、この配列は常に偶数の項目が最後のエントリを使用していない可能性があります (この場合、配列いずれかになりますアンワインド コード フィールドの数で指定されたよりも長い) があります。  
  
 **例外ハンドラーのアドレス**  
 これは、(UNW_FLAG_CHAININFO フラグがオフが存在する UNW_FLAG_EHANDLER または UNW_FLAG_UHANDLER フラグのいずれかで設定されている) 場合、関数の終了/言語固有の例外ハンドラーに、イメージの相対ポインターです。  
  
 **言語固有のハンドラーのデータ**  
 これは、関数の言語固有の例外ハンドラーのデータです。 このデータの形式が指定されていないし、使用中の特定の例外ハンドラーによって完全に決定されます。  
  
 **チェーン アンワインド情報**  
 UNW_FLAG_CHAININFO フラグが設定されている場合は、3 つ UWORDs で UNWIND_INFO 構造体が終了します。  これら UWORDs では、関数のチェーンのアンワインドの RUNTIME_FUNCTION 情報を表します。  
  
## <a name="see-also"></a>関連項目  
 [例外処理とデバッガー サポートのためのアンワインド データ](../build/unwind-data-for-exception-handling-debugger-support.md)