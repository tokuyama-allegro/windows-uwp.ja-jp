---
title: MultiplayerSessionRequest (JSON)
assetID: 2e311c6d-3427-5a39-1989-06dc08483057
permalink: en-us/docs/xboxlive/rest/json-multiplayersessionrequest.html
author: KevinAsgari
description: " MultiplayerSessionRequest (JSON)"
ms.author: kevinasg
ms.date: 20-12-2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: Xbox Live, Xbox, ゲーム, UWP, Windows 10, Xbox One
ms.localizationpriority: medium
ms.openlocfilehash: d7c2cb3ca95524b49ea6e0cbe14771036a3e6925
ms.sourcegitcommit: 63cef0a7805f1594984da4d4ff2f76894f12d942
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "4386069"
---
# <a name="multiplayersessionrequest-json"></a>MultiplayerSessionRequest (JSON)
**MultiplayerSession**オブジェクト上の操作に対して要求の JSON オブジェクトが渡されます。 
<a id="ID4EQ"></a>

  
 
MultiplayerSessionRequest JSON オブジェクトには、次の仕様があります。
 
| メンバー| 種類| 説明| 
| --- | --- | --- | 
| 定数| object| セッションの定数を生成するセッション テンプレートと結合された読み取り専用の設定。 | 
| プロパティ | object | セッションのプロパティへの結合を変更します。| 
| members.me | object| 定数と動作の多くのプロパティなどのトップレベルの相当します。 PUT メソッドでは、ユーザーが、セッションのメンバーである必要があり、必要に応じて、ユーザーを追加します。 "Me"が null として指定されている場合は、要求を行っているメンバーがセッションから削除されます。 | 
| メンバー | object| 0 から始まるインデックスでキーを持つ、セッションに追加するユーザーを表すその他のオブジェクトです。 既にセッションには、メンバーが含まれている場合でも、要求のメンバーの数は常に 0 で始まります。 メンバーは、要求で表示される順序でセッションに追加されます。 メンバーのプロパティは、先に属しているユーザーでのみ設定できます。 | 
| サーバー | object| 関連付けられているサーバーの参加者のセットに更新プログラムと、セッションに追加されたことを示す値。 サーバーが null として指定されている場合、そのサーバーのエントリは、セッションから削除されます。 | 
  
<a id="ID4EZ"></a>

 
## <a name="request-structure"></a>要求の構造
 

```json
{
  "constants": { /* Property Bag */ },
  "properties": { /* Property Bag */ },
  "members": {
    // Requires a service principal. Existing members can be deleted by index.
    // Not available on large sessions.
    "5": null,

    // Reservation requests must start with zero. New users will get added in order to the end of the session's member list.
    // Large sessions don't support reservations.
    "reserve_0": {
      "constants": { /* Property Bag */ }
    },
    "reserve_1": {
      "constants": { /* Property Bag */ }
    },

    // Requires a user principal with a xuid claim. Can be 'null' to remove myself from the session.
    "me": {
      "constants": { /* Property Bag */ },
      "properties": { /* Property Bag */ },
    }
  },

  // Requires a server principal.
  "servers": {
    // Can be any name. The value can be 'null' to remove the server from the session.
    "name": {
      "constants": {  /* Property Bag */ },
      "properties": {  /* Property Bag */ }
    }
  }
}
```

  
<a id="ID4EAB"></a>

 
## <a name="see-also"></a>関連項目
 
<a id="ID4ECB"></a>

 
##### <a name="parent"></a>Parent 

[JavaScript Object Notation (JSON) オブジェクト リファレンス](atoc-xboxlivews-reference-json.md)

  
<a id="ID4EMB"></a>

 
##### <a name="reference"></a>リファレンス 

[MultiplayerSession (JSON)](json-multiplayersession.md)

 [PUT (/serviceconfigs/{scid}/sessiontemplates/{sessionTemplateName}/sessions/{sessionName})](../uri/sessiondirectory/uri-serviceconfigsscidsessiontemplatessessiontemplatenamesessionssessionnameput.md)

   