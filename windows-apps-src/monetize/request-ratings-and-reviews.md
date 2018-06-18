---
author: mcleanbyron
Description: Learn about several ways you can programmatically enable customers to rate and review your app.
title: アプリの評価とレビューを求める
ms.author: mcleans
ms.date: 03/22/2018
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: Windows 10, UWP, 評価, レビュー
ms.localizationpriority: medium
ms.openlocfilehash: 8f897eeaee835c1c1bcd96e9bd843ed8f6a85612
ms.sourcegitcommit: 6618517dc0a4e4100af06e6d27fac133d317e545
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "1690378"
---
# <a name="request-ratings-and-reviews-for-your-app"></a>アプリの評価とレビューを求める

ユニバーサル Windows プラットフォーム (UWP) アプリでは、プログラムによってユーザーにアプリの評価やレビューを求めるコードを追加できます。 これを実現する方法にはいくつかあります。
* アプリのコンテキストで評価とレビュー ダイアログを直接表示する。
* Microsoft Store のアプリの評価とレビュー ページをプログラムで開く。

評価とレビューのデータを分析する準備が整ったら、Windows デベロッパー センター ダッシュボードでデータを参照するか、Microsoft Store 分析 API を使ってプログラムでこのデータを取得することができます。

## <a name="show-a-rating-and-review-dialog-in-your-app"></a>アプリ内での評価とレビュー ダイアログの表示

アプリを評価してレビューを提出するようにユーザーに求めるダイアログを、アプリ内からプログラムによって表示するには、[Windows.Services.Store](https://docs.microsoft.com/uwp/api/windows.services.store) 名前空間の [SendRequestAsync](https://docs.microsoft.com/uwp/api/windows.services.store.storerequesthelper.sendrequestasync) メソッドを呼び出します。 以下のコード例に示すように、*requestKind* パラメーターには整数 16 を渡し、*parametersAsJson* パラメーターには空の文字列を渡します。 この例では、Newtonsoft の [Json.NET](http://www.newtonsoft.com/json) ライブラリと、**Windows.Services.Store**、**System.Threading.Tasks**、**Newtonsoft.Json.Linq** の各名前空間に対する using ステートメントが必要です。

> [!IMPORTANT]
> 評価とレビュー ダイアログを表示する要求は、アプリの UI スレッドで呼び出す必要があります。

```csharp
public async Task<bool> ShowRatingReviewDialog()
{
    StoreSendRequestResult result = await StoreRequestHelper.SendRequestAsync(
        StoreContext.GetDefault(), 16, String.Empty);

    if (result.ExtendedError == null)
    {
        JObject jsonObject = JObject.Parse(result.Response);
        if (jsonObject.SelectToken("status").ToString() == "success")
        {
            // The customer rated or reviewed the app.
            return true;
        }
    }

    // There was an error with the request, or the customer chose not to
    // rate or review the app.
    return false;
}
```

**SendRequestAsync** メソッドは、シンプルな整数ベースの要求システムと JSON ベースのデータ パラメーターを使って、さまざまな Store 操作をアプリに公開します。 *requestKind* パラメーターに整数 16 を渡すと、評価とレビュー ダイアログを表示する要求を発行したことになり、関連するデータが Store に送信されます。 このメソッドは Windows 10 Version 1607 で導入され、Visual Studio で **Windows 10 Anniversary Edition (10.0、ビルド 14393)** 以降のリリースをターゲットとするプロジェクトでのみ使用できます。 このメソッドの一般的な概要については、「[Store に要求を送信する](send-requests-to-the-store.md)」をご覧ください。

### <a name="response-data-for-the-rating-and-review-request"></a>評価とレビューの要求に対する応答データ

評価とレビュー ダイアログを表示する要求を送信すると、[StoreSendRequestResult](https://docs.microsoft.com/uwp/api/windows.services.store.storesendrequestresult) の戻り値の [Response](https://docs.microsoft.com/uwp/api/windows.services.store.storesendrequestresult.Response) プロパティに、要求が成功したかどうかを示す JSON 形式の文字列が含められます。

次の例は、ユーザーが評価またはレビューを正しく提出した後のこの要求の戻り値を示しています。

```json
{ 
  "status": "success", 
  "data": {
    "updated": false
  },
  "errorDetails": "Success"
}
```

次の例は、ユーザーが評価またはレビューを提出しなかった後のこの要求の戻り値を示しています。

```json
{ 
  "status": "aborted", 
  "errorDetails": "Navigation was unsuccessful"
}
```

次の表では、JSON 形式のデータ文字列に含まれるフィールドについて説明します。

|  フィールド  |  説明  |
|----------------------|---------------|
|  *status*                   |  ユーザーから評価またはレビューが正しく提出されたかどうかを示す文字列です。 サポートされる値は **success** と **aborted** です。   |
|  *data*                   |  *updated* という名前の単一のブール値を含むオブジェクトです。 この値は、ユーザーが既存の評価またはレビューを更新したかどうかを示します。 *data* オブジェクトは、成功の応答にのみ含まれます。   |
|  *errorDetails*                   |  要求のエラーの詳細を含む文字列です。 |

## <a name="launch-the-rating-and-review-page-for-your-app-in-the-store"></a>Store でのアプリの評価とレビュー ページの起動

Store のアプリの評価とレビュー ページをプログラムによって開くには、次のコード例に示すように、```ms-windows-store://review``` URI スキームを指定して [LaunchUriAsync](https://docs.microsoft.com/uwp/api/windows.system.launcher.launchuriasync) メソッドを使用します。

```csharp
bool result = await Windows.System.Launcher.LaunchUriAsync(new Uri("ms-windows-store://review/?ProductId=9WZDNCRFHVJL"));
```

詳しくは、「[Microsoft Store アプリの起動](../launch-resume/launch-store-app.md)」をご覧ください。

## <a name="analyze-your-ratings-and-reviews-data"></a>評価とレビュー データの分析

ユーザーから提出された評価とレビューのデータを分析するには、いくつかの方法があります。
* Windows デベロッパー センター ダッシュボードの[レビュー](../publish/reviews-report.md) レポートを使って、ユーザーから提出された評価とレビューを確認できます。 このレポートは、ダウンロードしてオフラインで参照することもできます。
* Microsoft Store 分析 API の[アプリの評価の取得](get-app-ratings.md)メソッドと[アプリのレビューの取得](get-app-reviews.md)メソッドを使って、ユーザーから提出された評価とレビューをプログラムによって JSON 形式で取得できます。

## <a name="related-topics"></a>関連トピック

* [Store に要求を送信する](send-requests-to-the-store.md)
* [Microsoft Store アプリの起動](../launch-resume/launch-store-app.md)
* [[レビュー] レポート](../publish/reviews-report.md)