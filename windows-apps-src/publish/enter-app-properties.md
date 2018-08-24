---
author: jnHs
Description: The App properties page of the app submission process lets you define your app's category and indicate hardware preferences or other declarations.
title: アプリのプロパティの入力
ms.assetid: CDE4AF96-95A0-4635-9D07-A27B810CAE26
ms.author: wdg-dev-content
ms.date: 08/07/2018
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: windows 10, uwp, ゲーム設定, 表示モード, システム要件, ハードウェア要件, 最小ハードウェア, 推奨されるハードウェア, プライバシー ポリシー, サポートの問い合わせ先情報, アプリ Web サイト, サポート情報
ms.localizationpriority: medium
ms.openlocfilehash: d23fb0cb3fb4668682df1957cbf0c88bcf8649c1
ms.sourcegitcommit: c6d6f8b54253e79354f8db14e5cf3b113a3e5014
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2018
ms.locfileid: "2830521"
---
# <a name="enter-app-properties"></a>アプリのプロパティの入力

[アプリの申請プロセス](app-submissions.md)の **[プロパティ]** ページでは、アプリのカテゴリを定義し、他の情報や宣言を入力します。 このページでは、アプリに関する完全な詳細情報を正確に指定してください。


## <a name="category-and-subcategory"></a>カテゴリとサブカテゴリ

Microsoft Store でアプリの分類に使うカテゴリを (該当する場合はサブカテゴリ/ジャンルも) 示す必要があります。 アプリを提出するには、カテゴリを指定することが必要です。

詳しくは、「[カテゴリとサブカテゴリの一覧](category-and-subcategory-table.md)」をご覧ください。


## <a name="support-info"></a>サポート情報

このセクションでは、ユーザーがアプリの詳細とサポートを受ける方法について理解するのに役立つ情報を入力できます。

### <a name="privacy-policy-url"></a>プライバシー ポリシーの URL

開発者は、アプリをプライバシーに関する法令と規制に準拠させ、必要に応じてプライバシー ポリシーの有効な URL をここで提供する責任があります。

このセクションでは、アプリが[個人情報](https://docs.microsoft.com/legal/windows/agreements/store-policies#105-personal-information)へのアクセス、収集、送信を行うかどうかを指定する必要があります。 **[はい]** と回答した場合、プライバシー ポリシーの URL が必要です。 それ以外の場合、これは任意です (ただし、アプリにプライバシー ポリシーが必要と判断されたが、用意されていない場合、申請が認定に合格しない可能性があります)。

> [!NOTE]
> 個人情報へのアクセス、送信、収集を許可する可能性がある[機能](../packaging/app-capability-declarations.md)をパッケージが宣言していることが検出された場合、この質問が **[はい]** とマークされ、プライバシー ポリシーの URL の入力が必須になります。

アプリにプライバシー ポリシーが必要かどうかを確認するには、「[アプリ開発者契約](https://docs.microsoft.com/legal/windows/agreements/app-developer-agreement)」と「[Microsoft Store ポリシー](https://docs.microsoft.com/legal/windows/agreements/store-policies#105-personal-information)」をご覧ください。 

> [!NOTE]
> Microsoft では、アプリ用の既定のプライバシー ポリシーは用意していません。 同様に、アプリは Microsoft のプライバシー ポリシーの対象にはなりません。 


### <a name="website"></a>Web サイト

アプリの Web ページの URL を入力します。 この URL は、Microsoft Store のアプリの登録情報 Web ページではなく、独自の Web サイトのページを指すものにする必要があります。 このフィールドは任意ですが、使用することをお勧めします。

### <a name="support-contact-info"></a>サポートの問い合わせ先情報

アプリのサポートをユーザーに提供する Web ページの URL、またはユーザーがサポートに連絡するためのメール アドレスを入力します。 ユーザーが必要な場合にサポートを受ける方法を知ることができるように、すべての申請にこの情報を含めることをお勧めします。 Microsoft がアプリのサポートをユーザーに提供することはない点に注意してください。

> [!IMPORTANT]
> **[サポートの問い合わせ先情報]** フィールドは、アプリやゲームが Xbox で使用可能な場合に必須です。 それ以外の場合、これは任意です (ただし、推奨されます)。


## <a name="game-settings"></a>ゲーム設定

このセクションは、製品のカテゴリとして **[ゲーム]** を選択した場合にのみ表示されます。 ここでは、ゲームがサポートしている機能を指定できます。 このセクションで指定した情報はすべて、製品のストア登録情報に表示されます。

ゲームでマルチプレイヤー オプションのいずれかをサポートしている場合は、セッションあたりの最小プレイヤー数と最大プレイヤー数を指定してください。 最小または最大のプレイヤー数として 1,000 人より大きい値を入力することはできません。

**[クロスプラットフォーム マルチプレイヤー]** は、ゲームが Windows 10 PC と Xbox のプレイヤー間のマルチプレイヤー セッションをサポートしていることを示します。


## <a name="display-mode"></a>表示モード

このセクションでは、PC または HoloLens デバイス、あるいはその両方で、[Windows Mixed Reality](https://developer.microsoft.com/windows/mixed-reality) の (2D 表示でなく) イマーシブ ビューでの実行用に製品が設計されているかどうかを示します。 該当する場合は、次の操作も必要になります。
- **[プロパティ]** ページの後半に表示される [[システム要件]](#system-requirements) セクションで、**[Windows Mixed Reality イマーシブ ヘッドセット]** について **[最小ハードウェア要件]** または **[推奨されるハードウェア]** を選択します。
- PC を選択した場合は、アプリを座った状態のみまたは立った状態のみで使用するのか、使用中にさまざまな場所に移動できる (または移動する必要がある) のかをユーザーが判断できるように、**[境界線のセットアップ]** も指定します。 

製品のカテゴリとして **[ゲーム]** を選択した場合は、**[表示モード]** に追加のオプションが表示されます。ここでは、4K 解像度のビデオ出力、ハイ ダイナミック レンジ (HDR) のビデオ出力、可変リフレッシュ レートの表示を製品がサポートしているかどうかを指定できます。

製品がこれらの表示モード オプションをサポートしていない場合は、すべてのチェック ボックスをオフにしておきます。


## <a name="product-declarations"></a>製品の宣言

アプリにいずれかの宣言を適用するかどうかを指定するには、このセクションのチェック ボックスを使います。 これは、アプリがどのように表示されるか、特定のユーザーに提供されるかどうか、またはユーザーがアプリをどのように使うことができるかに影響を与える可能性があります。

詳しくは、「[製品の宣言](app-declarations.md)」をご覧ください。

## <a name="system-requirements"></a>システム要件

このセクションには、アプリを正常に実行して操作するために特定のハードウェア機能が必要かどうか、または推奨されているかどうかを指定するオプションがあります。 各ハードウェア項目を **[最小ハードウェア]** か **[推奨されるハードウェア]** (またはその両方) として指定するチェック ボックスをオンにできます (または該当するオプションを指定できます)。

**[推奨されるハードウェア]** を選択すると、製品のストア登録情報で、Windows 10 バージョン 1607 以降のユーザーに対し、それらの項目は推奨されるハードウェアとして表示されます。 それより前の OS バージョンのユーザーには、この情報は表示されません。

**[最小ハードウェア]** を選択すると、製品のストア登録情報で、Windows 10 バージョン 1607 以降のユーザーに対し、それらの項目は必須ハードウェアとして表示されます。 それより前の OS バージョンのユーザーには、この情報は表示されません。 また、ストアでは、必須ハードウェアのないデバイスでアプリの登録情報を表示しているユーザーに対して警告を表示することもできます。 これによって該当するハードウェアを持っていないデバイスへのアプリのダウンロードができなくなることはありませんが、それらのデバイスではアプリの評価をしたりレビューを書いたりすることはできません。 

ユーザーの動作は、特定の要件とユーザーの Windows のバージョンによって次のように異なります。

- **Windows 10 バージョン 1607 以降のユーザー:**
     - ストア登録情報に、最小要件と推奨要件のすべてが表示されます。
     - ストアによってすべての最小要件がチェックされ、要件を満たさないデバイスでは警告が表示されます。
- **それより前のバージョンの Windows 10 のユーザー:**
     - ほとんどのユーザーに関しては、すべての最小ハードウェア要件と推奨されるハードウェア要件がストア登録情報に表示されます (前のバージョンのストア クライアントを表示しているユーザーの場合には、最小ハードウェア要件しか表示されません)。
     - **[最小ハードウェア]** として指定した項目の検証がストアによって試みられます。ただし、**メモリ**、**DirectX**、**ビデオ メモリ**、**グラフィックス**、**プロセッサ**は例外で、これらについては検証が行われず、要件を満たしていないデバイスに関する警告は表示されません。 
- **Windows 8.x 以前および Windows Phone 8.x 以前のユーザー:**
     - **[タッチ スクリーン]** の **[最小ハードウェア]** チェック ボックスをオンにすると、この要件がアプリのストア登録情報に表示されます。また、タッチ スクリーンのないデバイスのユーザーがアプリをダウンロードしようとすると、警告が表示されます。 その他の要件については、検証も行われませんし、ストア登録情報に表示もされません。

また指定したハードウェアについての実行時のチェックをアプリにも追加することをお勧めします。これは、選択した機能がユーザーのデバイスにないことをストアが常に検出できるとは限らず、また、警告が表示されていてもユーザーはアプリをダウンロードできるためです。 メモリや DirectX レベルの最小要件を満たしていないデバイスに UWP アプリをまったくダウンロードできないようにするには、[StoreManifest XML ファイル](https://docs.microsoft.com/uwp/schemas/storemanifest/storemanifestschema2015/schema-root)で最小要件を指定します。

> [!TIP]
> 3D プリンターや USB デバイスなど、製品が正常に動作するためにこのセクションに示されていない追加の項目を必要とする場合、Store 登録情報を作成するときに、[追加のシステム要件](create-app-store-listings.md#additional-system-requirements)を入力することもできます。




