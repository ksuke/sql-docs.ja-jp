---
title: srv_paraminfo (拡張ストアド プロシージャ API) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paraminfo
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paraminfo
ms.assetid: ee2afd4e-0d91-462b-9403-98d481546330
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: f3c89eb2e6f810902e28e01c7e5ffbcdcc0375c7
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "63127186"
---
# <a name="srv_paraminfo-extended-stored-procedure-api"></a>srv_paraminfo (拡張ストアド プロシージャ API)
    
> [!IMPORTANT]  
>  
  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]代わりに CLR Integration をご使用ください。  
  
 パラメーターに関する情報を返します。 この関数は、[srv_paramtype](srv-paramtype-extended-stored-procedure-api.md)、[srv_paramlen](srv-paramlen-extended-stored-procedure-api.md)、[srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md)、および [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md) に代わる関数です。 **srv_paraminfo**では[、データ型と長さ](data-types-extended-stored-procedure-api.md)0 のデータのデータ型がサポートされます。  
  
## <a name="syntax"></a>構文  
  
```  
  
int srv_paraminfo (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbType  
,  
ULONG *  
pcbMaxLen  
,  
ULONG *  
pcbActualLen  
,  
BYTE *  
pbData  
,  
BOOL *  
pfNull  
);  
  
```  
  
## <a name="arguments"></a>引数  
 *srvproc*  
 クライアント接続のためのハンドルです。  
  
 *n*  
 設定するパラメーターの序数です。 最初のパラメーターは 1 です。  
  
 *pbType*  
 パラメーターのデータ型です。  
  
 *pcbMaxLen*  
 パラメーターの最大長へのポインターです。  
  
 *pcbActualLen*  
 パラメーターの実際の長さへのポインターです。 
  \*pfNull* が FALSE に設定されている場合、値 0 (**pcbActualLen* == 0) はデータの長さがゼロであることを示します。  
  
 *pbData*  
 パラメーター データのバッファーへのポインターです。 
  *pbData* が NULL でない場合、拡張ストアド プロシージャ API により \**pbData* に \**pcbActualLen* バイトのデータが書き込まれます。 
  *pbData* が NULL の場合、\**pbData* にデータは書き込まれませんが、関数により \**pbType*、\**pcbMaxLen*、\**pcbActualLen*、**pfNull* が返されます。 このバッファーのメモリは、アプリケーションで管理する必要があります。  
  
 *pfNull*  
 NULL フラグへのポインターです。 *パラメーターの値が NULL の場合、 *Pfnull*は TRUE に設定されます。  
  
## <a name="returns"></a>戻り値  
 パラメーター情報が正常に取得された場合は SUCCEED を返し、それ以外の場合は FAIL を返します。 FAIL が返されるのは、現在のリモート ストアド プロシージャがない場合、および *n* 番目のリモート ストアド プロシージャ パラメーターがない場合です。  
  
## <a name="remarks"></a>解説  
 **セキュリティ**に関する注意拡張ストアドプロシージャのソースコードを十分に確認し、コンパイル済みの Dll を実稼働サーバーにインストールする前にテストする必要があります。 セキュリティの確認およびテストについて詳しくは、[Microsoft の Web サイト](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/)をご覧ください。  
  
## <a name="see-also"></a>参照  
 [拡張ストアド プロシージャのプログラマーズ リファレンス](database-engine-extended-stored-procedures-reference.md)  
  
  
