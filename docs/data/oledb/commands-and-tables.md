---
title: コマンドとテーブル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, table support
- CCommand class, OLE DB consumer templates
- commands [C++], OLE DB Consumer Templates
- CTable class
- CAccessorRowset class, command and table classes
- rowsets, accessing
- tables [C++], OLE DB Consumer Templates
- OLE DB consumer templates, command support
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3d045035ad757286b30b4adecf2f04f4dfbfd25
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340196"
---
# <a name="commands-and-tables"></a>コマンドとテーブル
コマンドとテーブルに行セットにアクセスすることを許可します。行セットを開き、コマンドを実行して、列をバインドします。 [CCommand](../../data/oledb/ccommand-class.md)と[CTable](../../data/oledb/ctable-class.md)クラスがそれぞれコマンドとテーブルのオブジェクトをインスタンス化します。 これらのクラスから派生[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)次の図に示すようにします。  
  
 ![CCommand および CTable](../../data/oledb/media/vccommandstables.gif "vccommandstables")  
コマンドとテーブル クラス  
  
 前の表に`TAccessor`、アクセサーの型に指定できる[アクセサーの種類](../../data/oledb/accessors-and-rowsets.md)します。 *TRowset*任意の行セット型に指定できる[行セットの種類](../../data/oledb/accessors-and-rowsets.md)します。 *TMultiple* (1 つまたは複数の結果セット) の結果型を指定します。  
  
 [ATL OLE DB コンシューマー ウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)コマンドまたはテーブル オブジェクトにするかどうかを指定することができます。  
  
-   コマンドなしのデータ ソースで使用することができます、`CTable`クラス。 通常に使用するパラメーターを指定しないと、複数の結果を必要とする単純な行セット。 この単純なクラスは、指定したテーブル名を使用してデータ ソースのテーブルを開きます。  
  
-   コマンドをサポートするデータ ソースで使用することができます、`CCommand`クラスの代わりにします。 コマンドを実行するには、呼び出す[オープン](../../data/oledb/ccommand-open.md)このクラスにします。 代わりに、呼び出すことができます`Prepare`を複数回実行するコマンドを準備します。  
  
     `CCommand` 次の 3 つのテンプレート引数を持つ: アクセサーの型、行セットの種類、および結果型は (`CNoMultipleResults`、既定では、または`CMultipleResults`)。 指定した場合`CMultipleResults`、`CCommand`クラスでサポート、`IMultipleResults`インターフェイスし、複数の行セットを処理します。 [DBVIEWER](http://msdn.microsoft.com/07620f99-c347-4d09-9ebc-2459e8049832)サンプルは、複数の結果を処理する方法を示します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)