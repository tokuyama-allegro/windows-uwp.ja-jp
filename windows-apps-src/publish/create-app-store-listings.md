---
description: アプリの申請プロセスの [Store 登録情報] セクションでは、ユーザーが Microsoft Store でアプリの登録情報を表示したときに表示されるテキストと画像を指定できます。
title: アプリのストア登録情報の作成
ms.assetid: 50D67219-B6C6-4EF0-B76A-926A5F24997D
ms.date: 03/13/2019
ms.topic: article
keywords: windows 10, uwp, 登録情報, 説明, Microsoft Store ページ, リリース ノート, タイトル
ms.localizationpriority: medium
ms.openlocfilehash: cb895dcabcc72361575f2d160b10fade03905d9a
ms.sourcegitcommit: a3bbd3dd13be5d2f8a2793717adf4276840ee17d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "93033295"
---
# <a name="create-app-store-listings"></a>アプリのストア登録情報の作成

[アプリの申請プロセス](app-submissions.md)の **[Store 登録情報]** セクションでは、ユーザーが Microsoft Store でアプリの登録情報を表示したときに表示されるテキストと [画像](app-screenshots-and-images.md)を指定できます。

**[Store 登録情報]** のフィールドの多くは省略可能ですが、登録情報が目立つように複数の画像とできるだけ多くの情報を指定することをお勧めします。 **[Store 登録情報]** の手順が完成したと見なされるには、説明のテキストと少なくとも 1 つの [スクリーンショット](app-screenshots-and-images.md#screenshots)が必要です。

> [!TIP]
> 情報を提供したり、ファイルをパートナーセンターに直接アップロードするのではなく、.csv ファイルにリスト情報をオフラインで入力する場合は、必要に応じて [ストアの一覧をインポートおよびエクスポート](import-and-export-store-listings.md) することができます。 インポートおよびエクスポート オプションでは、一度に複数の更新を行うことができるため、多くの言語の登録情報がある場合に特に便利です。

以前に発行されたアプリで Windows 8.x または Windows Phone 2.x 以前がサポートされている場合は、それらの顧客に表示する [プラットフォーム固有のストアの一覧を作成](create-platform-specific-store-listings.md) できます。

## <a name="store-listing-languages"></a>ストア登録情報の言語

少なくとも 1 つの言語の **[ストア登録情報]** ページを完成させる必要があります。 ストア登録情報は、パッケージでサポートしているすべての言語で提供することをお勧めしますが、ストア登録情報を提供しない言語を削除することもできます。 パッケージでサポートしていない言語のストア登録情報を作成することもできます。

> [!NOTE]
> 申請にパッケージが既に含まれている場合は、パッケージでサポートされている[言語](supported-languages.md)が [申請の概要] ページに表示されます (言語を削除していない場合)。

ストア登録情報の言語を追加または削除するには、申請の概要ページで **[言語の追加/削除]** をクリックします。 既にパッケージをアップロードしている場合は、 **[Languages supported by your packages]** (パッケージでサポートしている言語) セクションに言語が表示されます。 これらの言語の 1 つまたは複数を削除するには、 **[削除]** をクリックします。 以前にこのセクションから削除した言語を後で含める場合は、 **[加算]** をクリックします。

**[ストア登録情報の追加言語]** セクションで、 **[追加言語の管理]** をクリックして、パッケージに含まれて *いない* 言語を追加するか、パッケージに含めない言語を削除します。 追加する言語のチェック ボックスをクリックし、 **[更新]** をクリックします。 選択した言語が **[ストア登録情報の追加言語]** セクションに表示されます。 1 つまたは複数の言語を削除するには、 **[削除]** をクリックします (または、 **[追加言語の管理]** をクリックし、削除する言語のチェック ボックスをオフにします)。

選択が終了したら **[保存]** をクリックして、申請の概要ページに戻ります。

## <a name="add-and-edit-store-listing-info"></a>ストアリスティング情報の追加と編集

ストアの一覧を編集するには、[送信の概要] ページから言語名を選択します。 ストアの一覧をエクスポートしてオフラインで作業することを選択していない場合は、各言語を個別に編集し、すべてのリスティングデータを一度にインポートする必要があります。 そのしくみの詳細については、「 [ストアの一覧のインポートとエクスポート](import-and-export-store-listings.md)」を参照してください。

使用できるフィールドを次に示します。

## <a name="product-name"></a>製品名

このドロップダウンボックスでは、ストアの一覧で使用する名前を指定できます (アプリに複数の名前を予約している場合)。

作業中のストアの一覧と同じ言語でパッケージをアップロードした場合は、それらのパッケージで使用される名前が選択されます。 アプリが既に発行された後で [名前を変更](manage-app-names.md#rename-an-app-that-has-already-been-published) する必要がある場合は、新しい名前を使用するパッケージをアップロードした後で、新しい送信を作成するときに、ここで別の予約名を選択できます。

作業中の言語に対してパッケージをアップロードしていないときに、複数の名前を予約している場合は、予約済みのアプリ名のいずれかを選択する必要があります。これは、その言語で名前を取得するためのパッケージが関連付けられていないためです。

> [!NOTE]
> 選択した **製品名** は、使用している言語のストアの一覧にのみ適用されます。 顧客がアプリをインストールするときに表示される名前には影響しません。この名前は、インストールされるパッケージのマニフェストから取得されます。 混乱を避けるために、各言語のパッケージとストアの一覧で同じ名前を使用することをお勧めします。

## <a name="description"></a>説明

説明フィールドでは、アプリの内容をユーザーに伝えることができます。 このフィールドは必須であり、最大 10,000 文字のプレーンテキストを入力できます。

説明を目立たせるためのヒントについては、「[人の心をつかむアプリの説明を書く](write-a-great-app-description.md)」をご覧ください。

<a name="release-notes"></a>

## <a name="whats-new-in-this-version"></a>今回のバージョンでの新機能

初めてアプリを申請する場合、このフィールドは空白のままにしてください。 既存のアプリを更新する場合は、最新のリリースで変更内容をお客様に知らせることができます。 このフィールドには 1,500 文字の制限があります。 (以前は、このフィールドは **[リリース ノート]** と呼ばれていました)。

## <a name="product-features"></a>製品の機能

アプリの主な機能の短い概要です。 これらは、アプリの Store 登録情報の **[機能]** セクションに、 **[説明]** と共に箇条書きの形式で表示されます。 各機能につき短い 1 文 (かつ、200 文字未満) になるようにまとめます。 最大 20 の機能を含めることができます。

> [!NOTE]
> これらの機能はストアの一覧に箇条書きとして表示されるため、独自の箇条書きを追加しないでください。

## <a name="screenshots"></a>Screenshots (スクリーンショット)

アプリを提出するには、少なくとも 1 つのスクリーンショットが必要です。 ユーザーが自分が使っている種類のデバイスでアプリがどのように表示されるかをイメージできるように、アプリがサポートするデバイスの種類ごとに少なくとも 4 つのスクリーンショットを用意することをお勧めします。

詳しくは、「[アプリのスクリーンショットと画像](app-screenshots-and-images.md#screenshots)」をご覧ください。

## <a name="store-logos"></a>ストア ロゴ

ストア ロゴは、アプリの情報をより適切にユーザーに表示するためにアップロードできるオプションの画像です。 必要に応じて、ここでアップロードした画像を Windows 10 (Xbox を含む) ユーザー向けのアプリの Store 登録情報に使うように指定して、アプリのパッケージからのロゴ画像が Microsoft Store で使われないようにすることもできます。

> [!IMPORTANT]
> アプリが Xbox をサポートしている場合、または Windows Phone 8.1 以前をサポートしている場合、ストアで登録情報が適切に表示されるようにするには、ここで特定の画像を提供する必要があります。

詳しくは、「[ストア ロゴ](app-screenshots-and-images.md#store-logos)」をご覧ください。

## <a name="trailers-and-additional-assets"></a>トレーラーとその他の資産

ビデオのトレーラーやプロモーション用の画像など、製品の追加資産を送信できます。 これらはいずれも省略可能ですが、できるだけ多くの資産のアップロードを検討することをお勧めします。 これらの画像は、より魅力的な登録情報を作成し、製品がどのようなものかをユーザーに知ってもらうために役立ちます。

詳細については、「 [トレーラーとその他の資産](app-screenshots-and-images.md#trailers-and-additional-assets)」を参照してください。

<a name="supplemental-information"></a>

## <a name="supplemental-fields"></a>補足フィールド

このセクションのフィールドはすべてオプションです。 以下の情報を確認し、申請でこの情報を提供する意味があるかどうかを判断してください。 特に、ほとんどの申請では **簡単な説明** をお勧めします。 他のフィールドは、さまざまなシナリオで製品の最適なエクスペリエンスを実現するのに役立つ場合があります。

### <a name="short-title"></a>短いタイトル

製品の名前の短いバージョン。 指定した場合、Xbox One のさまざまな場所 (インストール時や [実績] など) で製品のフル タイトルの代わりにこの短い名前が表示されることがあります。

このフィールドには 50 文字の制限があります。

### <a name="sort-title"></a>ソート タイトル

製品のアルファベット表記やスペルが複数ある場合、ここに別のバージョンを入力できます。 これにより、ユーザーが検索時にそのバージョンを入力した場合に製品をすばやく見つけることができるようになります。

このフィールドには 255 文字の制限があります。

### <a name="voice-title"></a>音声タイトル

Kinect やヘッドセットを使うときに Xbox One のオーディオ エクスペリエンスで使われる、製品の代替名 (ある場合)。

このフィールドには 255 文字の制限があります。

### <a name="short-description"></a>簡単な説明

製品の Store 登録情報の先頭に使うことができる短くてわかりやすい説明です。 指定しない場合、長い[説明](#description)の最初の段落 (最大 500 の文字) が代わりに説明されます。 説明はこのテキストの下にも表示されるため、Store 登録情報が繰り返されないように内容が異なる簡単な説明を指定することをお勧めします。

ゲームの場合、簡単な説明は Xbox One のゲーム ハブの [情報] セクションにも表示されることがあります。

最良の結果を得るには、簡単な説明を270文字以内に保存します。 フィールドには1000文字の制限がありますが、一部のビューでは、最初の270文字のみが表示されます (短い説明の残りの部分を表示するためのリンクがあります)。

### <a name="additional-system-requirements"></a>Additional system requirements

必要に応じて、アプリが正常に動作するうえで必要となるハードウェア構成を記述できます ( [アプリのプロパティ](enter-app-properties.md#system-requirements)の **[システム必要条件]** セクションに指定した情報以外)。 この情報は、一部のコンピューターでしか使うことができないハードウェアが必要なアプリの場合、特に重要です。 たとえば、3D プリンターやマイクロコントローラーなどの外部 USB ハードウェアがある場合にのみ、アプリケーションが正常に動作する場合は、ここにその情報を入力することをお勧めします。 入力した情報は、製品のプロパティ ページで指定した要件と共に、Windows 10 バージョン 1607 以降 (Xbox を含む) でアプリの Store 登録情報を表示するユーザーに表示されます。

**[最小ハードウェア要件]** と **[推奨されるハードウェア]** の両方に最大 11 個の項目を入力できます。 これらは、Store 登録情報に箇条書きの形式で表示されます。 各項目につき短い 1 文 (かつ、200 文字未満) になるようにまとめます。

> [!NOTE]
> 追加のシステム要件は、Store 登録情報に箇条書きの項目として表示されるため、独自に行頭文字を追加しないでください。

<a name="shared-fields"></a>

## <a name="additional-information"></a>関連情報

以下に説明する項目は、ユーザーにとって製品を見つけやすくしたり、製品の理解を助けたりするために役立ちます。 (このセクションは以前、 **共有フィールド** と呼ばれていました)。

### <a name="search-terms"></a>検索語句

検索語句は (以前はキーワードと呼ばれていました)、ユーザーには表示されない単語または短いフレーズで、ユーザーがそれらの語句を使って検索したときに Microsoft Store でアプリを見つけやすくすることができます。 最大 7 個の検索語句を含めることができ、それぞれの語句の最大長は 30 文字です。すべての検索語句を合わせて使用できる個々の単語の数は 21 個までです。

検索語句を追加するとき、特にアプリ名の一部ではない語句を追加する場合は、同様のアプリを検索する際にユーザーが使いそうな単語を考えてください。 アプリに実際に関連しない検索語句は使わないでください。

### <a name="copyright-and-trademark-info"></a>著作権と商標の情報

その他の著作権や商標の情報を指定する場合は、ここに入力します。 このフィールドには 200 文字の制限があります。

### <a name="additional-license-terms"></a>追加のライセンス条項

「 **標準アプリケーション ライセンス条項** 」(「 [アプリ開発者契約](/legal/windows/agreements/app-developer-agreement)」からリンクされています) の条項に基づいて、アプリのライセンスをユーザーに付与する場合は、このフィールドを空白にします。

アプリのライセンス条項が「 **標準アプリケーション ライセンス条項** 」と異なる場合は、ここに入力します。

このフィールドに 1 つの URL を入力すると、ユーザーがクリックして追加のライセンス条項を読むことができるリンクとして表示されます。 これは、追加のライセンス条項が非常に長い場合や、追加のライセンス条項にクリック可能なリンクや書式設定を含める場合に便利です。

さらに、このフィールドには最大で 10,000 文字のテキストを入力できます。 この場合、これらの追加のライセンス条項は、ユーザーに対してプレーンテキストとして表示されます。

### <a name="developed-by"></a>Developed by (開発元)

アプリのストア登録情報に **[Developed by] (開発元)** フィールドを含める場合は、ここにテキストを入力します  ( **[Developed by] (開発元)** フィールドに値を入力していかどうかには関係なく、 **[公開元]** フィールドにはアカウントに関連付けられた発行者の表示名が示されます)。

このフィールドには 255 文字の制限があります。
 
<a name="privacy-policy"></a>

> [!NOTE]
> **[プライバシー ポリシー]** 、 **[Web サイト]** 、 **[サポートの問い合わせ先情報]** の各フィールドは、 [[プロパティ]](enter-app-properties.md) ページに移動しました。
