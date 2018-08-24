---
author: GrantMeStrength
title: 複雑などこからでも Windows プラットフォーム (UWP) アプリケーションを構築します。
description: Microsoft のデザイン チームのアプリ作成プロセスは、5 つの段階 (概念、構造、ダイナミクス、視覚、プロトタイプ) で構成されています。 同様のプロセスを採用して、だれもが楽しめるエクスペリエンスを実現することをお勧めします。
ms.assetid: 9A5189CD-3B97-4967-8E7D-36D25F04F244
ms.author: jken
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: Windows 10, UWP
ms.localizationpriority: medium
ms.openlocfilehash: 7f2dbbf2d8cb653f0783c3e2655278b6d65634b6
ms.sourcegitcommit: 897a111e8fc5d38d483800288ad01c523e924ef4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "1015538"
---
#  <a name="building-a-complex-universal-windows-platform-uwp-app"></a>複雑などこからでも Windows プラットフォーム (UWP) アプリケーションを構築します。

Microsoft のデザイン チームのアプリ作成プロセスは、5 つの段階 (概念、構造、ダイナミクス、視覚、プロトタイプ) で構成されています。 同様のプロセスを採用して、だれもが楽しめるエクスペリエンスを実現することをお勧めします。

## <a name="concept"></a>概念

**アプリに焦点を当てる**

ユニバーサル Windows プラットフォーム (UWP) アプリを計画する際は、アプリの内容や対象ユーザーだけでなく、アプリの 1 番の特徴も決定する必要があります。 すべての優れたアプリの中心には、しっかりした基盤を提供する強力な概念があります。

たとえば、写真アプリを作るとします。 ユーザーが写真を操作、保存、共有する動機を考えてみると、写真で思い出をたどったり、写真を通じて他の人々と交流したり、写真を安全に保管したりすることであるとわかります。 次に、このような用途に適した写真アプリを作ることにします。このユーザー エクスペリエンスの目標を意識しながら、アプリの設計プロセスを進めていきましょう。

**何のためのアプリか** まず、大まかなコンセプトを決めます。ユーザーがアプリで何をできるようにするか、一覧にまとめてみましょう。

たとえば、旅行の計画に使うアプリを作るとします。 次のように、頭に浮かんだアイデアをメモしてみましょう。

-   旅行計画に含まれている場所の地図をすべて集めて、旅行中もそれを携帯する。
-   旅行先で滞在中に開催されるイベントを見つける。
-   必ずするアクティビティや必ず見る観光名所の一覧を、旅行に行くメンバーが各自で作成し、他のメンバーも見られるようにする。
-   旅行のメンバーが撮ったすべての写真をまとめて、友人や家族と共有する。
-   航空料金に基づいて、お勧めの行き先を選ぶ。
-   目的地周辺のレストラン、店舗、アクティビティが多数掲載されている情報源を見つける。

![旅行アプリのデザイン](images/ux-triptracker-tab-phone-700.png)

**アプリの 1 番の特徴は何か** すべてのアイデアを全体的に見て、特に目立つシナリオがないか考えてみます。 数多くのアイデアの中から絞り込んで、これに集中しようと思えるシナリオを 1 つだけ選びます。 優れたアイデアをたくさん捨てることになりますが、その 1 つのシナリオを良いものにしあげるには、いさぎよくアイデアを捨てることが肝心です。

シナリオを 1 つ選んだら、アプリの 1 番の特徴を普通の人に 1 行で伝えるにはどうしたらよいかを考えます。 例: 

-   この旅行アプリを使えば、友人どうしで協力してグループ旅行の計画を作り上げることができます。
-   このワークアウト アプリを使うと、友人どうしでトレーニングの経過を記録して、互いに成果を見せることができます。
-   この食料雑貨アプリを使うと、家族で毎週の食料雑貨を計画的に買うことができ、買い忘れや重複がなくなります。

![コラボレーション ツールのデザイン](images/ux-collaboration-tabphone-700.png)

このようにアプリの 1 番の特徴を示す説明文を作っておくと、アプリを作るプロセスで、設計上のさまざまな決定事項や妥協点を判断する際に役立ちます。 アプリでユーザーに提供するエクスペリエンスのシナリオを中心とした説明文にしますが、単なる機能一覧にならないように注意してください。 この説明文では、アプリが実行できる機能を説明するのではなく、ユーザーがこのアプリを使ってできることを説明します。

**じょうご型設計**

運用環境に取り入れるまでの道のりは長いと思いますが、自由にアイデアを考えて、開発することはとても魅力的です。 ただし、仮にそれを実現したとして、新たに別の興味深いアイデアが思い付きます。 当然のことながら、2 つのアイデアの優劣にかかわらず、既に投資してきたアイデアにこだわろうとするでしょう。 その別のアイデアをプロセスのもっと早い段階で思い付いていればよかったのです。 そこで、じょうご型設計は、できるだけ早く最善のアイデアを発見するのに役立つ手法です。

"じょうご" という用語は、その形に由来しています。 じょうごの幅広の部分では、多くのアイデアが入ると、各アイデアが忠実度の非常に低い設計アーティファクト (スケッチ、テキストの段落) であるとわかります。 このように集められたアイデアがじょうごの狭い方に向かって移動するにつれ、アイデアを表すアーティファクトの忠実度が高まると同時にアイデアの数は削減されます。 各アーティファクトでは、アイデアどうしを比較して判定するため、または "これが使って便利なのか (つまり直感的に使えるのか)" などの特定の質問に答えるために必要な情報のみをキャプチャする必要があります。 *各アーティファクトにそれ以上の時間と労力を使わないでください*。 アイデアによっては、テスト時に途中で挫折することもありますが、そのアイデアの判定に必要以上に投資しないようにするため、それでかまいません。 じょうごの中でさらに残り続けるアイデアは、忠実度の高いものとして扱われます。 最終的には、魅力的なアイデアを表す 1 つの設計アーティファクトが残ることになります。 これは、単に最初に思い付いたからではなく、その利点によって残ったアイデアといえます。 これで、最適なアプリを設計できるでしょう。

## <a name="structure"></a>構造


**構成によってすべてが簡単になる**

![構成によってすべてが簡単になる](images/ux-vision-and-process-organization.png)

概念に満足したら、次の段階としてアプリの青写真を作る準備に入ります。 情報アーキテクチャ (IA) により、コンテンツには、必要な構造的整合性が提供されます。 これは、アプリのナビゲーション モデルを定義し、最終的にアプリの ID を定義するのに役立ちます。 コンテンツをどのように整理するか、また、どうすればユーザーがそのコンテンツを見つけられるのかを計画することにより、ユーザーがアプリを使ったときのエクスペリエンスについて理解を深めることができます。

優れた IA は、ユーザーのシナリオを容易にするだけでなく、最初に主な画面を構想するのに役立ちます。 ユーザーのライブラリ、ストア、ニュース、および"補正"へのアクセスを提供するハブに直接など、[音](http://go.microsoft.com/fwlink/p/?LinkID=268089)のアプリを起動します。ユーザー エクスペリエンスは重点を置いた、ユーザーがアクセスしたり、audiobooks をすぐに利用できるようにします。 アプリのより深いレベルでは、より具体的なタスクに焦点を当てています。

関連するガイドラインについては、「[Windows ユニバーサル アプリのナビゲーション デザインの基本](../design/basics/navigation-basics.md)」をご覧ください。

## <a name="dynamics"></a>ダイナミクス

**概念の実現**

概念の段階でアプリの目的を定義した場合、ダイナミクスの段階ではその目的を遂行するだけです。 これを実現するには多くの方法があります。たとえば、ワイヤーフレームを使ってページ フロー (目的を果たすためにアプリ内のある場所から別の場所に移動する方法) をスケッチしたり、アプリの UI 全体で使う音声や言葉について考えたりします。 ワイヤーフレームは簡単ですが忠実度の低いツールで、アプリのユーザー フローについて重要な判断を行うのに役立ちます。

アプリ フローは、"1 番の特徴" の説明文と関連していることが必要です。アプリ用に選んだ 1 つのシナリオを実現できるように、フローを作ります。 優れたアプリは、最小限の労力で覚えられるフローを備えています。 まずは画面間レベルで考えてみましょう。アプリを初めて使うかのように眺めてください。 作るページのユーザー シナリオを正確に示す場合、不要な画面タッチが多くならないように、必要なものだけを提供します。 ダイナミクスはアニメーションにも関連しています。 適切なアニメーション機能によって、ページ間の滑らかな動作と使いやすさが決まります。

この手順に役立つ一般的な方法: 

-   フローの概要: 最初の操作とその次の操作を決める
-   フローのストーリーボード: フロー完了までの UI 操作の順序を決める
-   プロトタイプ: 簡単なプロトタイプを使ってフローをテストする

**ユーザーは何をできるか** たとえば、旅行アプリを使うと "友人どうしで協力してグループ旅行の計画を作り上げる" ことができます。 必要なフローをリストにまとめましょう。

-   一般的な情報で旅行計画を作る。
-   友人たちを旅行に誘う。
-   友人の旅行に参加する。
-   他の旅行者が勧める旅行計画を見る。
-   目的地とアクティビティを旅行に追加する。
-   友人たちが追加した目的地とアクティビティを編集したり、コメントを書いたりする。
-   友人や家族に見てもらえるように旅行計画を共有する。

## <a name="visual"></a>視覚

**言葉を使わずに伝える**

![カクテル作成アプリのデザイン](images/ux-cocktailcreator-tab-phone.png)

アプリのダイナミクスを確立したら、アプリの外観を洗練して魅力的なものにすることができます。 優れた視覚効果として、アプリの外観だけでなく、アニメーションやモーションを使ってライブ感を出す方法を定義します。 選んだカラー パレット、アイコン、アートワークは、この視覚言語の一例です。

どのアプリにも独自の一意な ID があるため、アプリで利用できる視覚的な向きを確かめます。 コンテンツによって外観を誘導できます。つまり、外観によってコンテンツが決まるのではありません。

## <a name="prototype"></a>プロトタイプ

**作品を絞り込む**

プロトタイプは、*じょうご型設計* (既に説明した手法) における 1 つの段階です。ここでは、アイデアを表すアーティファクトが、スケッチ以上だが、完成したアプリほど複雑ではないレベルに進化します。 プロトタイプは、ユーザーに表示される画面を手書きで表したフローである場合があります。 テストの実行者は、実行中のアプリをシミュレートするために、さまざまな画面を下に配置したり、ページ上のいくつかの UI をくっつけたり離したりすることで、ユーザーのキューに応答する場合があります。 また、操作者がスクリプト最後まで実行して正しいボタンを押す場合、プロトタイプは複数のワークフローをシミュレートする非常にシンプルなアプリになります。 この段階で、アイデアは実際に実現性を帯び始め、これまで費やしてきた作業が本格的にテストされます。 アプリの領域のプロトタイプを作る場合、時間をかけて、最も必要なコンポーネントを調整して絞り込んでください。

優れたアプリの作成とは反復プロセスであるということは、経験の少ない開発者にとっていくら強調してもしすぎることはありません。 初期段階から何度もプロトタイプを作ることをお勧めします。 創造力を養う努力と同様、最適なアプリは徹底的な試行錯誤による成果です。

## <a name="decide-what-features-to-include"></a>アプリに含める機能を決める

ユーザーの目的を理解し、その目的を助ける方法もわかったら、次にすることは、それを実現するための機能を探すことです。 ユニバーサル Windows プラットフォーム (UWP) を調べて、アプリのニーズに対応する機能を探します。 各機能については、「[ユニバーサル Windows プラットフォーム (UWP) アプリのガイドライン](https://developer.microsoft.com/windows/apps/design)」に従ってください。
<!--need URL for landing page -->

一般的な方法:

-   プラットフォームの調査: プラットフォームにある機能を確かめて、どのように使えるかを考える。
-   関連付けのダイアグラム: フローと機能を結び付ける。
-   プロトタイプ: 機能をテストして、必要な働きができるかを確かめる。

**アプリ コントラクト**  幅広いアプリ間ユーザー フローと機能間ユーザー フローを実現するアプリ コントラクトに、アプリを参加させることができます。

-   **共有**  ユーザーがアプリのコンテンツを他のアプリ経由で他のユーザーと共有できるだけでなく、他のユーザーやアプリの共有コンテンツを受け取ることもできるようにします。
-   **リモート再生**  オーディオ、ビデオ、またはイメージをアプリからホーム ネットワーク上の別のデバイスにストリーミングして楽しむことができます。
-   **ファイル ピッカーとファイル ピッカーの拡張機能**   ユーザーがローカル ファイル システム、接続された記憶装置、ホームグループ、さらに他のアプリからファイルをアプリに読み込み、保存できるようにします。 また、ファイル ピッカーの拡張機能を使って、アプリのコンテンツを他のアプリに読み込むこともできます。

詳しくは、[アプリ コントラクトと拡張機能](https://msdn.microsoft.com/library/windows/apps/hh464906)についてのページをご覧ください。
<!-- Win 8 page. Should have replacement. -->

**さまざまなビュー、フォーム ファクター、ハードウェア構成**  Windows では、ユーザーがさまざまな持ち方や向きでデバイスを構えるので、アプリもそれに対応する必要があります。 アプリの UI は、ユーザーが使うあらゆるデバイス、入力モード、向き、ハードウェア構成、状況で適切に表示される必要があります。

**タッチ優先**  Windows では、独自の直感的なタッチ操作を使うことができます。これはマウスと同じように使えるだけではありません。

たとえば、セマンティック ズームは、大きなコンテンツ セットの中を移動するときにタッチ操作のメリットが活かした操作方法です。 パンまたはスクロールでコンテンツのカテゴリを移動し、カテゴリを拡大して詳しい情報を見ることができます。 タブなどの従来のナビゲーション手法やレイアウト パターンよりも、コンテンツを感覚的、視覚的に表現でき、多くの情報を示すことができます。

もちろん、回転、パン、スワイプなどタッチ操作のさまざまな長所を利用できます。 詳しくは、「[操作のガイドライン](../design/input/input-primer.md)」をご覧ください。

**魅力と新鮮さ**  アプリが新鮮に感じられ、次のような標準的なエクスペリエンスでユーザーを魅了できることが重要です。

-   **アニメーション**  アニメーションのライブラリを使って、ユーザーにとってアプリを軽快で柔軟なものにすることができます。 コンテキストの変化がわかりやすく、視覚的な切り替えがエクスペリエンスに結び付きます。 詳しくは、[UI のアニメーション化](../graphics/animations-overview.md)についてのページをご覧ください。
-   **トースト通知**  トースト通知によって、即時性が必要なコンテンツや個人的に関係のあるコンテンツをユーザーに知らせ、アプリが非表示の場合は、アプリを表示するようにユーザーに促します。 詳しくは、[タイル、バッジ、トースト通知](../design/shell/tiles-and-notifications/index.md)についてのページをご覧ください。
-   **アプリ タイル**  ユーザーと関連性の深い最新の更新情報を知らせて、ユーザーがアプリを開くように誘います。 次のセクションで詳しく説明します。 詳しくは、「[アプリ タイル](../design/shell/tiles-and-notifications/creating-tiles.md)」をご覧ください。

**個人設定**

-   **設定**  アプリ設定を保存することによって、ユーザーは好みのエクスペリエンスを作ることができます。 すべての設定を 1 つの画面にまとめて、ユーザーが使い慣れた一般的なメカニズムでアプリを構成できるようにします。 詳しくは、「[アプリ設定の追加](../design/app-settings/app-settings-and-data.md)」をご覧ください。
-   **ローミング**  データのローミングによってデバイス間で連続性のあるエクスペリエンスを実現し、ユーザーが作業を中断したところから再開できるようにすると共に、使われているデバイスに関係なく、ユーザーが最も重視する UX を保持できるようにします。 設定と状態をローミングによって維持することで、キッチンで家族が使う PC、仕事用 PC、個人用のタブレット、その他のフォーム ファクターなど、どこにいてもアプリを快適に使えるようにします。 詳しくは、「[アプリケーション データの管理](../design/app-settings/store-and-retrieve-app-data.md)」と「[アプリケーション データのローミングのガイドライン](https://msdn.microsoft.com/library/windows/apps/hh465094)」をご覧ください。
-   **ユーザー タイル**   ユーザーがアプリを個人設定で使えるようにします。ユーザーのイメージを読み込んだり、アプリからのコンテンツを Windows で個人用タイルとして設定できるようにします。

**デバイスの機能**  最新のデバイスの機能をアプリで十分に活用してください。

-   **近接ジェスチャ**  ユーザーは、複数のデバイスを物理的に "タップ" することで、物理的に近くにいる他のユーザーとデバイスを接続できます (マルチプレイヤー ゲーム)。 詳しくは、「[近接通信とタップのサポート](https://msdn.microsoft.com/library/windows/apps/hh465229)」をご覧ください。
-   **カメラと外部記憶装置**  内蔵カメラまたは接続されたカメラを利用します。チャットや電話会議、ビデオ ログの記録、プロファイル写真の撮影、日常的な文書作成など、アプリの特徴に応じたさまざまな活動に使うことができます。 詳しくは、[リムーバブル ストレージのコンテンツへのアクセス](https://msdn.microsoft.com/library/windows/apps/hh465189)についてのページをご覧ください。
-   **加速度計やその他のセンサー**     最新のデバイスはさまざまなセンサーを備えています。 アプリでは、環境光に応じてディスプレイの明るさを調節したり、ユーザーがディスプレイの向きを変えたときに UI を自動的に再配置したり、物理的な動きに応じて処理を行ったりできます。 詳しくは、[センサー](../devices-sensors/sensors.md)についてのページをご覧ください。
-   **地理位置情報**  標準的な Web データまたは地理位置情報センサーからの地理位置情報を使って、ユーザーの移動や地図上での位置確認、または近くのユーザー、アクティビティ、目的地に関するユーザー通知を支援します。 詳しくは、[地理位置情報](https://msdn.microsoft.com/library/windows/apps/hh465139)についてのページをご覧ください。

旅行アプリの例についてもう一度考えてみましょう。 友人どうしで協力してグループ旅行の計画を作り上げるアプリには、次のような機能があるとよいかもしれません。

-   共有: 次の旅行の計画を複数のソーシャル ネットワークで公開して、旅行前の楽しみを家族や友人と分かち合います。
-   検索: 他の共有された旅行計画や公開された旅行計画を検索して、アクティビティや目的地を探し、自分たちの旅行に取り入れることができます。
-   通知: 旅行の仲間が旅行計画を更新したときに、通知を受け取ります。
-   設定: 通知する旅行、旅行計画の検索用を許可するソーシャル グループなどの設定をユーザーが構成できます。
-   セマンティック ズーム: ユーザーは旅行計画のタイムラインを閲覧しながら、数多くの計画済みアクティビティを必要に応じて拡大表示し、詳しい内容を見ることができます。
-   ユーザー タイル: 友人と旅行を共有するときに表示する画像を選択できます。

## <a name="decide-how-to-monetize-your-app"></a>アプリで収益を得る方法を決める

さまざまな方法でアプリから収益を得られます。 アプリ内の広告や販売を使う場合は、それに対応するように UI を設計します。 詳しくは、「[収益の計画](../monetize/index.md)」をご覧ください。

## <a name="design-the-ux-for-your-app"></a>アプリの UX を設計する

ここでは、適切な基本構造を作ります。 アプリの 1 番の特徴が決まり、サポートするフローも決まったので、次はユーザー エクスペリエンス (UX) 設計の基本構造を検討します。

**UI コンテンツをどのようにまとめるか**   ほとんどのアプリ コンテンツは、特定の形式のグループまたは階層にまとめることができます。 コンテンツの最上位グループの内容は、1 番の特徴の説明文に沿ったものにします。

旅行アプリを例に考えてみましょう。旅行計画をグループ化する方法はいくつかあります。 アプリの主な目的が興味深い目的地を見つけることであれば、冒険旅行、リゾート旅行、ロマンチックな休暇旅行など、興味の対象ごとにグループ化できます。 しかし、このアプリの主な目的は友人と協力して旅行計画を立てることなので、家族、友人、同僚など、ソーシャル グループごとに旅行計画を整理する方が理にかなっています。

コンテンツのグループ化の方法が決まると、アプリにどのようなページやビューが必要なのかがわかります。 詳しくは、「UI の基本」をご覧ください。

**UI コンテンツをどのように表示するか** UI をまとめる方法が決まったら、UI がどのように構築され、ユーザーに表示されるかを指定する、UX の目標を定義できます。 どのシナリオでも、できるだけ早くユーザーがアプリを楽しんで使い続けることができるようにする必要があります。 これを行うには、最初にユーザーに表示する UI の部分を決めて、その部分を完成させてから、その他の重要でない部分の構築に時間を使う必要があります。

旅行アプリでは、ユーザーはまず具体的な旅行計画を探します。 この情報をできるだけ早くユーザーに表示するには、まず **ListView** コントロールを活用して、旅行の一覧を表示します。

![旅行アプリの旅行計画セレクターのデザイン](images/ux-app-travel-cc-a-1-180.png)

旅行の一覧が表示されると、友人の旅行のニュース フィードなどの機能の読み込みが始まります。

**必要な UI サーフェスとコマンドは何か**   前の手順で決めたフローをもう一度見てみます。 各フローについて、ユーザーが行う手順を大まかに作成します。

たとえば、"友人や家族が旅行計画を確認できるように共有する" フローで考えてみましょう。 ユーザーが既に旅行計画を立てているとします。 旅行計画を共有するには、次の手順が必要です。

1.  アプリを開き、作成した旅行の一覧を表示します。
2.  共有する旅行をタップします。
3.  旅行の詳しい内容が画面に表示されます。
4.  共有を開始するための UI を操作します。
5.  旅行を共有したい友人のメール アドレスまたは名前を選ぶか、入力します。
6.  共有の操作を完了するための UI を操作します。
7.  アプリの旅行の情報が更新され、旅行計画を共有するメンバーの一覧が反映されます。

このプロセスによって、作る必要のある UI と、さらに作り込みが必要な部分 (アプリをまだ使っていない友人に送るメールの定型文を考えるなど) を把握することができます。 さらに、不要な手順を削る作業も始めます。 たとえば、旅行の詳しい内容を共有前に実際に見る必要はないかもしれません。 フローが整理されると使いやすくなります。

さまざまなサーフェスを使う方法について詳しくは、「<!--[Command design basics](../design/basics/commanding-basics.md)-->」をご覧ください

**フローをどのようにするか** ユーザーの手順を定義したら、そのフローをパフォーマンスの目標にします。 詳しくは、「[パフォーマンスの計画](../debug-test-perf/planning-and-measuring-performance.md)」をご覧ください。

**コマンドをどのように配置するか**  大まかなフロー手順に従って、設計する必要のあるコマンドを決めます。 次に、アプリのどこでコマンドを使うかを考えます。

-   **できるだけコンテンツを直接操作できるようにする。**  できる限り、コンテンツを操作するコマンドを用意せず、アプリのキャンバス上でユーザーがコンテンツを直接操作できるようにします。 たとえば、旅行アプリで旅行計画を編集するときに、リスト内のアクティビティを上下に移動するコマンド ボタンを使うのではなく、キャンバスのリスト上でアクティビティをドラッグ アンド ドロップできるようにします。
-   **コンテンツを直接操作できない場合。** コンテンツを直接操作できない場合は、コマンドを次の UI サーフェスのいずれかに配置します。

    -   [コマンド バー](https://msdn.microsoft.com/library/windows/apps/hh465302): コマンドはできる限りコマンド バーに配置してください。通常、コマンド バーは非表示になっており、ユーザーがタップすると表示されます。
    -   アプリのキャンバス上: 目的が 1 つに限られているページまたはビューは、その目的用のコマンドをキャンバス上に直接配置できます。 しかし、このようなコマンドはなるべく作らないでください。
    -   [ショートカット メニュー](https://msdn.microsoft.com/windows/uwp/controls-and-patterns/menus): クリップボードの操作 (切り取り、コピー、貼り付けなど) や、選択できないコンテンツに実行するコマンド (地図の目的の位置にピンを追加するなど) に使うことができます。

**各ビューでアプリを準備する方法を決定します。**  Windows では横向きと縦向きがサポートされ、全画面表示から最小幅にいたるまで、アプリの幅をあらゆるサイズに変更できます。 アプリは、任意のサイズの任意の画面で、どの向きでも適切に表示され、機能することが望まれます。 つまり、さまざまなサイズとビューについて、UI 要素のレイアウトを計画する必要があります。 そうすることで、ユーザーのニーズと好みに合わせてアプリ UI が柔軟に変化します。

![PC とモバイルにおけるアプリのデザイン](images/ux-budgettracker1-md-notablet.png)

さまざまな画面サイズのための設計について詳しくは、「[画面のサイズとレスポンシブ デザインのブレークポイント](https://docs.microsoft.com/en-us/windows/uwp/layout/screen-sizes-and-breakpoints-for-responsive-design)」をご覧ください。

## <a name="make-a-good-first-impression"></a>第一印象を良くする

初めてアプリを起動したユーザーがどのように思ったり感じたりするかを考えましょう。 アプリの "1 番の特徴" の説明文を再確認します。 アプリの 1 番の特徴をユーザーに直接説明できなくても、第一印象を演出することでメッセージを伝えることができます。 次の機能を利用します。

**タイルと通知**    タイルはアプリの顔です。 ユーザーのスタート画面に表示される数多くのアプリの中から自分のアプリが起動される決め手になるのは、何でしょうか。 タイルでアプリのブランドを明確にして、アプリの特徴を示すようにします。 アプリで常に最新の役立つ情報が伝えられるようにタイル通知を使うことで、ユーザーがアプリを繰り返し利用するようにします。

**スプラッシュ画面**  スプラッシュ画面はできるだけ短時間で読み込む必要があります。この画面は、アプリの状態を初期化する必要が生じない限り画面上に維持する必要があります。 スプラッシュ画面の表示内容で、アプリの特徴を伝えます。

**初めての起動**  ユーザーがサービスの新規登録、アカウントへのログイン、独自のコンテンツの追加を行う前に、ユーザーに対して何を表示しますか。 ユーザーに情報を求める前に、アプリの価値をアピールします。 アプリを使ってもらうためには、ユーザーが自由に見ることのできるサンプル コンテンツを表示して、どのようなアプリなのかを知ってもらうのもよいでしょう。

**ホーム ページ**  ホーム ページとは、ユーザーがアプリを起動するたびに表示されるページです。 ここに表示されるコンテンツは、目的をはっきりさせ、アプリの特徴がすぐにわかるようにする必要があります。 このページでは、1 番の特徴だけを強調します。アプリの他の部分はユーザーが探し出してくれることを期待しましょう。 ランディング ページでは、ユーザーがアプリの特徴に気付きやすくするのではなく、散漫な印象を与えないようにすることを重視してください。

## <a name="validate-your-design"></a>設計を検証する

設計のやり直しを避けるために、アプリの開発があまり進まないうちに、設計内容またはプロトタイプをガイドライン、ユーザーの印象、要件に照らして検証します。 各機能には、アプリをブラッシュ アップするためのユーザー エクスペリエンスのガイドラインと一連のストア要件を Microsoft ストアにアプリを発行する必要があります。 [Windows アプリ認定キット](https://developer.microsoft.com/windows/develop/app-certification-kit)を使って、ストア要件を技術的に満たすかどうかのテストを実行できます。 また、Microsoft Visual Studio のパフォーマンス ツールを使って、すべてのシナリオでユーザーに快適なエクスペリエンスを提供しているかどうかを確認できます。

[UWP アプリの詳細な UX ガイドライン](https://msdn.microsoft.com/library/windows/apps/hh465424)を使って、重要な機能に集中して取り組みます。 [Visual Studio パフォーマンス ツール](https://msdn.microsoft.com/library/windows/apps/hh696636.aspx)を使って、各アプリのシナリオのパフォーマンスを分析します。