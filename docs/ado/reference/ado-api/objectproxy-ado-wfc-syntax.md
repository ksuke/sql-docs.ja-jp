---
title: ObjectProxy (ADO-WFC 構文) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- ObjectProxy collection [ADO]
ms.assetid: f68f58bc-ad28-46cc-9fb3-099e1a678397
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 485d011fa6762acd04cad54ff7fffc8d8136e063
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67917957"
---
# <a name="objectproxy-ado---wfc-syntax"></a>ObjectProxy (ADO - WFC 構文)
**Objectproxy**オブジェクトは、サーバーを表し、[そのオブジェクトの](../../../ado/reference/rds-api/dataspace-object-rds.md) **createObject**メソッドによって返されます。 ObjectProxy クラスには、1つのメソッドがあります。これ**は、サーバー**でメソッドを呼び出し、その呼び出しによって生成されたオブジェクトを返すことができます。  
  
 **パッケージ com.. wfc. データ**  
  
## <a name="methods"></a>メソッド  
  
### <a name="call-method-adowfc-syntax"></a>Call メソッド (ADO/WFC 構文)  
 ObjectProxy によって表されるサーバーでメソッドを呼び出します。 必要に応じて、メソッドの引数をオブジェクトの配列として渡すことができます。  
  
#### <a name="syntax"></a>構文  
  
```  
public Object ObjectProxy.( String method )  
public Object ObjectProxy.( String method, Object[] args)  
```  
  
#### <a name="returns"></a>戻り値  
 Object  
 メソッドを呼び出した結果のオブジェクト。  
  
#### <a name="parameters"></a>パラメーター  
 *ObjectProxy*  
 サーバーを表す**Objectproxy**オブジェクト。  
  
 *b*  
 サーバーで呼び出すメソッドの名前を格納している文字列。  
  
 *value*  
 省略可能。 サーバー上のメソッドの引数であるオブジェクトの配列。 Java のデータ型は、サーバーでの使用に適したデータ型に自動的に変換されます。
