---
author: jnHs
Description: The Reviews report in the Windows Dev Center dashboard lets you see the reviews (comments) that customers entered when rating your app in the Store.
title: レビュー レポート
ms.assetid: E50C3A4D-1D8A-4E5B-8182-3FAD049F2A2D
ms.author: wdg-dev-content
ms.date: 08/16/2018
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: windows 10、uwp、校閲、コメント、校閲者
ms.localizationpriority: medium
ms.openlocfilehash: 8891aecb904f69e3f77ec5892d9234f79db46ff0
ms.sourcegitcommit: c6d6f8b54253e79354f8db14e5cf3b113a3e5014
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2018
ms.locfileid: "2839024"
---
# <a name="reviews-report"></a>レビュー レポート


**レビュー** Windows デベロッパー センターのダッシュ ボードにレポートを使用して、ストアにアプリを評価するとき、お客様が入力されたレビュー (コメント) を表示できます。

このデータは、ダッシュボードで表示することも、[レポートをダウンロード](download-analytic-reports.md) してオフラインで表示することもできます。 または、[分析 REST API を Microsoft ストア](../monetize/access-analytics-data-using-windows-store-services.md)で[アプリのレビューを取得する](../monetize/get-app-reviews.md)方法を使用して、プログラムを使用してこのデータを取得することができます。

お客様のレビュー[このページから直接](respond-to-customer-reviews.md)、プログラムを使用して[、Microsoft ストア レビュー API を使って](../monetize/submit-responses-to-app-reviews.md)、または[デベロッパー センター アプリ](https://www.microsoft.com/store/apps/dev-center/9nblggh4r5ws)を使って応答することもできます。

> [!TIP]
> 左側のナビゲーション メニューで **[Engage] (関心を引く)** を展開して **[レビューとフィードバック]** を選ぶと、自分のすべてのアプリの過去 30 日間のレビュー、評価、ユーザー フィードバックの概要を確認できます。 


## <a name="apply-filters"></a>フィルターを適用

ページの上部で、レビューを表示する期間を選択できます。 既定では **[有効期間]** が選択されていますが、30 日間、3 カ月間、6 か月間、12 か月間のレビューや、指定した任意の期間のデータを表示することもできます。

**[フィルター]** を展開すると、次のオプションを使って、このページに表示するレビューをフィルター処理できます。 これらのフィルターは **[評価の内訳]** と **[長期的な平均評価]** のグラフには、適用されません。

-   **[評価]**: 既定ではすべての星評価のレビューが表示される設定になっていますが、特定の星評価に関連するレビューのみを表示する場合は、特定の評価 (1 ～ 5 つの星) をオンまたはオフにすることができます。
- **コンテンツを確認する**: 既定の設定は、**評価とコンテンツを確認する**ためだけの評価を校閲のコンテンツが表示されます。 **すべて**表示のすべての評価、レビュー記事のいずれかのテキストが含まれていないことも選択できます。 メモの**評価ブレーク ダウン**グラフが自分が選んだ内容に関係なく、すべてのレビューを常に表示されます。
-   **[OS バージョン]**: 既定の設定は **[すべて]** です。 特定の OS バージョンを選ぶと、その OS バージョンを使っているユーザーによるレビューのみをこのページに表示できます。
-   **[パッケージ バージョン]**: 既定の設定は **[すべて]** です。 アプリに複数のパッケージがある場合、ここで特定のパッケージを選ぶと、アプリのレビュー時にそのパッケージを持っていたユーザーによるレビューのみをこのページに表示できます。
-   **[応答]**: 既定の設定は **[すべて]** です。 [ユーザーに返信した](respond-to-customer-reviews.md)レビューのみを表示したり、まだ返信していないレビューのみを表示するには、レビューをフィルター処理できます。
-   **[更新]**: 既定の設定は **[すべて]** です。 レビューをフィルター処理して、[レビューへの返信](respond-to-customer-reviews.md)以降に、ユーザーによって更新されているレビューのみ、または、ユーザーによって更新されていないレビューのみを表示できます。
-   **[市場]**: 既定の設定は **[すべての市場]** です。 このページに特定の市場のユーザーからのレビューのみを表示する場合は、特定の市場を選ぶことができます。
-   **[デバイスの種類]**: 既定のフィルターは **[すべてのデバイス]** です。 このページにその種類のデバイスを使っているユーザーによるレビューのみを表示する場合は、特定のデバイスの種類を選ぶことができます。
-   **[カテゴリ名]**: 既定のフィルターは **[すべて]** です。 のみそのカテゴリに関連付けられているレビューを表示するには、[カテゴリの情報を確認](#review-insight-categories)する特定を選択します。 

> [!TIP]
> このページにレビューが表示されない場合は、フィルターですべてのレビューを除外していないかどうかを確認してください。 たとえば、アプリがサポートされていないターゲット OS でフィルター処理する場合、レビューは表示されません。


## <a name="ratings-breakdown"></a>評価の内訳

次の概要がアクセスできるようにするは、[レポートの上部にある**評価ブレーク ダウン**グラフが表示されます。 
- アプリの平均の星評価。
- 過去 12 か月間のアプリの評価の合計数。
- 各星評価の評価総数。
- 評価の種類 (新着または更新済み) 別に示した、星評価ごとの過去 12 か月間の評価の数。
 - **新しい評価**は、ユーザーが送信し、まったく変更していない評価です。
 - **更新済み評価**は、単にレビューのテキストを変更しただけであっても、何かしらユーザーによって変更されている評価です。

> [!TIP]
> ストア内でユーザーに表示される平均評価では、ユーザーの市場とデバイスの種類が考慮されているため、このレポートに表示される内容と異なる可能性があります。

**評価とコンテンツを確認する****コンテンツを確認する**ページ フィルターで選択した場合でも、[このグラフ常に含まれているすべてのレビューの注意してください。

このグラフは、[評価レポート](ratings-report.md)の詳細については、アプリの評価とも表示できます。


< 範囲 id ="校閲のカテゴリ洞察/>

## <a name="insight-categories"></a>情報のカテゴリ

グラフで**情報カテゴリに分類**グループ化を特定のカテゴリによって、レビューはレビューに関連付けられたにあります。

> [!NOTE]
> カテゴリ別にレビューを表示するときは、24 時間以内のレビューや英語以外の言語でのレビューは含まれません。

ページ上部に、レビューのカテゴリ別に色分けされたブロックが表示されます。 カテゴリの 1 つを選ぶと、そのカテゴリに関連付けられているレビューのみが表示されます。 [ページ フィルター](#apply-filters)を使って、カテゴリを基にフィルターを適用することもできます。

カテゴリごとのレビュー数の内訳を確認するには、**[詳細の表示]** を選びます。 


## <a name="reviews"></a>レビュー

各ユーザー レビューには、次の情報が含まれます。

-   ユーザーが記入したタイトルとレビュー本文  (Windows Phone 8.1 およびそれ以前のユーザーによって作成されたレビューにはタイトルはありません)。
-   レビューの日付。
-   Microsoft ストアにその名前を付けて、校閲者の名前が表示されます。
-   レビューアーの国/地域。
-   レビューが残された時点でのユーザーのデバイス上のアプリのパッケージ バージョン  (この情報はオンラインまたは Windows 8.1 およびそれ以前の顧客から送信されたレビューについては利用できません)。
-   レビューが残されたときにユーザーが使っていたデバイスの OS のバージョン。
-   レビューが残されたときにユーザーが使っていたデバイスの名前  (この情報はオンラインまたは Windows 8.1 およびそれ以前の顧客から送信されたレビューについては利用できません)。
-   他のユーザーがこのレビューを読んだ際に評価される、レビューの "役立ち度" も表示されます。 これらは、2 つの数字のセットで示されます。最初の数字はこのレビューが役に立ったと評価したユーザーの数、2 番目の数字はレビューを評価したユーザーの総数です。 たとえば、役立ち度が "4/10" であった場合、10 人の評価者のうち 4 人はレビューが役立ったと評価し、6 人は役立ったとは評価していないことを意味します。 (レビューに対する役立ち度の評価がない場合、役立ち度は表示されません)。

ユーザーはコメントを追加しなくてもアプリを評価できるため、通常は評価数よりもレビュー数が少なくなります。

このページのレビューは、日付や評価によって昇順または降順に並べ替えることができます。 **日付**または**評価**で並べ替えるにはオプションを表示するのには、**基準にして並べ替える**リンクをクリックします。

アプリのレビューの特定の単語または語句を検索する [検索] ボックスを使用することもできます。 レビューが別の言語で入力された場合でも、元のみが顧客によって書かれたテキストを確認するノートが検索されます。 変換後のレビューのテキストは検索されません。

> [!NOTE]
> 場合によっては、レビューがこのレポートに表示されなくなることがあります。 原因としては、Windows 10 の特定のプレリリース版と Insider ビルドを実行しているお客様によって書き込まれたレビューが、Microsoft によってストアから削除されたことが考えられます。 これは、プレリリース版の Windows ビルドの問題が原因で発生した、否定的なレビューを削除する目的で行われるものです。 また、スパム、不適切、不快感を与えるなどのポリシー違反と見なされたレビューが、Microsoft によってストアから削除される場合もあります。 この操作は、カスタマー エクスペリエンスの改善になることを期待して行われています。


## <a name="translating-reviews"></a>レビューの翻訳

既定では、優先する言語で記述されていないレビューは翻訳されます。 必要に応じて、レビューの一覧の右上にある **[レビューを翻訳する]** チェック ボックスをオフにして、レビューの翻訳を無効にすることができます。

レビューは自動翻訳システムによって翻訳されるため、翻訳の結果が正確でない場合があることに注意してください。 元のテキストと翻訳を比較する場合や、元のテキストを他の方法で翻訳する場合は、元のテキストが提供されます。

前述のように、顧客によって左元のテキストのみを検索、レビューを検索するには、(とテキストを翻訳なく)、**翻訳を確認**] ボックスをオンになっている場合でもします。


## <a name="responding-to-customer-reviews"></a>顧客のレビューへの返信

Microsoft ストア デベロッパー センターのダッシュ ボード、 [Microsoft ストア API をレビューする](../monetize/submit-responses-to-app-reviews.md)、または[デベロッパー センター アプリ](https://www.microsoft.com/store/apps/dev-center/9nblggh4r5ws)を使用するには、お客様のレビューの応答を送信します。 詳しくは、「[顧客のレビューに返信する](respond-to-customer-reviews.md)」をご覧ください。

アプリについて確認した評価とレビューに基づいて検討できるその他の対応を以下に示します。

-   機能の追加または変更を望む意見や、問題に関する不満の声が多数ある場合は、特定のフィードバックに対応した新しいバージョンのリリースを検討します  (その場合は、必ずアプリの[説明](create-app-descriptions.md)を更新して、問題が解決したことを示してください)。
-   平均評価は高いが、ダウンロード数が少ない場合は、アプリを試した人には好評だったことを意味するため、[より多くの人にアプリについて知ってもらう](attract-customers-and-promote-your-apps.md)方法を検討します。


 

 

 