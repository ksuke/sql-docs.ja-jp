---
title: JDBC ドライバーの JDBC 4.2 への準拠 | Microsoft Docs
ms.custom: ''
ms.date: 08/12/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 36025ec0-3c72-4e68-8083-58b38e42d03b
author: MightyPen
ms.author: genemi
ms.openlocfilehash: fb9ab0375c1d718b9559b3c85acc0b3ba4f6993b
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "69027980"
---
# <a name="jdbc-42-compliance-for-the-jdbc-driver"></a>JDBC ドライバーの JDBC 4.2 への準拠

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

> [!NOTE]  
> Microsoft JDBC Driver 4.2 for SQL Server より前のバージョンのドライバーは、Java Database Connectivity API 4.0 仕様に準拠しています。 このセクションは、4.2 リリースより前のバージョンには適用されません。  
  
 Java Database Connectivity API 4.2 仕様は Microsoft JDBC Driver 4.2 for SQL Server によってサポートされ、以下の API メソッドが実装されています。  
  
## <a name="sqlserverstatement-class"></a>SQLServerStatement クラス
  
|新しいメソッド|説明|注目に値する実装|  
|-----------------|-----------------|-------------------------------|  
|long[] executeLargeBatch()|バッチを実行します。返される更新数は long 型が可能です。|Java.sql.Statement インターフェイスの説明に従って実装されています。 詳細については、「[java.sql.Statement](https://docs.oracle.com/javase/8/docs/api/java/sql/Statement.html#executeLargeBatch--)」をご覧ください。|  
|long executeLargeUpdate(String sql)<br /><br /> long executeLargeUpdate(String sql, int autoGeneratedKeys)<br /><br /> long executeLargeUpdate(String sql, int[] columnIndexes)<br /><br /> executeLargeUpdate(String sql, String[] columnNames)|DML/DDL ステートメントを実行します。返される更新数は long 型が可能です。 long 型の更新数をサポートする 4 つの新しい (オーバーロードされた) メソッドがあります。|Java.sql.Statement インターフェイスの説明に従って実装されています。 詳細については、「[java.sql.Statement](https://docs.oracle.com/javase/8/docs/api/java/sql/Statement.html#executeLargeBatch--)」をご覧ください。|  
|long getLargeMaxRows()|ResultSet に含めることができる行の最大数を long 型の値として取得します。|SQL Server は、最大行数として整数の制限値のみをサポートしています。 詳細については、「[java.sql.Statement](https://docs.oracle.com/javase/8/docs/api/java/sql/Statement.html#executeLargeBatch--)」をご覧ください。|  
|long getLargeUpdateCount()|現在の結果を long 型の更新数として取得します。|SQL Server は、最大行数として整数の制限値のみをサポートしています。 詳細については、「[java.sql.Statement](https://docs.oracle.com/javase/8/docs/api/java/sql/Statement.html#executeLargeBatch--)」をご覧ください。|  
|void setLargeMaxRows(long max)|ResultSet に含めることができる行の最大数を long 型の値として設定します。|SQL Server は、最大行数として整数の制限値のみをサポートしています。 パラメーターとして最大の整数値より大きいサイズを渡すと、このメソッドは、非サポート例外をスローします。 詳細については、「[java.sql.Statement](https://docs.oracle.com/javase/8/docs/api/java/sql/Statement.html#executeLargeBatch--)」をご覧ください。|  
  
## <a name="sqlservercallablestatement-class"></a>SQLServerCallableStatement クラス  
  
|新しいメソッド|説明|注目に値する実装|  
|-----------------|-----------------|-------------------------------|  
|void registerOutParameter(int parameterIndex, SQLType sqlType)<br /><br /> void registerOutParameter(int parameterIndex, SQLType sqlType, int scale)<br /><br /> void registerOutParameter(int parameterIndex, SQLType sqlType, String typeName)<br /><br /> void registerOutParameter(String parameterName, SQLType sqlType)<br /><br /> void registerOutParameter(String parameterName, SQLType sqlType, int scale)<br /><br /> registerOutParameter(String parameterName, SQLType sqlType, String typeName)|OUT パラメーターを登録します。 新しい SQLType インターフェイスをサポートする 6 個の新しい (オーバーロードされた) メソッドがあります。|java.sql.CallableStatement インターフェイスの説明に従って実装されています。 詳細については、「[java.sql.CallableStatement](https://docs.oracle.com/javase/8/docs/api/java/sql/CallableStatement.html)」をご覧ください。|  
|void setObject(String parameterName, Object x, SQLType targetSqlType)<br /><br /> void setObject(String parameterName, Object x, SQLType targetSqlType, int scaleOrLength)|パラメーターの値を、指定したオブジェクトで設定します。 新しい SQLType インターフェイスをサポートする 2 つの新しい (オーバーロードされた) メソッドがあります。|java.sql.CallableStatement インターフェイスの説明に従って実装されています。 詳細については、「[java.sql.CallableStatement](https://docs.oracle.com/javase/8/docs/api/java/sql/CallableStatement.html)」をご覧ください。|  
  
## <a name="sqlserverpreparedstatement-class"></a>SQLServerPreparedStatement クラス
  
|新しいメソッド|説明|注目に値する実装|  
|-----------------|-----------------|-------------------------------|  
|long executeLargeUpdate()|DML/DDL ステートメントを実行し、long 型の更新数を返します。|java.sql.PreparedStatement インターフェイスの説明に従って実装されています。 詳細については、「[java.sql.PreparedStatement](https://docs.oracle.com/javase/8/docs/api/java/sql/PreparedStatement.html)」をご覧ください。|  
|void setObject(int parameterIndex, Object x, SQLType targetSqlType)<br /><br /> void setObject(int parameterIndex, Object x, SQLType targetSqlType, int scaleOrLength)|パラメーターの値を、指定したオブジェクトで設定します。 新しい SQLType インターフェイスをサポートする 2 つの新しい (オーバーロードされた) メソッドがあります。|java.sql.PreparedStatement インターフェイスの説明に従って実装されています。 詳細については、「[java.sql.PreparedStatement](https://docs.oracle.com/javase/8/docs/api/java/sql/PreparedStatement.html)」をご覧ください。|  
  
## <a name="sqlserverdatabasemetadata-class"></a>SQLServerDatabaseMetaData クラス
  
|新しいメソッド|説明|注目に値する実装|  
|-----------------|-----------------|-------------------------------|  
|long getMaxLogicalLobSize()|このデータベースで LOB の論理サイズとして許容される最大バイト数を取得します。|SQL Server では、この値は 2^31-1 です。 詳細については、「[java.sql.DatabaseMetaData](https://docs.oracle.com/javase/8/docs/api/java/sql/DatabaseMetaData.html)」をご覧ください。|  
|boolean supportsRefCursors()|このデータベースが REF CURSOR をサポートするかどうかを取得します。|SQL Server は false を返し、REF CURSOR をサポートしていません。 詳細については、「[java.sql.DatabaseMetaData](https://docs.oracle.com/javase/8/docs/api/java/sql/DatabaseMetaData.html)」をご覧ください。|  
  
## <a name="sqlserverresultset-class"></a>SQLServerResultSet クラス
  
||||  
|-|-|-|  
|新しいメソッド|説明|注目に値する実装|  
||指定した列を Object 値で更新します。 新しい SQLType インターフェイスをサポートする 4 つの新しい (オーバーロードされた) メソッドがあります。|java.sql.ResultSet インターフェイスの説明に従って実装されています。 詳細については、「[java.sql.ResultSet](https://docs.oracle.com/javase/8/docs/api/java/sql/ResultSet.html)」をご覧ください。|  
  
 Java Database Connectivity API 4.2 仕様は Microsoft JDBC Driver 4.2 for SQL Server によってサポートされ、以下のようにデータ型がマッピングされています。  
  
|||  
|-|-|  
|新しいデータ型のマッピング|説明|  
|**Java 8 の新しい Java クラス:** <br /> <br /> LocalDate/LocalTime/LocalDateTime<br /><br /> OffsetTime/OffsetDateTime<br /><br /> **新しい JDBC の型:**<br /><br /> TIME_WITH_TIMEZONE<br /><br /> TIMESTAMP_WITH_TIMEZONE<br /><br /> REF_CURSOR|SQL Server では、REF_CURSOR はサポートされていません。 この型を使用すると、ドライバーは SQLFeatureNotSupportedException 例外をスローします。 その他のすべての新しい Java 型および JDBC 型のマッピングは、JDBC 4.2 仕様で指定されているとおりにサポートされます。|  
