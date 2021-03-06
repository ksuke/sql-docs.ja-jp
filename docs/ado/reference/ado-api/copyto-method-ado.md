---
title: CopyTo メソッド (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Stream::raw_CopyTo
- _Stream::CopyTo
helpviewer_keywords:
- CopyTo method [ADO]
ms.assetid: b4aa5714-916b-48b8-8b09-cc2708379602
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 25d57116e1fa24658d62a0c9083e00a3e320d2a8
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67933372"
---
# <a name="copyto-method-ado"></a>CopyTo メソッド (ADO)
[ストリーム](../../../ado/reference/ado-api/stream-object-ado.md)内の指定した文字数またはバイト数 ([型](../../../ado/reference/ado-api/type-property-ado-stream.md)によって異なる) を別の**ストリーム**オブジェクトにコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
  
Stream.CopyTo DestStream, NumChars  
```  
  
#### <a name="parameters"></a>パラメーター  
 *DestStream*  
 開いている**ストリーム**オブジェクトへの参照を含むオブジェクト変数の値です。 現在の**ストリーム**は、 *deststream*によって指定されたコピー先**ストリーム**にコピーされます。 コピー先の**ストリーム**は既に開いている必要があります。 それ以外の場合は、実行時エラーが発生します。  
  
> [!NOTE]
>  *Deststream*パラメーターを**ストリーム**オブジェクトのプロキシにすることはできません。これは、クライアントにリモート接続できない**ストリーム**オブジェクトのプライベートインターフェイスにアクセスする必要があるためです。  
  
 *NumChars*  
 省略可能。 ソース**ストリーム**内の現在位置からコピー先の**ストリーム**にコピーするバイト数または文字数を指定する**整数**値。 既定値は-1 です。これは、すべての文字またはバイトが現在の位置から[EOS](../../../ado/reference/ado-api/eos-property.md)にコピーされることを指定します。  
  
## <a name="remarks"></a>解説  
 このメソッドは、 [position](../../../ado/reference/ado-api/position-property-ado.md)プロパティによって指定された現在位置を起点として、指定された文字数またはバイト数をコピーします。 指定された数が**eos**までの使用可能なバイト数を超えている場合は、現在の位置から**eos**までの文字またはバイトだけがコピーされます。 *Numchars*の値が-1 であるか省略されている場合は、現在の位置から始まるすべての文字またはバイトがコピーされます。  
  
 コピー先のストリームに既存の文字またはバイトが含まれている場合、コピーが終了した時点以降のすべてのコンテンツは切り捨てられません。 **位置**は、コピーされた最後のバイトの直後のバイトになります。 これらのバイトを切り捨てる場合は、 [SetEOS](../../../ado/reference/ado-api/seteos-method.md)を呼び出します。  
  
 **CopyTo**は、ソース**ストリーム**と同じ型のコピー先**ストリーム**にデータをコピーする場合に使用する必要があります (その**type**プロパティ設定は、 **adTypeText**または両方**adtypebinary**です)。 テキスト**ストリーム**オブジェクトの場合は、変換先**ストリーム**の[Charset](../../../ado/reference/ado-api/charset-property-ado.md)プロパティ設定を変更して、ある文字セットから別の文字セットに変換することができます。 また、テキスト**ストリーム**オブジェクトはバイナリ**ストリーム**オブジェクトに正常にコピーできますが、バイナリ**ストリーム**オブジェクトをテキスト**ストリーム**オブジェクトにコピーすることはできません。  
  
## <a name="applies-to"></a>適用対象  
 [Stream オブジェクト (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)
