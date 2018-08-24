---
author: jnHs
Description: The Health report in the Windows Dev Center dashboard lets you get data related to the performance and quality of your app, including crashes and unresponsive events.
title: '[正常性] レポート'
ms.assetid: 4F671543-1E91-4E59-88A3-638E3E64539A
ms.author: wdg-dev-content
ms.date: 06/01/2018
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: windows 10, uwp, 正常性, クラッシュ, 応答停止イベント, アプリの正常性, 正常性データ, スタック トレース, cab ファイル, 失敗, エラー, pdb, シンボル
ms.localizationpriority: medium
ms.openlocfilehash: 5f5bf63eae4b1504642e764265a7936bcd67c645
ms.sourcegitcommit: c6d6f8b54253e79354f8db14e5cf3b113a3e5014
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2018
ms.locfileid: "2843714"
---
# <a name="health-report"></a>[正常性] レポート

Windows デベロッパー センター ダッシュボードの**状態**レポートによって、クラッシュや応答停止イベントなど、アプリの品質とパフォーマンスに関連するデータを取得できます。 このデータは、ダッシュボードで表示することも、[レポートをダウンロード](download-analytic-reports.md)してオフラインで表示することもできます。 該当する場合、さらにデバッグのスタック トレースや CAB ファイルを表示できます。

または、[Microsoft Store 分析 REST API](../monetize/access-analytics-data-using-windows-store-services.md) を使って、プログラムによりこのレポートのデータを取得することもできます。


## <a name="apply-filters"></a>フィルターの適用

ページの上部で、データを表示する期間を選択できます。 既定では **[72 時間]** が選択されていますが、**[30 日間]** を選んで過去 30 日間のデータを表示することもできます。 **30 D**ビューの UTC と**72 H**ビューのローカル タイム ゾーンでのデータが表示されるように注意してください。

このページにある **[フィルター]** を展開して、このページのすべてのデータをパッケージ バージョンや市場、デバイスの種類を基にフィルター処理できます。

-   **[パッケージ バージョン]**: 既定の設定は **[すべて]** です。 アプリに複数のパッケージが含まれる場合、ここで特定のパッケージを選ぶことができます。
-   **[市場]**: 既定のフィルターは **[すべての市場]** ですが、特定の 1 つまたは複数の市場のデータのみを抽出することもできます。
-   **[デバイスの種類]**: 既定の設定は **[すべて]** ですが、特定の 1 つのデバイスの種類のデータのみを表示することもできます。 **[その他]** というカテゴリに含まれているデバイスは、製造元/モデルを認識できても、このフィルターに示される定義済みの製造元/モデルのいずれかに含めることができないものです。 これらのデバイスについては、**[エラーの詳細]** レポートの **[エラー ログ]** セクションでデバイス モデルを確認できます。  
-   **[OS バージョン]**: 既定値は **[すべての OS バージョン]** ですが、特定の OS バージョンを選ぶこともできます。
-   **[OS リリース バージョン]**: 既定値は **[すべての OS リリース バージョン]** ですが、選択された **[OS バージョン]** の特定リリース バージョンを選ぶこともできます。
-   **[サンドボックス]**: 既定値は **[製品]** ですが、複数の開発サンドボックスを使用している製品 (Xbox Live に統合できるゲームなど) の場合は、特定のサンドボックスをここで選択できます。 (製品にサンドボックスを使用していない場合、このフィルターには **[製品]** のみが表示され、適用されません。)
-   **[アーキテクチャ]**: 既定値は **[すべてのアーキテクチャ]** ですが、特定のシステム アーキテクチャの種類を選ぶこともできます。 このフィルターは、**[30 日間]** が選択されている場合にのみ使用できます。
-   **[PRAID]**: 既定の設定は **[すべて]** ですが、アプリ パッケージを作成するときに複数のパッケージ相対アプリ ID (PRAID) を定義した場合は、1 つの PRAID に関連するデータのみを表示することもできます。 複数の PRAID を定義していない場合、このフィルターは表示されません。

以下のすべてのグラフで、指定した期間とフィルターに応じた情報が表示されます。 セクションの中には、追加のフィルターを適用できるものもあります。


## <a name="failure-hits"></a>Failure hits (エラーのヒット数)

**[Failure hits] (エラーのヒット数)** のグラフには、選んだ期間中にユーザーがアプリを使用したときに発生した 1 日のクラッシュとイベントの数が表示されます。 各アプリで発生した各種のイベント (クラッシュ、ハング、JavaScript の例外、メモリ エラー) は個別に追跡されます。

**30 D**期間が選択されている場合は、円記号が表示されます。 これらは大幅に増加を表す増減内の指定された値を知りたいと思います。 円を表示する日付が大幅に増加または減少前に、その曜日と比較してを検出して週の最後を表します。 詳細については、変更内容を表示するには、円をマウスでポイントします。  

> [!TIP]
> [分析レポート](insights-report.md)の最後の 30 日間の大きな変更に関連する他の情報を表示することができます。

## <a name="failure-hits-by-market"></a>[Failure hits by market] (市場別のエラーのヒット数)

**[Failure hits by market] (市場別のエラーのヒット数)** のグラフには、選んだ期間中に発生した市場別のクラッシュとイベントの合計数が表示されます。

このデータは**マップ** フォームで視覚化して表示することも、設定を切り替えて**テーブル** フォームで表示することもできます。 テーブル フォームでは一度に 5 つの市場を表示でき、アルファベット順か、ユーザー セッション数の多い順か少ない順で並べ替えることができます。 また、データをダウンロードして、すべての市場の情報をまとめて閲覧することもできます。


## <a name="package-version"></a>パッケージ バージョン

**[パッケージ バージョン]** のグラフには、選んだ期間中に発生したクラッシュとイベントの合計数がパッケージ バージョン別に表示されます。 既定では、クラッシュとイベントの合計数が最も多いパッケージ バージョンが一番上に表示され、そこから降順に表示されます。 このグラフの **[ヒット]** 列の矢印をクリックすることで、この順序を逆にすることができます。

## <a name="failures"></a>エラー

**[エラー]** のグラフには、選んだ期間中に発生したクラッシュとイベントの合計数がエラー名別に表示されます。 各エラー名は、4 つの部分 (問題が発生した 1 つ以上のクラス、例外/バグ チェック コード、障害が発生したイメージ/ドライバーの名前、関連する関数の名前) で構成されます。 既定では、クラッシュとイベントの合計数が最も多いエラーが一番上に表示され、そこから降順に表示されます。 このグラフの **[ヒット]** 列の矢印をクリックすることで、この順序を逆にすることができます。 各エラーには、エラーの合計数に対する割合も表示されます。

> [!TIP]
> 場合によっては、このセクションに **[不明]** のエントリが表示されます。 最大限に取り組んでいますが、1 つ以上のエラーについて完全な詳細を収集することができない場合に、**[不明]** のカテゴリに分類されます。 この状況はほとんどの場合、記憶域の制約によって発生しますが、デバイスのプライバシー設定、ネットワーク接続の問題、部分/不良クラッシュ ダンプ、およびその他の要因の結果として発生することもあります。
>
> エラー名に **!unknown** が含まれる場合は、シンボルが存在せず、
エラー名を特定できなかったことを意味します。 正確なエラー分析を取得するには、必ずパッケージにシンボルを含めてください。 「[アプリ パッケージを構成する](../packaging/packaging-uwp-apps.md#configure-an-app-package)」をご覧ください。 これに対し、エラー名に **!unknown_error_in_** または **!unknown_function** が含まれる場合は、他のさまざまな理由で完全な詳細を収集できなかったことを示します。

特定のエラーに関する **[エラーの詳細]** レポートを表示するには、エラー名を選びます。 シンボル ファイルが含まれている場合、**[エラーの詳細]** レポートには、先月のエラー ヒットの数、エラーの発生に関する詳細 (日付、パッケージ バージョン、デバイスの種類、デバイス モデル、OS ビルド) を示すエラー ログ、スタック トレースまたは CAB ファイル (ある場合) へのリンクが表示されます。

> [!TIP]
> CAB ファイルを利用できるのは、Windows Insider ビルドを使っているコンピューターでエラーが発生した場合のみです。したがって、すべてのエラーに CAB のダウンロード オプションがあるわけではありません。 CAB ファイルのあるエラーだけを表示するのには、[フィルター] セクションで**ダウンロードが失敗**を選択します。 リストの上部にある CAB ファイルを含むエラーが表示されるように結果を並べ替えるには、**エラーのログ**のヘッダー**のリンク**をクリックすることもできます。

[**エラーの詳細**] ページも表示されます**スタック流行**グラフは、一定の割合で注文スタックの一番上の失敗を投稿した表示して、**デバイスの構成 (30 D)** グラフに関する詳細情報を提供する、エラーが発生した機器の構成します。 


## <a name="crash-free-sessions-and-devices-30d"></a>クラッシュのないセッションとデバイス (30 D)

**クラッシュのないセッションとデバイス**のグラフでは、デバイスまたは過去 30 日間でクラッシュが発生していないユーザー セッションの割合が表示されます。 この情報を使用して、自分がクラッシュする範囲が広方法は、ユーザーに影響を与えずに理解できます。 たとえば、アプリでは、1 日に 10,000 がクラッシュするをことができます。 デバイスの 90% に影響がある場合は可能性がありますクリティカルとして分類されるし、今すぐ修復機能します。 ただし、アプリを使用して、デバイスの 5% を表すのみ、優先順位が少ないこともあります。

このグラフは、2 つのタブには。
- **クラッシュのないデバイス**: それぞれの日 (過去 30 日間) の中にエラーは発生しませんでした一意のデバイスの割合が表示されます。
- **セッションのクラッシュのない**: それぞれの日 (過去 30 日間) の中にエラーは発生しませんでした固有のユーザーのセッションの割合が表示されます。


 

 