---
title: sysmail_sentitems (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysmail_sentitems_TSQL
- sysmail_sentitems
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_sentitems database mail view
ms.assetid: 16eb2a44-cebb-4cec-93ac-e2498c39989f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c935a83c3c3fdd9fa577a3232e46caed7865c1c3
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "70745367"
---
# <a name="sysmail_sentitems-transact-sql"></a>sysmail_sentitems (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-asdbmi-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdbmi-xxxx-xxx-md.md)]

  データベースメールによって送信されたメッセージごとに1行のレコードを格納します。 正常に送信されたメッセージを確認するには、 **sysmail_sentitems**を使用します。  
  
 データベースメールによって処理されるすべてのメッセージを表示するには[sysmail_allitems &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sysmail-allitems-transact-sql.md)を使用します。 失敗した状態のメッセージだけを表示するには、 [sysmail_faileditems &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sysmail-faileditems-transact-sql.md)を使用します。 未送信または再試行中のメッセージだけを表示するには、 [sysmail_unsentitems &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sysmail-unsentitems-transact-sql.md)を使用します。 電子メールの添付ファイルを表示するには、 [sysmail_mailattachments &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sysmail-mailattachments-transact-sql.md)を使用します。  
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**mailitem_id**|**int**|メールキュー内のメールアイテムの識別子。|  
|**profile_id**|**int**|メッセージの送信に使用されるプロファイルの識別子。|  
|**recipients**|**varchar(max)**|メッセージの受信者の電子メールアドレス。|  
|**copy_recipients**|**varchar(max)**|メッセージのコピーを受信するユーザーの電子メールアドレス。|  
|**blind_copy_recipients**|**varchar(max)**|メッセージのコピーを受信したが、その名前がメッセージヘッダーに表示されない電子メールアドレス。|  
|**subject**|**nvarchar (510)**|メッセージの件名行。|  
|**部位**|**varchar(max)**|メッセージの本文|  
|**body_format**|**varchar (20)**|メッセージの本文形式。 指定できる値は、 **TEXT**と**HTML**です。|  
|**importance**|**varchar (6)**|メッセージの**重要度**パラメーター。|  
|**区別**|**varchar (12)**|メッセージの**感度**パラメーター。|  
|**file_attachments**|**varchar(max)**|電子メール メッセージに添付されたファイル名の、セミコロン区切りの一覧。|  
|**attachment_encoding**|**varchar (20)**|メールの添付ファイルの種類。|  
|**照会**|**varchar(max)**|メールプログラムによって実行されるクエリ。|  
|**execute_query_database**|**sysname**|メールプログラムによってクエリが実行されたデータベースコンテキスト。|  
|**attach_query_result_as_file**|**bit**|値が0の場合、クエリ結果は、本文の内容の後に電子メールメッセージの本文に含まれていました。 値が 1 の場合、結果が添付ファイルとして返されたことを示します。|  
|**query_result_header**|**bit**|値が1の場合、クエリ結果には列ヘッダーが含まれます。 値が 0 の場合、クエリの結果に列のヘッダーが含まれていないことを示します。|  
|**query_result_width**|**int**|メッセージの**query_result_width**パラメーター。|  
|**query_result_separator**|**char (1)**|クエリの出力で列の区切りに使用された文字。|  
|**exclude_query_output**|**bit**|メッセージの**exclude_query_output**パラメーター。 詳細については、「 [sp_send_dbmail &#40;transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-send-dbmail-transact-sql.md)」を参照してください。|  
|**append_query_error**|**bit**|メッセージの**append_query_error**パラメーター。 0 は、クエリにエラーがあった場合、データベース メールで電子メール メッセージが送信されないことを示します。|  
|**send_request_date**|**DATETIME**|メッセージがメールキューに置かれた日付と時刻。|  
|**send_request_user**|**sysname**|メッセージを送信したユーザー。 これは、メッセージの From: フィールドではなく、データベースメールプロシージャのユーザーコンテキストです。|  
|**sent_account_id**|**int**|メッセージの送信に使用されるデータベースメールアカウントの識別子。|  
|**sent_status**|**varchar (8)**|メールの状態。 常にこのビューに**送信され**ます。|  
|**sent_date**|**DATETIME**|メッセージが送信された日時。|  
|**last_mod_date**|**DATETIME**|行が最後に変更された日付と時刻。|  
|**last_mod_user**|**sysname**|行を最後に変更したユーザー。|  
  
## <a name="remarks"></a>解説  
 データベースメールのトラブルシューティングを行うときに、このビューは、正常に送信されたメッセージの属性を表示することによって、問題の性質を特定するのに役立ちます。 データベースメールは、SMTP メールサーバーに正常に送信されたときにメッセージを送信済みとしてマークします。 通常、電子メールは数分のうちに相手側に届きますが、SMTP サーバーの問題が原因で遅れることもあります。 データベースメールは、SMTP メールサーバーによって受け付けられたときにメッセージを送信済みとしてマークします。 受信者の電子メール アドレスに配信できないなど、SMTP メール サーバーで発生する電子メール エラーは、データベース メールには返されません。 これらの電子メールは、配信されていない場合でも、送信済みとして記録されます。 SMTP サーバーでのエラーのトラブルシューティングを行います。 また、SMTP メールサーバーは、データベースメールアカウントの返信用電子メールアドレスに配信不能メッセージ通知を送信する場合があります。  
  
## <a name="permissions"></a>アクセス許可  
 **Sysadmin**固定サーバーロールおよび**databasemailuserrole**データベースロールに付与されます。 **Sysadmin**固定サーバーロールのメンバーによって実行されると、このビューには、送信されたすべてのメッセージが表示されます。 その他のユーザーの場合は、自分が送信したメッセージだけを確認できます。  
  
## <a name="see-also"></a>参照  
 [データベース メール メッセージング オブジェクト](../../relational-databases/database-mail/database-mail-messaging-objects.md)  
  
  
