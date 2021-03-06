---
title: 顧客のフィードバックに返信する
description: 顧客がフィードバック Hub に入力したフィードバックに直接返信できます。
ms.date: 10/31/2018
ms.topic: article
keywords: windows 10, uwp
ms.assetid: 04983b80-2a18-4ace-93d3-e8c33c04bfb9
ms.localizationpriority: medium
ms.openlocfilehash: 9bc305834381fcdddac6e4eacf12144fd9f189c2
ms.sourcegitcommit: b52ddecccb9e68dbb71695af3078005a2eb78af1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74259943"
---
# <a name="respond-to-customer-feedback"></a>顧客のフィードバックに返信する

[フィードバック レポート](feedback-report.md)を使用して、Windows 10 のユーザーがフィードバック Hub で入力したアプリ関連のフィードバックを確認し、そのフィードバックに直接返信することができます。 フィードバック Hub ですべてのユーザー向けに返信を投稿 (単独のコメントとして投稿したり、特定のフィードバックのステータスを更新して説明を追加するなど) すると、新機能やバグ修正に関する情報を顧客に通知したり、アプリの改善方法に関するより詳細なフィードバックを募ることができます。 また、フィードバックを入力した顧客への返信を、メールとして直接送信することもできます。

> [!TIP]
> [Microsoft Store Services SDK](https://marketplace.visualstudio.com/items?itemName=AdMediator.MicrosoftStoreServicesSDK) 内の Feedback API を使用してコントロールを追加し、顧客が直接 [UWP アプリからフィードバック Hub を起動](../monetize/launch-feedback-hub-from-your-app.md)できるようにすることで、顧客からのフィードバック提供を促進することもできます。 フィードバック Hub をサポートする Windows 10 デバイスにアプリをダウンロードしたユーザーはだれでも、フィードバック Hub アプリを通じて直接フィードバックを残すことができます。 このため、アプリ内でフィードバックを特に募集していない場合でも、このレポートでユーザーからのフィードバックが表示される場合があります。

フィードバックに返信するには、 **[フィードバック] レポート**でフィードバックをクリックし、表示される **[フィードバックに返信する]** リンクをクリックします。

[パートナーセンター](https://partner.microsoft.com/dashboard)では、アプリに関するフィードバックを提供する顧客に応答するための3つのオプションがサポートされています。 いずれの方法を選択した場合も、1 回の返信につき 1000 文字の文字数制限があるので注意してください。

## <a name="public-comments-in-feedback-hub"></a>フィードバック Hub での公開コメント

既定では、 **[フィードバックに返信する]** をクリックした後、 **[コメント]** のラジオ ボタンはオンになっています。 顧客のフィードバックに対して公開の返信を投稿するには、このボタンをオンのままにします。 ボックスにコメントを入力した後、 **[送信]** をクリックします。

入力したコメントは、その他の顧客から送信されたコメントと共に、フィードバック Hub にコメントとして表示されます。 コメントを入力した開発者が分かるよう、コメントと共に発行元名とアプリ名も表示されます。 フィードバックに対して書き込めるコメント数に制限はありませんが、送信後にコメントを編集したり、削除することはできません。 **[フィードバック] レポート** (およびフィードバック Hub) では、各フィードバックについて直近 5 件のコメントが表示されます。 コメントが 5 件以上ある場合は、 **[すべてのコメントの表示]** をクリックすると、フィードバック Hub にすべてのコメントが表示されます。


## <a name="private-responses-via-email"></a>メールでの非公開返信

返信を公開で投稿したくない場合、 **[コメントをメールで送信]** チェックボックスをオンにすると、非公開の返信を顧客に直接送信できます (顧客がメール アドレスを入力していて、かつ返信のメール受信をオプトアウトしていない場合)。 これをオンにした場合、Microsoft があなたに代わって顧客へのメールを送信します。 このメールには、元のフィードバックとあなたが書き込んだ返信内容が記述されます。

**[コメントをメールで送信]** ボックスをオンにしたら、コメントを入力し、 **[送信]** をクリックします。 このオプションを使用する場合は、 **[サポート連絡先のメール アドレス]** フィールドにメール アドレスを入力する必要があります。 既定では、アカウントの連絡先情報として入力されたメール アドレスが使用されます。 別のメール アドレスを使用する場合は、 **[サポート連絡先のメール アドレス]** フィールドの内容を別の名前に更新できます。 返信を受け取った顧客は、このメール アドレスに直接返事を返すことができます。


## <a name="public-status-updates-and-descriptions-in-feedback-hub"></a>フィードバック Hub での公開ステータスの更新と説明

公開の返信に関する 3 つ目のオプションとして、特定のフィードバックのステータスを設定することができます。これにより、問題に対応中であることや、問題が修正されたことを顧客に知らせることができます。 特定のフィードバックのステータスを更新すると、フィードバック Hub 内の該当するフィードバックにそのステータスが表示されます。

このオプションを使用するには、 **[ステータスの更新]** ラジオ ボタンをオンにします。 その後、次のいずれかのオプションを選択します。

- **調査中**: 問題を認識しており、現在調査中であることを示します。
- **処理中**: 問題を修正しているか、要求された機能を追加している途中であることを示します。
- **完了**: 問題を修正するか、要求された機能を追加するためのアップデートが既に公開されていることを示します。

ステータスを更新するだけでなく、コメントを入力して、問題修正にかかる時間の見積りや、最新の変更点についての詳しい情報を提供することができます。 この説明は、コメント一覧の上部に表示されます (また [フィードバック] レポートにも、現在のステータスと説明が表示されます)。

**[ステータスの更新]** オプションを使用すると、ステータス (および各ステータス変更に関する最新の説明) をいつでも変更できます。 フィードバックのステータスを変更するとフィードバック Hub でステータスが更新されるので、返信を見たユーザーが最新のステータスを確認できます。


## <a name="guidelines-for-responses"></a>返信のガイドライン

顧客のフィードバックへの返信にどの方法を使用するとしても、すべての返信について、以下のガイドラインに従う必要があります。
- 返信は 1,000 文字以内である必要があります。
- 顧客の公開コメントに対する補償 (デジタル アプリ アイテムなど) を提供することは、一切認められていません。
- 返信にマーケティング的な内容や広告を含めないでください。 フィードバックを入力した個人は、既にあなたの顧客です。
- 返信で他のアプリやサービスを宣伝しないでください。
- 返信は、特定のアプリおよびフィードバックに直接関係したものにしてください。
- 品位を欠いたコメントや、攻撃的、個人的、あるいは悪意のあるコメントを、返信に記載しないでください。 常に礼儀正しさを保つようにしてください。また、満足した顧客はアプリの最も重要な推薦人となるということを忘れないでください。

> [!NOTE]
> 顧客は、開発者から不適切なフィードバック返信を受け取った場合、そのことを Microsoft に報告できます。 また顧客は、メールによるフィードバック返信の受信をオプトアウトすることもできます。

顧客との関係はお客様の責任です。 開発者と顧客との間の係争に Microsoft は関与しません。 ただし、顧客からの製品のフィードバック内容が不適切であると思われる場合は、[サポート チケット](https://developer.microsoft.com/windows/support)を送信してください。
