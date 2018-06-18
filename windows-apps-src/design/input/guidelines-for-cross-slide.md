---
author: mijacobs
Description: Use cross-slide to support selection with the swipe gesture and drag (move) interactions with the slide gesture.
title: クロススライドのガイドライン
ms.assetid: 897555e2-c567-4bbe-b600-553daeb223d5
ms.author: kbridge
ms.date: 10/25/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: windows 10, uwp
ms.localizationpriority: medium
ms.openlocfilehash: ecce3c9e0eee30864c2777b657e9b951a8ab0b06
ms.sourcegitcommit: f9a4854b6aecfda472fb3f8b4a2d3b271b327800
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2017
ms.locfileid: "1393831"
---
# <a name="guidelines-for-cross-slide"></a>クロススライドのガイドライン




**重要な API**

-   [**CrossSliding**](https://msdn.microsoft.com/library/windows/apps/br241942)
-   [**CrossSlideThresholds**](https://msdn.microsoft.com/library/windows/apps/br241941)
-   [**Windows.UI.Input**](https://msdn.microsoft.com/library/windows/apps/br242084)

クロススライドは、スワイプ ジェスチャによる選択や、スライド ジェスチャによるドラッグ (移動) 操作をサポートするために使います。

## <a name="span-iddosanddontsspanspan-iddosanddontsspanspan-iddosanddontsspandos-and-donts"></a><span id="Dos_and_don_ts"></span><span id="dos_and_don_ts"></span><span id="DOS_AND_DON_TS"></span>推奨と非推奨


-   クロススライドは、単一の方向にスクロールするリストやコレクションに使います。
-   クロススライドは、タップ操作が別の目的で使われる場合に、項目を選ぶために使います。
-   キューに項目を追加するためにクロススライドを使わないでください。

## <a name="span-idadditionalusageguidancespanspan-idadditionalusageguidancespanspan-idadditionalusageguidancespanadditional-usage-guidance"></a><span id="Additional_usage_guidance"></span><span id="additional_usage_guidance"></span><span id="ADDITIONAL_USAGE_GUIDANCE"></span>その他の使い方のガイダンス


選択とドラッグは、1 方向 (垂直または水平) にパンできるコンテンツ領域内でだけ行うことができます。 これらの操作が機能するには、1 つのパン方向がロックされていて、ジェスチャがパン方向に対して垂直な方向に行われる必要があります。

ここでは、クロススライドを使ってオブジェクトを選び、ドラッグする方法を示します。 左の図は、スワイプ ジェスチャで距離のしきい値を超える前に指を離してオブジェクトを解放することで、項目が選択された状態を示しています。 右の図は、距離のしきい値を超えてスライド ジェスチャを行うことで、オブジェクトがドラッグされた状態を示しています。

![選択とドラッグ アンド ドロップのプロセスを示す図。](images/crossslide-mechanism.png)

クロススライド操作で使われるしきい値の距離を次の図に示します。

![選択とドラッグ アンド ドロップのプロセスを示すスクリーン ショット。](images/crossslide-threshold.png)

パンの機能を維持するために、選択操作とドラッグ操作は、2.7 mm (ターゲット解像度で約 10 ピクセル) という小さいしきい値を超えないと有効にならないしくみになっています。 この小さいしきい値は、クロススライドとパンの区別に使われるほか、タップ ジェスチャをクロススライドやパンと区別する目的でも使われます。

この図は、ユーザーが UI の要素にタッチしたときに、指の位置がわずかに下に動いてしまった状態を示しています。 しきい値がなければ、最初に垂直方向に移動しているため、この操作はクロススライドと解釈されてしまいます。 このしきい値があるおかげで、水平方向のパンと正しく解釈されます。

![選択かドラッグ アンド ドロップかを明確に区別するためのしきい値を示すスクリーン ショット。](images/crossslide-threshold2.png)

次に、クロススライド機能をアプリに含める際に考慮する必要がある、いくつかのガイドラインを示します。

クロススライドは、単一の方向にスクロールするリストやコレクションに使います。 詳しくは、「[ListView コントロールの追加](https://msdn.microsoft.com/library/windows/apps/hh465382)」をご覧ください。

**注:**  Web ブラウザーや電子ブック リーダーのように、コンテンツ領域を 2 方向にパンできる場合は、時間制限のある長押しの対話式操作を使って、画像やハイパーリンクなどのオブジェクトのコンテキスト メニューを呼び出すようにしてください。

 

|                                                                                         |                                                                                         |
|-----------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| ![水平方向にパンする 2 次元のリスト](images/groupedlistview1.png)                | ![垂直方向にパンする 1 次元のリスト](images/listviewlistlayout.png)                |
| 水平方向にパンする 2 次元のリスト。 項目を選択または移動するには垂直方向にドラッグします。 | 垂直方向にパンする 1 次元のリスト。 項目を選択または移動するには水平方向にドラッグします。 |

 

### <span id="selection"></span><span id="SELECTION"></span>

**選択**

選択は、1 つ以上のオブジェクトを起動またはアクティブ化せずにマークする操作です。 これは、マウスを 1 回クリックする操作、または Shift キーを押しながらクリックする操作 (オブジェクトが複数の場合) に相当します。

クロススライド選択を行うには、要素をタッチし、少しドラッグして放します。 この選択方法を使えば、他のタッチ インターフェイスで必要になるような、専用の選択モードや時間制限のある長押し操作は必要ありません。また、アクティブ化のためのタップ操作と競合することもありません。

クロススライド選択には、距離のしきい値のほかにも領域のしきい値があり、次の図に示すように範囲が 90° に制限されます。 この領域の外にドラッグすると、オブジェクトは選択されません。

![選択のしきい値の領域を示す図。](images/crossslide-selection.png)

クロススライド操作を補完する操作に、"自己説明" 操作とも呼ばれる時間制限のある長押し操作があります。 この補助操作でアクティブ化されるアニメーションによって、オブジェクトに対して実行できる操作が示されます。 不明瞭解消 UI について詳しくは、「[視覚的なフィードバックのガイドライン](guidelines-for-visualfeedback.md)」をご覧ください。

次のスクリーン ショットは、自己説明のアニメーションの動作を示しています。

1.  長押しして、自己説明操作のアニメーションを開始します。 項目が選ばれているかどうかによって、アニメーションで説明される内容が変わります。選ばれていない場合はチェック マークが付き、選ばれている場合はチェック マークが付きません。

    ![選択されていない状態を示すスクリーン ショット。](images/crossslide-selfreveal1.png)

2.  スワイプ ジェスチャ (上または下) を使って項目を選びます。

    ![選択のアニメーションを示すスクリーン ショット。](images/crossslide-selfreveal2.png)

3.  この時点で、項目が選ばれています。 スライド ジェスチャを使って選択動作を上書きし、項目を移動します。

    ![ドラッグ アンド ドロップのアニメーションを示すスクリーン ショット。](images/crossslide-selfreveal3.png)

主な操作が選択だけであるアプリケーションでは、選択にシングル タップを使います。 この場合、アクティブ化やナビゲーションのための標準のタップ操作と区別するために、クロススライドの自己説明のアニメーションが表示されます。

**選択バスケット**

選択バスケットは、アプリの主要なリストやコレクションから選択された項目を視覚的に区別して動的に表す機能です。 これは選択された項目の追跡に役立つ機能で、次のようなアプリで使うと便利です。

-   項目を複数の場所から選択できる。
-   複数の項目を選択できる。
-   選択リストによって操作やコマンドが異なる。

選択バスケットの内容は、操作やコマンドの実行後も保持されます。 たとえば、ギャラリーから一連の写真を選択して各写真に色補正を適用し、それらの写真を何らかの方法で共有した場合、それらの項目は選択されたままになります。

アプリで選択バスケットを使わない場合は、操作やコマンドの実行後に現在の選択がクリアされます。 たとえば、再生リストから曲を選択して評価した後、その選択はクリアされます。

また、選択バスケットを使わない場合は、リストやコレクションで別の項目がアクティブ化されたときにも現在の選択がクリアされます。 たとえば、受信トレイのメッセージを選択すると、プレビュー ウィンドウが更新されます。 その後、受信トレイで別のメッセージを選択すると、前のメッセージの選択が取り消され、プレビュー ウィンドウが更新されます。

**キュー**

キューと選択バスケットのリストは異なるものであるため、混同しないように注意してください。 主な違いは次のとおりです。

-   選択バスケットの項目のリストは、視覚的に表すことだけを目的としたものです。キューの項目は、特定の操作を想定してまとめられたものです。
-   選択バスケットでは同じ項目は 1 回しか表示できませんが、キューでは複数回表示できます。
-   選択バスケットの項目の順序は、選択の順序を表します。 キューの項目の順序は、機能に直接関連します。

これらの理由から、キューに項目を追加する目的でクロススライド選択操作を使わないでください。 キューに項目を追加するときは、代わりにドラッグ操作を使います。

### <span id="draganddrop"></span><span id="DRAGANDDROP"></span>

**ドラッグ**

1 つまたは複数のオブジェクトを別の場所に移動するには、ドラッグを使います。

複数のオブジェクトを移動する必要がある場合は、ユーザーが複数の項目を選択してから、すべてを同時にドラッグできるようにします。

## <a name="span-idrelatedtopicsspanrelated-articles"></a><span id="related_topics"></span>関連記事


**サンプル**
* [基本的な入力のサンプル](http://go.microsoft.com/fwlink/p/?LinkID=620302)
* [待機時間が短い入力のサンプル](http://go.microsoft.com/fwlink/p/?LinkID=620304)
* [ユーザー操作モードのサンプル](http://go.microsoft.com/fwlink/p/?LinkID=619894)
* [フォーカスの視覚効果のサンプル](http://go.microsoft.com/fwlink/p/?LinkID=619895)
**サンプルのアーカイブ**
* [入力: XAML ユーザー入力イベントのサンプルに関するページ](http://go.microsoft.com/fwlink/p/?linkid=226855)
* [入力: デバイス機能のサンプル](http://go.microsoft.com/fwlink/p/?linkid=231530)
* [入力: タッチのヒット テストのサンプル](http://go.microsoft.com/fwlink/p/?linkid=231590)
* [XAML のスクロール、パン、ズームのサンプルに関するページ](http://go.microsoft.com/fwlink/p/?linkid=251717)
* [入力: 簡略化されたインクのサンプル](http://go.microsoft.com/fwlink/p/?linkid=246570)
* [入力: Windows 8 のジェスチャのサンプルに関するページ](http://go.microsoft.com/fwlink/p/?LinkId=264995)
* [入力: 操作とジェスチャ (C++) のサンプルに関するページ](http://go.microsoft.com/fwlink/p/?linkid=231605)
* [DirectX タッチ入力のサンプル](http://go.microsoft.com/fwlink/p/?LinkID=231627)
 

 



