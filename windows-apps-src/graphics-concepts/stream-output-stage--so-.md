---
title: ストリーム出力 (SO) ステージ
description: ストリーム出力 (SO) ステージでは、直前のアクティブなステージからメモリ内の 1 つ以上のバッファーに、頂点データを連続して出力 (ストリーミング) します。 メモリにストリーミングされたデータは、CPU からの入力データまたはリード バックとして、パイプラインに再循環させることができます。
ms.assetid: DE89E99F-39BC-4B34-B80F-A7D373AA7C0A
keywords:
- ストリーム出力 (SO) ステージ
author: michaelfromredmond
ms.author: mithom
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
ms.localizationpriority: medium
ms.openlocfilehash: 30c3ed335360d7b259c045722b65bb08a71b6e0c
ms.sourcegitcommit: 897a111e8fc5d38d483800288ad01c523e924ef4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "1044041"
---
# <a name="stream-output-so-stage"></a>ストリーム出力 (SO) ステージ


ストリーム出力 (SO) ステージでは、直前のアクティブなステージからメモリ内の 1 つ以上のバッファーに、頂点データを連続して出力 (ストリーミング) します。 メモリにストリーミングされたデータは、CPU からの入力データまたはリード バックとして、パイプラインに再循環させることができます。

## <a name="span-idpurposeandusesspanspan-idpurposeandusesspanspan-idpurposeandusesspanpurpose-and-uses"></a><span id="Purpose_and_uses"></span><span id="purpose_and_uses"></span><span id="PURPOSE_AND_USES"></span>目的と用途


![パイプライン内のストリーム出力ステージの場所を示す図](images/d3d10-pipeline-stages-so.png)

ストリーム出力ステージでは、パイプラインからラスタライザーへの途中でメモリにプリミティブ データをストリーミングします。 前のステージのデータをメモリにストリーミングするか、ラスタライザーに渡すことができます。 メモリにストリーミングされたデータは、CPU からの入力データまたはリード バックとして、パイプラインに再循環させることができます。

メモリにストリーミングされたデータは、後続のレンダリング パスでパイプラインに読み戻すか、ステージング リソースにコピーできます (CPU によって読み取られるようにするため)。 ストリーム出力されるデータの量は一定ではありません。Direct3D は、書き込まれるデータの量について (GPU に) 照会しなくてもデータを処理できるように設計されています。&gt;

ストリーム出力データをパイプラインに送る方法は 2 とおりあります。

-   ストリーム出力データは、入力アセンブラー (IA) ステージに戻すことができます。
-   ストリーム出力データは、ロード関数 ([Load](https://msdn.microsoft.com/library/windows/desktop/bb509694) など) を使用して、プログラム可能なシェーダーで読み取ることができます。

## <a name="span-idinputspanspan-idinputspanspan-idinputspaninput"></a><span id="Input"></span><span id="input"></span><span id="INPUT"></span>入力


前のシェーダー ステージの頂点データです。

## <a name="span-idoutputspanspan-idoutputspanspan-idoutputspanoutput"></a><span id="Output"></span><span id="output"></span><span id="OUTPUT"></span>出力


ストリーム出力 (SO) ステージでは、ジオメトリ シェーダー (GS) ステージなど、直前のアクティブなステージからメモリ内の 1 つ以上のバッファーに、頂点データを連続して出力 (ストリーミング) します。 ジオメトリ シェーダー (GS) ステージがアクティブでない場合、ストリーム出力 (SO) ステージでは、ドメイン シェーダー (DS) ステージから (DS もアクティブでない場合は、頂点シェーダー (VS) ステージから) メモリ内のバッファーに頂点データを継続して出力します。

三角形または行のストリップが入力アセンブラー (IA) ステージにバインドされると、各ストリップをストリームする前に、リストに変換されます。頂点常に記述として完了プリミティブ (たとえば、3 頂点の三角形を一度に)。不完全なプリミティブはアウト ストリーミング配信されることはありません。ナチュラル プリミティブ型では、データをストリーミングする前にナチュラル データを破棄します。

ストリーム出力ステージでは、同時に最大 4 つのバッファーまでサポートします。

-   複数のバッファーにデータをストリームする場合、各バッファーは頂点単位のデータの 1 つの要素 (最大 4 コンポーネント) のみを取得でき、出力されるデータは、各バッファーの要素幅と等しくなるようにストライドされます (単一要素バッファーをシェーダー ステージへの入力のためにバインドする方法に対応しています)。さらに、各バッファーのサイズが異なる場合、バッファーのいずれかがいっぱいになるとすぐに書き込みが停止します。 さらに、各バッファーのサイズが異なる場合、バッファーのいずれかがいっぱいになるとすぐに書き込みが停止します。
-   1 つのバッファーにデータをストリームする場合、そのバッファーでは、頂点単位のデータ (256 バイト以下) のスカラーコンポーネントを 64 個まで取得できます。また、頂点を 2048 バイトまでストライドできます。

## <a name="span-idrelated-topicsspanrelated-topics"></a><span id="related-topics"></span>関連トピック


[グラフィックス パイプライン](graphics-pipeline.md)

 

 



