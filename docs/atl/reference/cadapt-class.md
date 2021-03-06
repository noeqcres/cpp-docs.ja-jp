---
title: CAdapt クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs:
- C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bf0739c92513519147e9aed3b88210c4f61d0b4
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882983"
---
# <a name="cadapt-class"></a>CAdapt クラス
このテンプレートは、オブジェクトのアドレス以外の値を返すために、アドレス演算子を再定義するクラスをラップするときに使用されます。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CAdapt
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 適合された型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|コンストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAdapt::operator const T (& a)](#operator_const_t_amp)|返します、 **const**への参照`m_T`します。|  
|[CAdapt::operator T (& a)](#operator_t_amp)|`m_T` への参照を返します。|  
|[CAdapt::operator <](#operator_lt)|適合された型のオブジェクトを `m_T` と比較します。|  
|[CAdapt::operator =](#operator_eq)|適合された型のオブジェクトを `m_T` に割り当てます。|  
|[CAdapt::operator = =](#operator_eq_eq)|適合された型のオブジェクトを `m_T` と比較します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|適合しているデータ。|  
  
## <a name="remarks"></a>Remarks  
 `CAdapt` は、オブジェクトのアドレス以外の値を返すために、アドレス演算子 (`operator &`) を再定義するクラスをラップするときに使用される簡単なテンプレートです。 このようなクラスの例としては、ATL の `CComBSTR`、`CComPtr`、および `CComQIPtr` クラス、そしてコンパイラ COM サポート クラスである `_com_ptr_t` が含まれます。 これらすべてのクラスがそのデータ メンバーのいずれかのアドレスを返す address-of 演算子を再定義 (の場合、BSTR `CComBSTR`、他のクラスの場合はインターフェイス ポインター)。  
  
 `CAdapt` の主な役割は、クラス `T` によって定義された address-of 演算子を隠しながら、適合されたクラスの特性を保持することです。 `CAdapt` によって、パブリック メンバーを保持するこのロールを満たす[m_T](#m_t)、型の`T`との特殊化を許可するには、変換演算子、比較演算子、およびコピー コンス トラクターを定義することで`CAdapt`いるかのように扱われます型のオブジェクト`T`します。  
  
 アダプター クラス `CAdapt` は、いくつかの container-style クラスで、含まれるオブジェクトのアドレスを address-of 演算子を使用して取得できることが想定されているために、役立ちます。 address-of 演算子の再定義によって、この要件に混乱が生じ、通常はコンパイル エラーが発生し、"単に動作" することが想定されているクラスで、適合されていない型の使用が妨げられることがあります。 `CAdapt` では、こうした問題を回避するための手段が提供されています。  
  
 通常 container-style クラスでは、`CAdapt`、`CComBSTR`、`CComPtr`、または `CComQIPtr` オブジェクトを保存する場合に `_com_ptr_t` を使用します。 これは、C++11 Standard のサポート前には C++ Standard Library コンテナーで最も一般的に必要とされていましたが、C++11 Standard Library コンテナーは `operator&()` をオーバーロードした型と共に自動的に動作します。 標準ライブラリ、これを使用して内部的に実現[std::addressof](../../standard-library/memory-functions.md#addressof)オブジェクトの場合は true。 アドレスを取得します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="cadapt"></a>  CAdapt::CAdapt  
 コンス トラクターを使用すると、既定で構築された、適合された型のオブジェクトからコピーまたは別のアダプター オブジェクトからコピーするアダプター オブジェクト。  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 *rSrc*  
 新しく構築されたアダプター オブジェクトにコピーされるが適用される型の変数を指定します。  
  
 *rSrCA*  
 アダプター オブジェクトが含まれているデータをコピー (または移動)、新しく構築されたアダプタ オブジェクトにします。  
  
##  <a name="m_t"></a>  CAdapt::m_T  
 適合しているデータを保持します。  
  
```
T m_T;
```  
  
### <a name="remarks"></a>Remarks  
 これは、**パブリック**データ メンバーにアクセスできる直接的または間接的に[演算子 const T &](#operator_const_t_amp)と[演算子 T &](#operator_t_amp)します。  
  
##  <a name="operator_const_t_amp"></a>  CAdapt::operator const T&amp;  
 返します、 **const**への参照、 [m_T](#m_t)メンバー型のオブジェクトの場合と同様に処理されるアダプター オブジェクト`T`します。  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>戻り値  
 A **const**への参照`m_T`します。  
  
##  <a name="operator_t_amp"></a>  CAdapt::operator T&amp;  
 参照を返します、 [m_T](#m_t)アダプター オブジェクトを型のオブジェクトの場合と同様に扱うメンバー`T`します。  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>戻り値  
 参照を`m_T`します。  
  
##  <a name="operator_lt"></a>  CAdapt::operator &lt;  
 適合された型のオブジェクトと比較[m_T](#m_t)します。  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>パラメーター  
 *rSrc*  
 比較するオブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 間の比較の結果`m_T`と*rSrc*します。  
  
##  <a name="operator_eq"></a>  CAdapt::operator =  
 代入演算子には、引数が割り当てられます*rSrc*、データ メンバーに[m_T](#m_t)アダプターの現在のオブジェクトを返します。  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 *rSrc*  
 コピーする適合された型のオブジェクトへの参照。 

 *rSrCA*移動するオブジェクトへの参照。 
  
### <a name="return-value"></a>戻り値  
 現在のオブジェクトへの参照。  
  
##  <a name="operator_eq_eq"></a>  CAdapt::operator = =  
 適合された型のオブジェクトと比較[m_T](#m_t)します。  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>パラメーター  
 *rSrc*  
 比較するオブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 間の比較の結果`m_T`と*rSrc*します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
