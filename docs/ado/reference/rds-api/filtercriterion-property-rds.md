---
title: Filterfilterproperty (RDS) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- FilterCriterion property [RDS]
ms.assetid: 24eb03ba-ccfd-4353-b6af-03586b2da6fd
author: MightyPen
ms.author: genemi
ms.openlocfilehash: e5b14e042c7566b6b6f8559e9dc371028a509979
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67964071"
---
# <a name="filtercriterion-property-rds"></a>FilterCriterion プロパティ (RDS)
フィルター値に使用する評価演算子を示します。  
  
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および[Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416)」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
  
DataControl.FilterCriterion = String  
```  
  
#### <a name="parameters"></a>パラメーター  
 *DataControl*  
 RDS を表すオブジェクト変数です[。DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)オブジェクト。  
  
 *String*  
 レコードに対する[Filtervalue](../../../ado/reference/rds-api/filtervalue-property-rds.md)の評価演算子を示す**文字列**値です。 次のいずれかを指定できます: < \<、=、>、>=、=、または <>。  
  
## <a name="remarks"></a>解説  
 [Sortcolumn](../../../ado/reference/rds-api/sortcolumn-property-rds.md)、 [sortcolumn](../../../ado/reference/rds-api/sortdirection-property-rds.md)、 [filtervalue](../../../ado/reference/rds-api/filtervalue-property-rds.md)、 **filterfilter、** および[filtervalue](../../../ado/reference/rds-api/filtercolumn-property-rds.md)プロパティは、クライアント側キャッシュでの並べ替えとフィルター処理の機能を提供します。 並べ替え機能は、1つの列の値でレコードを並べ替えます。 フィルター機能では、検索条件に基づいてレコードのサブセットが表示されますが、完全な[レコードセット](../../../ado/reference/ado-api/recordset-object-ado.md)はキャッシュに保持されます。 [Reset](../../../ado/reference/rds-api/reset-method-rds.md)メソッドは、条件を実行し、現在の**レコードセット**を更新可能な**レコードセット**に置き換えます。  
  
 "! =" 演算子は**フィルター条件**に対して無効です。代わりに、"<>" を使用してください。  
  
 フィルターと並べ替えの両方のプロパティが設定されていて、 **Reset**メソッドを呼び出すと、行セットが最初にフィルター処理され、次に並べ替えられます。 昇順の並べ替えでは、null 値が一番上にあります。降順の並べ替えでは、null 値は下部にあります (昇順は既定の動作です)。  
  
## <a name="applies-to"></a>適用対象  
 [DataControl オブジェクト (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## <a name="see-also"></a>参照  
 [FilterColumn、Filtercolumn、Filtercolumn、SortColumn、および Sortcolumn プロパティと Reset メソッドの例 (VBScript)](../../../ado/reference/rds-api/filter-column-criterion-value-sortcolumn-sortdirection-example-vbscript.md)   
 [FilterColumn プロパティ (RDS)](../../../ado/reference/rds-api/filtercolumn-property-rds.md)   
 [FilterValue プロパティ (RDS)](../../../ado/reference/rds-api/filtervalue-property-rds.md)   
 [SortColumn プロパティ (RDS)](../../../ado/reference/rds-api/sortcolumn-property-rds.md)   
 [SortDirection プロパティ (RDS)](../../../ado/reference/rds-api/sortdirection-property-rds.md)


