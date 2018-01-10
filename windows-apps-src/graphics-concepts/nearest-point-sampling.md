---
title: "最近点サンプリング"
description: "アプリケーションがテクスチャ フィルタリングを使う必要はありません。"
ms.assetid: D7F88320-2C61-47E9-9B92-EC31D48DB079
keywords: "最近点サンプリング"
author: PeterTurcan
ms.author: pettur
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
ms.openlocfilehash: 351acc87764fadc2cd967aaf1d918f4b4837c81f
ms.sourcegitcommit: 909d859a0f11981a8d1beac0da35f779786a6889
translationtype: HT
---
# <a name="span-iddirect3dconceptsnearest-pointsamplingspannearest-point-sampling"></a><span id="direct3dconcepts.nearest-point_sampling"></span>最近点サンプリング


アプリケーションがテクスチャ フィルタリングを使う必要はありません。 Direct3D は、テクセル アドレスを計算するように設定できます。この場合、整数に評価されることはあまりなく、最も近い整数アドレスを持つテクセルの色がコピーされます。 このプロセスは*最近点サンプリング*と呼ばれます。 最近点サンプリングは、テクスチャのサイズが画面上のプリミティブのイメージと同様の場合、テクスチャを処理するのにすばやく効率的な方法です。 そうでない場合、テクスチャを拡大または縮小する必要があります。 テクスチャのサイズとプリミティブ イメージのサイズが一致しない場合、イメージが太くなったり、エイリアシングされたり、ぼやけたりすることがあります。

2 つのテクセルの境界でテクスチャがサンプリングされるとグラフィックが不自然になる可能性があるため、最近点サンプリングは慎重に使ってください。 この境界は、サンプリングされたテクセルがあるテクセルから次のテクセルに移動するテクスチャに沿った位置 (u または v) です。 点サンプリングを使うと、システムはいずれかのサンプル テクセルを選択するため、境界をまたぐと、あるテクセルと次のテクセルで結果が突然変わる可能性があります。 この効果は、表示されたテクスチャのグラフィックが不自然になって現れる可能性があります。 リニア フィルタリングを使うと、生成されるテクセルは隣接する両方のテクセルから計算され、テクスチャ インデックスが境界をまたいで移動するとそれらのテクセルをスムーズにブレンドします。

この効果は、非常に小さいテクスチャを非常に大きい多角形にマッピングすると (多くの場合、拡大と呼ばれる操作) 現れる可能性があります。 たとえば、チェッカーボードのようなテクスチャを使った場合、最近点サンプリングを行うと縁がはっきりした大きいチェッカーボードになります。 一方、リニア テクスチャ フィルタリングを行うと、チェッカーボードの色が多角形間でスムーズに変化するイメージになります。

ほとんどの場合、可能な限り最近点サンプリングを避けることでアプリケーションは最良の結果を出します。 現在のハードウェアの大部分は、リニア フィルタリングに合わせて最適化されているため、アプリケーションのパフォーマンスが低下することはありません。 目的の効果を出すためにどうしても最近点サンプリングを使う必要がある場合 (読みやすいテキスト文字を表示するためにテクスチャを使う場合など)、アプリケーションがテクセル境界でサンプリングを行わないように特に注意する必要があります (望ましくない効果が現れる可能性があるため)。 次の図は、どのように不自然な効果が現れるかを示しています。

![右上の 2 つの四角形に連続しない水平線が表示されている、6 つに分割されたボックスの図](images/ptrtfct.png)

グループの右上にある 2 つの四角形は斜めのオフセットが通過しており、隣接する四角形と異なって表示されています。 このような不自然なグラフィックを避けるには、最近点サンプリングの Direct3D テクスチャ サンプリング ルールについて精通している必要があります。 Direct3D は、\[0.0, 1.0\] (0.0 ～ 1.0。両端を含む) の範囲の浮動小数点テクスチャ座標を、\[ - 0.5, n - 0.5\] (n はテクスチャの特定の範囲におけるテクセルの数) の範囲の整数テクセル空間値にマッピングします。 生成されたテクスチャ インデックスは最も近い整数に丸められます。 このマッピングにより、テクセル境界でサンプリングが不正確になる可能性があります。

シンプルな例として、ラップ テクスチャ アドレス指定モードで多角形をレンダリングするアプリケーションを想像してみてください。 Direct3D により採用されているマッピングを使うと、次のテクスチャの図に示すように、u テクスチャ インデックスは 4 テクセルの幅にマッピングされます。

![テクセルの境界にあるテクスチャ座標 0.0 および 1.0 の図](images/ptsmpprb.png)

この図のテクスチャ座標 0.0 および 1.0 は、ちょうどテクセルの境界にあります。 Direct3D が値をマッピングする方法を使うと、テクスチャ座標の範囲は \[ - 0.5, 4 - 0.5\] (4 はテクスチャの幅) になります。 この場合、サンプリングされたテクセルはテクスチャ インデックスが 1.0 の 0 テクセルになります。 ただし、テクスチャ座標が 1.0 をわずかに下回る場合、サンプリングされたテクセルは 0 テクセルではなく n テクセルになります。

これは、画面空間に沿った三角形で最近点フィルタリングを行って、ちょうど 0.0 および 1.0 のテクスチャ座標を使って小さいテクスチャを拡大すると、テクセルの境界でテクスチャ マップがサンプリングされるピクセルとなることを意味します。 テクスチャ座標の計算における不正確さは大きくありませんが、テクスチャ マップのテクセルの縁に対応する、レンダリングされたイメージ内の領域に沿って不自然な結果が生じます。

浮動小数点テクスチャ座標を完全な正確さで整数テクセルにマッピングするのは難しいだけでなく、計算に時間がかり、一般には必要ありません。 ほとんどのハードウェア実装では、三角形内の各ピクセル位置でテクスチャ座標を計算するために反復的な方法が使われます。 反復的な方法では、反復中エラーが均等に積み重なるため、このような不正確さが隠れる傾向にあります。

Direct3D リファレンス ラスタライザーでは、各ピクセル位置でテクスチャ インデックスを計算するために直接評価の方法が使われます。 直接評価は、操作の不正確さがよりランダムなエラー分布となって現れる点が反復的な方法と異なります。 この結果、境界で発生したサンプリング エラーがより目立つことがあります。リファレンス ラスタライザーは、完全な正確さでこの操作を実行しないためです。

最も良い方法は、必要なときにだけ最近点フィルタリングを使うことです。 使う必要がある場合は、テクスチャ座標を境界位置からわずかにオフセットして、不自然な結果を回避することをお勧めします。

## <a name="span-idrelated-topicsspanrelated-topics"></a><span id="related-topics"></span>関連トピック


[テクスチャ フィルタリング](texture-filtering.md)

 

 



