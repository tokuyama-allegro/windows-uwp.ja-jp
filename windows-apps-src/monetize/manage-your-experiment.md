---
description: パートナーセンターで実験を定義し、アプリで実験をコーディングしたら、実験をアクティブにして、パートナーセンターを使用して実験の結果を確認することができます。
title: パートナー センターで実験を管理する
ms.assetid: D48EE0B4-47F2-455C-8FB9-630769AC5ACE
ms.date: 02/08/2017
ms.topic: article
keywords: Windows 10, UWP, Microsoft Store Services SDK, A/B テスト, 実験
ms.localizationpriority: medium
ms.openlocfilehash: dfcd9819940d21dcc81c5ac698b76381adf05af6
ms.sourcegitcommit: a3bbd3dd13be5d2f8a2793717adf4276840ee17d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "93030555"
---
# <a name="manage-your-experiment-in-partner-center"></a>パートナー センターで実験を管理する

[パートナーセンターで実験を定義](define-your-experiment-in-the-dev-center-dashboard.md)し、[実験のためにアプリをコーディング](code-your-experiment-in-your-app.md)したら、実験をアクティブ化し、パートナーセンターを使用して実験の結果を確認することができます。 必要なすべてのデータを取得したら、実験を終了し、すべてのアプリでコントロールのバリエーションの変数値を使用し続けるか、他のバリエーションの変数値を使用することに切り替えるかを選択できます。

> [!NOTE]
> 実験をアクティブ化すると、パートナーセンターは、インストルメント化されたすべてのアプリからのデータ収集をすぐに開始して、実験のデータをログに記録します。 ただし、実験データがパートナーセンターに表示されるまでに数時間かかることがあります。

実験の作成と実行のプロセスについて詳しく示すチュートリアルについては、「[A/B テストを使用して最初の実験を作成および実行する](create-and-run-your-first-experiment-with-a-b-testing.md)」をご覧ください。

## <a name="activate-your-experiment"></a>実験をアクティブ化する

パートナーセンターで実験のパラメーターに問題がなければ、アプリコードを更新したので、アプリから実験データの収集を開始できるように実験をアクティブ化する準備ができました。 実験がアクティブになると、アプリはバリエーション値とレポートビューおよび変換イベントをパートナーセンターに取得できます。

1. [パートナー センター](https://partner.microsoft.com/dashboard)にサインインします。
2. **[アプリ]** の下で、アクティブ化する実験を備えたアプリを選択します。
3. ナビゲーション ウィンドウで、 **[サービス]** を選択し、 **[実験]** を選択します。
4. **[プロジェクト]** セクションのプロジェクトの表で、目的の実験が含まれるプロジェクトを展開し、次のいずれかを実行します。
  * 実験の **[アクティブ化]** リンクをクリックします。 実験が、ページの上部にある **[アクティブな実験]** セクションに追加されます。
  * 実験の名前をクリックし、実験のページの下部までスクロールして、 **[アクティブ化]** をクリックします。

> [!IMPORTANT]
> 実験の作成時に **[編集可能な実験]** チェック ボックスをオンにしていないと、実験をアクティブ化した後で実験のパラメーターを変更できなくなります。 アプリで実験のコードを記述してから実験をアクティブ化することをお勧めします。

## <a name="review-the-results-of-your-experiment"></a>実験の結果を確認する

1. パートナーセンターで、アプリの **実験** ページに戻ります。
2. **[アクティブな実験]** セクションで、目的のアクティブな実験の名前をクリックし、実験のページに移動します。
3. アクティブな実験または完了した実験の場合、このページの最初の 2 つのセクションに実験の結果が表示されます。
  * **[結果の概要]** セクションには、実験の目標と各バリエーションのコンバージョン率の一覧が表示されます。
  * **[結果の詳細]** セクションには、ビュー、コンバージョン、固有ユーザー数、コンバージョン率、デルタ %、信頼性、重要性など、実験のすべての目標に対する各検証結果の詳細が表示されます。 *信頼性* は、推定値の信頼性の統計的な計測であり、許容誤差を計算したものです。 *重要性* は、サンプル サイズに基づいた統計的な計測であり、結果が偶然に発生したのではなく、特定の原因によって発生した可能性があることを示すものです。

> [!NOTE]
> パートナーセンターは、24時間以内に各ユーザーの最初の変換イベントのみを報告します。 ユーザーが 24 時間以内にアプリで複数のコンバージョン イベントをトリガーした場合は、最初のコンバージョン イベントのみ報告されます。 これは、多数のコンバージョン イベントを使用する単一のユーザーによって、サンプルのユーザー グループの実験の実行結果が歪曲されないようにすることを目的としています。


## <a name="complete-your-experiment"></a>実験を完了する

1. パートナーセンターで、実験ページに戻ります。 手順については、前のセクションをご覧ください。
2. **[Results summary]** セクションで、次のいずれかの操作を行います。
  * 実験を終了し、アプリでコントロールのバリエーションの変数値を使用し続ける場合は、 **[保存]** をクリックします。
  * 実験を終了するが、アプリでは別のバリエーションの変数値を使用する場合は、新たに使用するバリエーションの下にある **[切り替え]** をクリックします。
3. **[OK]** をクリックして、試験的機能を終了することを確認します。


## <a name="related-topics"></a>関連トピック

* [パートナーセンターでプロジェクトを作成し、リモート変数を定義する](create-a-project-and-define-remote-variables-in-the-dev-center-dashboard.md)
* [アプリの実験用のコードを記述する](code-your-experiment-in-your-app.md)
* [パートナー センターで実験を定義する](define-your-experiment-in-the-dev-center-dashboard.md)
* [A/B テストを使用して最初の試験的機能を作成および実行する](create-and-run-your-first-experiment-with-a-b-testing.md)
* [A/B テストを使用してアプリの実験を実行する](run-app-experiments-with-a-b-testing.md)
