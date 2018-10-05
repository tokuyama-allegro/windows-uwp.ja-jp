---
title: GET (/public/scids/{scid}/clips)
assetID: 15b3e873-1f96-b1da-2f79-6dac1369a4c0
permalink: en-us/docs/xboxlive/rest/uri-publicscidclipsget.html
author: KevinAsgari
description: " GET (/public/scids/{scid}/clips)"
ms.author: kevinasg
ms.date: 20-12-2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: Xbox Live, Xbox, ゲーム, UWP, Windows 10, Xbox One
ms.localizationpriority: medium
ms.openlocfilehash: b945427118122e3b6d52210efc5e1de84a8c8d68
ms.sourcegitcommit: 63cef0a7805f1594984da4d4ff2f76894f12d942
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "4383737"
---
# <a name="get-publicscidsscidclips"></a>GET (/public/scids/{scid}/clips)
パブリック クリップを一覧表示します。 この URI のドメインが`gameclipsmetadata.xboxlive.com`します。
 
  * [注釈](#ID4EV)
  * [URI パラメーター](#ID4ECB)
  * [クエリ文字列パラメーター](#ID4ENB)
 
<a id="ID4EV"></a>

 
## <a name="remarks"></a>注釈
 
この API は、さまざまな方法は、パブリック一覧クリップにできます。 クリップの一覧に基づいて返されたプライバシー チェックと要求元の XUID に対してコンテンツの分離チェックします。
 
クエリは、サービス構成 id (SCID) ごとに最適化されます。 さらにフィルターを使ってまたは以下に示す既定値以外の並べ替え順序を指定するいくつかの状況で長い時間がかかるに戻ります。 これは、ビデオの大きなセットのより顕著です。 クエリでは、昇順の並べ替え順序を指定できません。
 
修飾子は、公開のクリップを特定のコレクションを取得する必要があります。 要求元のユーザーに要求された SCID にアクセスする必要があります、そうしないと http/403 が返されます。
  
<a id="ID4ECB"></a>

 
## <a name="uri-parameters"></a>URI パラメーター
 
| パラメーター| 型| 説明| 
| --- | --- | --- | 
| scid| string| パブリック クリップの主要なサービス構成の識別子です。| 
| タイトル id| string| パブリック クリップのタイトル Id。 SCID と同じ URI で指定することはできません。 指定した場合はプライマリー SCID を検索するために使用されます。| 
  
<a id="ID4ENB"></a>

 
## <a name="query-string-parameters"></a>クエリ文字列パラメーター
 
| パラメーター| 型| 説明| 
| --- | --- | --- | --- | --- | --- | 
| <b>? achievementId = {achievementId}</b>| 最新のクリップが指定した<b>achievementId</b>に一致します。| 追加の並べ替え/フィルタ リングはサポートされていません。| 
| <b>? greatestMomentId = {greatestMomentId}</b>| 最新のクリップが指定した<b>greatestMomentId</b>に一致します。| 追加の並べ替え/フィルタ リングはサポートされていません。| 
| <b>? 修飾子 = 作成 </b>| Most Recent| 必須。| 
  
<a id="ID4EDD"></a>

 
## <a name="see-also"></a>関連項目
 
<a id="ID4EFD"></a>

 
##### <a name="parent"></a>Parent 

[/public/scids/{scid}/clips](uri-publicscidclips.md)

   