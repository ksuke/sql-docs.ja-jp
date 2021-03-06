---
title: SQL 型識別子 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data types [ODBC], identifiers
- SQL data types [ODBC], identifiers
- type identifiers [ODBC], SQL
- identifiers [ODBC], SQL type
- SQL type identifiers [ODBC]
ms.assetid: 22f6793b-2f43-4281-b35a-28f48e504dd8
author: MightyPen
ms.author: genemi
ms.openlocfilehash: be36bd8efc059c1a4f9b5ddf2cdd7faf32cf7dd4
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68107449"
---
# <a name="sql-type-identifiers"></a>SQL の型識別子
各データソースは、独自の SQL データ型を定義します。 ODBC では、型識別子を定義し、各型識別子にマップされる可能性がある SQL データ型の一般的な特性について説明します。 これは、基になるデータソースの各データ型が ODBC の SQL 型識別子にマップされる方法によって異なります。  
  
 たとえば、SQL_CHAR は固定長の文字列の型識別子であり、通常は 1 ~ 254 文字です。 これらの特性は、多くの SQL データソースで検出された CHAR データ型に対応しています。 このため、アプリケーションは、列の型識別子が SQL_CHAR ことを検出すると、CHAR 型の列を処理している可能性があると考えられます。 ただし、列のバイト長が 1 ~ 254 文字であることを前提としています。たとえば、SQL 以外のデータソースのドライバーは、完全一致ではないため、500文字の固定長文字列を SQL_CHAR または SQL_LONGVARCHAR にマップする場合があります。  
  
 ODBC では、さまざまな種類の SQL 型識別子が定義されています。 ただし、ドライバーはこれらの識別子をすべて使用する必要はありません。 代わりに、基になるデータソースでサポートされている SQL データ型を公開するために必要な識別子だけを使用します。 基になるデータソースが、型識別子が一致しない SQL データ型をサポートしている場合、ドライバーは追加の型識別子を定義できます。 詳細については、「[ドライバー固有のデータ型、記述子の型、情報の種類、診断の種類、および属性](../../../odbc/reference/develop-app/driver-specific-data-types-descriptor-information-diagnostic.md)」を参照してください。  
  
 SQL 型識別子の詳細については、「付録 D: データ型」の「 [C データ型](../../../odbc/reference/appendixes/c-data-types.md)」を参照してください。
