---
title: fn_cdc_decrement_lsn (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_cdc_decrement_lsn
- sys.fn_cdc_decrement_lsn_TSQL
- sys.fn_cdc_decrement_lsn
- fn_cdc_decrement_lsn_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- fn_cdc_decrement_lsn
- sys.fn_cdc_decrement_lsn
ms.assetid: 83c182ad-4713-439b-8769-9b7408aec8b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 468fa452a5b9015bf5fcc613c040f76160e87210
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68046507"
---
# <a name="sysfn_cdc_decrement_lsn-transact-sql"></a>sys.fn_cdc_decrement_lsn (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  指定された LSN の直前のログ シーケンス番号 (LSN) を返します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sys.fn_cdc_decrement_lsn ( lsn_value )  
```  
  
## <a name="arguments"></a>引数  
 *lsn_value*  
 LSN 値を指定します。 *lsn_value*は**binary (10)** です。  
  
## <a name="return-type"></a>戻り値の型  
 **binary (10)**  
  
## <a name="remarks"></a>解説  
 この関数から返される LSN は、指定された値よりも必ず小さくなり、2 つの値の間に LSN 値が存在することはありません。  
  
## <a name="permissions"></a>アクセス許可  
 **Public**データベースロールのメンバーシップが必要です。  
  
## <a name="examples"></a>例  
 次の例で`sys.fn_cdc_decrement_lsn`は、を使用して、lsn 値が最大値よりも小さい変更データ行を返すクエリで、上限の lsn の境界を設定します。  
  
```  
Use AdventureWorks2012;  
GO  
DECLARE @from_lsn binary(10), @to_lsn binary(10);  
SET @from_lsn = sys.fn_cdc_get_min_lsn('HumanResources_Employee');  
SET @to_lsn = sys.fn_cdc_decrement_lsn(sys.fn_cdc_get_max_lsn());  
SELECT * FROM cdc.fn_cdc_get_all_changes_HumanResources_Employee( @from_lsn, @to_lsn, 'all');   
GO  
```  
  
## <a name="see-also"></a>参照  
 [fn_cdc_increment_lsn &#40;Transact-sql&#41;](../../relational-databases/system-functions/sys-fn-cdc-increment-lsn-transact-sql.md)   
 [fn_cdc_get_min_lsn &#40;Transact-sql&#41;](../../relational-databases/system-functions/sys-fn-cdc-get-min-lsn-transact-sql.md)   
 [fn_cdc_get_max_lsn &#40;Transact-sql&#41;](../../relational-databases/system-functions/sys-fn-cdc-get-max-lsn-transact-sql.md)   
 [トランザクションログ &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md)   
 [変更データキャプチャについて &#40;SQL Server&#41;](../../relational-databases/track-changes/about-change-data-capture-sql-server.md)  
  
  
