---
author: stevewhims
Description: "このセクションでは、アプリの文字列、画像、ファイル リソースを作成、パッケージ化、利用する方法を示します。"
title: "アプリ リソースとリソース管理システム"
label: Intro
template: detail.hbs
ms.author: stwhi
ms.date: 10/20/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: "Windows 10, UWP, リソース, 画像, アセット, MRT, 修飾子"
localizationpriority: medium
ms.openlocfilehash: 38a131704bacbffdf89636aa70b405aa30861d27
ms.sourcegitcommit: d0c93d734639bd31f264424ae5b6fead903a951d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2017
---
# <a name="app-resources-and-the-resource-management-system"></a>アプリ リソースとリソース管理システム
<link rel="stylesheet" href="https://az835927.vo.msecnd.net/sites/uwp/Resources/css/custom.css">

このセクションでは、アプリの文字列、画像、ファイル リソースを作成、パッケージ化、利用する方法を示します。 たとえば、カジュアル ゲームと共に、ゲームのレベルの定義が含まれるファイルをパッケージ化し、実行時にそのファイルを読み込むことができます。 アプリのロジックとは別にリソースを管理することによって、さまざまなロケール、デバイスのディスプレイ、アクセシビリティの設定、その他のユーザーとコンピューターのコンテキストに合わせたアプリのローカライズやカスタマイズが容易になることも説明します。 文字列や画像などのリソースには、通常、言語、スケール、コントラストの複数のバリエーションが存在している必要があります。 そのようなリソースについては、[リソース管理システム](resource-management-system.md)を活用できます。

アプリ リソースには、次の 2 種類があります。
- ファイル リソースは、ディスク上のファイルとして格納されているリソースです。 ファイル リソースには、ビットマップ画像、XAML、XML、HTML、またはその他のあらゆる種類のデータを含めることができます。
- 埋め込みリソースは、特定の格納するリソース ファイル内に埋め込まれたリソースです。 最も一般的な例は、リソース ファイル (.resw または .resjson) に埋め込まれた文字列リソースです。

アプリのローカライズの価値提案の詳細については、「[グローバリゼーションとローカライズ](../globalizing/globalizing-portal.md)」をご覧ください。

| 記事 | 説明 |
|---------|-------------|
| [リソース管理システム](resource-management-system.md) | ビルド時に、リソース管理システムは、アプリとしてパッケージ化されているリソースのさまざまなバリエーションすべてのインデックスを作成します。 実行時に、システムは、有効になっているユーザーやコンピューターの設定を検出し、それらの設定に最適なリソースを読み込みます。 |
| [リソース管理システムでのリソースの照合と選択の仕組み](how-rms-matches-and-chooses-resources.md) | リソースを要求すると、現在のリソース コンテキストにある程度一致するリソース候補がいくつか存在する場合があります。 リソース管理システムはすべての候補を分析して、返すのに最もよい候補を決定します。 このトピックでは、そのプロセスの詳細について説明し、例を示します。 |
| [リソース管理システムでの言語タグの照合の仕組み](how-rms-matches-lang-tags.md) | 前のトピック (「[リソース管理システムでのリソースの照合と選択の仕組み](how-rms-matches-and-chooses-resources.md)」) では、一般的な修飾子の照合について説明しました。 このトピックでは、言語タグの照合についてさらに詳しく説明します。 |
| [言語、スケール、ハイ コントラスト、その他の修飾子用にリソースを調整する](tailor-resources-lang-scale-contrast.md) | このトピックでは、リソース修飾子の一般概念、使用方法、各修飾子名の目的について説明します。 |
| [UI とアプリ パッケージ マニフェスト内の文字列をローカライズする](localize-strings-ui-manifest.md) | アプリで複数の表示言語をサポートする必要があり、コード、XAML マークアップ、アプリ パッケージ マニフェスト内に文字列リテラルが含まれている場合は、その文字列をリソース ファイル (.resw) に移動します。 アプリでサポートする各言語用に、このリソース ファイルを翻訳したコピーを作成することができます。 |
| [表示倍率、テーマ、ハイ コントラスト、その他の設定に合わせた画像とアセットの読み込み](images-tailored-for-scale-theme-contrast.md) | アプリで、表示倍率、テーマ、ハイ コントラスト、その他の実行時のコンテキストに合わせた画像を含む画像リソース ファイルを読み込むことができます。 |
| [言語、スケール、ハイ コントラストに合わせたタイルとトースト通知のサポート](tile-toast-language-scale-contrast.md) | タイルやトーストで、表示言語、表示倍率、ハイ コントラスト、その他の実行時のコンテキストに合わせた文字列や画像を読み込むことができます。 |
| [URI スキーム](uri-schemes.md) | アプリのパッケージ、アプリのデータ フォルダー、またはクラウドからのファイルを参照するために使用できる URI (Uniform Resource Identifier) スキームはいくつかあります。 また、URI スキームを使用して、アプリのリソース ファイル (.resw) から読み込まれた文字列を参照することもできます。 |
| [MakePri.exe を使用して手動でリソースをコンパイルする](compile-resources-manually-with-makepri.md) | MakePri.exe は、PRI ファイルを作成およびダンプするために使用できるコマンド ライン ツールです。 このツールは、Microsoft Visual Studio の MSBuild の一部として統合されていますが、パッケージを手動で作成したり、カスタム ビルド システムを使って作成する場合にも使うことができます。 |
| [MakePri.exe のコマンド ライン オプション](makepri-exe-command-options.md) | MakePri.exe には、`createconfig`、`dump`、`new`、`resourcepack`、`versioned` コマンドのセットが含まれます。 このトピックでは、コマンド ライン オプションの使用について説明します。 |
| [MakePri.exe 構成ファイル](makepri-exe-configuration.md) | ここでは、MakePri.exe XML 構成ファイルのスキーマについて説明します。 |
| [MakePri.exe の形式に固有のインデクサー](makepri-exe-format-specific-indexers.md) | このトピックでは、リソースのインデックスを生成するために MakePri.exe ツールによって使われる形式に固有のインデクサーについて説明します。 |
| [レガシ アプリやゲームで Windows 10 のリソース管理システムを使用する](using-mrt-for-converted-desktop-apps-and-games.md) | .NET または Win32 アプリやゲームを AppX パッケージとしてパッケージ化することにより、リソース管理システムを活用して実行時のコンテキストに合わせたアプリ リソースを読み込むことができます。 この詳細なトピックでは、この手法について説明します。 |

当初は Windows 8.x 用に作成されたドキュメントもご覧ください。このドキュメントは、ユニバーサル Windows プラットフォーム (UWP) のアプリや Windows 10 にも適用されます。

-   [アプリ リソースとローカライズ](https://msdn.microsoft.com/library/windows/apps/xaml/hh710212.aspx)