---
author: mtoepke
title: グラフィックス診断ツール
description: Visual Studio でグラフィックス デバッグ、グラフィックス フレーム分析、GPU 使用率などのグラフィックス診断機能を取得して使用する方法について説明します。
ms.assetid: 629ea462-18ed-a333-07e9-cc87ea2dcd93
ms.author: mtoepke
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: Windows 10, UWP, ゲーム, グラフィックス, 診断, ツール, DirectX
ms.openlocfilehash: 076020d88889a9cc8b417befa2dd54b41d688e5e
ms.sourcegitcommit: 909d859a0f11981a8d1beac0da35f779786a6889
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.locfileid: "243269"
---
# <a name="graphics-diagnostics-tools"></a>グラフィックス診断ツール


\[Windows 10 の UWP アプリ向けに更新。 Windows 8.x の記事については、[アーカイブ](http://go.microsoft.com/fwlink/p/?linkid=619132)をご覧ください\]

Windows 10 では、オプション機能として、グラフィックス診断ツールを Windows 内から使うことができるようになりました。 DirectX のアプリやゲームを開発するために、ランタイムや Visual Studio で提供されるグラフィックス診断機能を使うには、次の手順に従ってオプションのグラフィックス ツール機能をインストールします。

1.  **[設定]** に移動し、**[システム]**、**[アプリと機能]** の順に選んで、**[オプション機能の管理]** をクリックします。
2.  **[機能の追加]** をクリックします。   
3.  **[オプション機能]** の一覧から **[グラフィックス ツール]** を選び、**[インストール]** をクリックします。

グラフィックス診断機能には、DirectX ランタイム、またグラフィックス デバッグ、フレーム分析、GPU 使用率で Direct3D SDK デバッグ デバイス (Direct3D SDK レイヤー経由) を作成する機能が備わっています。

-   グラフィックス デバッグ機能を使うと、アプリによる Direct3D 呼び出しをトレースできます。 これらの呼び出しを再生し、パラメーターを調べることで、また、シェーダーのデバッグや検証を実行したり、グラフィックス アセットを視覚化したりすることでレンダリングの問題を診断することもできます。 Windows PC、シミュレーター、またはデバイスでログを収集し、別のハードウェアで再生できます。
-   Visual Studio のグラフィックス フレーム分析機能は、グラフィックス デバッグ ログに対して実行され、Direct3D 描画呼び出しのベースライン タイミングを収集します。 また、さまざまなグラフィックス設定を変更して一連の検証を行い、タイミング結果のテーブルを生成します。 このデータを使うと、アプリのグラフィックス パフォーマンスに関する問題点を把握し、さまざまな検証の結果を確認して、パフォーマンス向上の可能性を探ることができます。
-   Visual Studio の GPU 使用率では、リアルタイムで GPU の使用状況を監視できます。 CPU や GPU で処理されるワークロードのタイミング データを収集し分析することで、ボトルネックがどこにあるかを特定できます。

## <a name="related-topics"></a>関連トピック


[Visual Studio でのグラフィックス診断の概要](http://go.microsoft.com/fwlink/p/?LinkID=526382)

 

 



