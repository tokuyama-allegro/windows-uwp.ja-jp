---
author: eliotcowley
title: 取得し、バーコード データを理解します。
description: 入手をスキャンするバーコード データを解釈する方法について説明します。
ms.author: elcowle
ms.date: 08/29/2018
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: Windows 10, UWP, 店舗販売時点管理, POS
ms.localizationpriority: medium
ms.openlocfilehash: 0992ea54092063ba53f23871599905e58f1b456e
ms.sourcegitcommit: 72710baeee8c898b5ab77ceb66d884eaa9db4cb8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2018
ms.locfileid: "3848686"
---
# <a name="obtain-and-understand-barcode-data"></a>取得し、バーコード データを理解します。

バーコード スキャナーをセットアップした後は、もちろん方法をスキャンするデータの理解の必要があります。 バーコードをスキャンする[DataReceived](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.claimedbarcodescanner.datareceived)イベントが発生します。 [ClaimedBarcodeScanner](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.claimedbarcodescanner)は、このイベントにサブスクライブする必要があります。 **DataReceived**イベントは、バーコード データにアクセスするために使用できる、 [BarcodeScannerDataReceivedEventArgs](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodescannerdatareceivedeventargs)オブジェクトを渡します。

## <a name="subscribe-to-the-datareceived-event"></a>DataReceived イベントにサブスクライブします。

**ClaimedBarcodeScanner**したら、 **DataReceived**イベントをサブスクライブすることがあります。

```cs
claimedBarcodeScanner.DataReceived += ClaimedBarcodeScanner_DataReceived;
```

イベント ハンドラーは、 **ClaimedBarcodeScanner**と**BarcodeScannerDataReceivedEventArgs**オブジェクトが渡されます。 このオブジェクトの[レポート](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodescannerdatareceivedeventargs.report#Windows_Devices_PointOfService_BarcodeScannerDataReceivedEventArgs_Report)プロパティの型は[BarcodeScannerReport](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodescannerreport)でバーコード データにアクセスすることができます。

```cs
private async void ClaimedBarcodeScanner_DataReceived(ClaimedBarcodeScanner sender, BarcodeScannerDataReceivedEventArgs args)
{
    // Parse the data
}
```

## <a name="get-the-data"></a>データを取得します。

**BarcodeScannerReport**したらにアクセスし、バーコード データを解析できます。 **BarcodeScannerReport**では、3 つのプロパティがあります。

* [ScanData](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodescannerreport.scandata): 完全な生のバーコード データ。
* [ScanDataLabel](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodescannerreport.scandatalabel): バーコードがデコードのラベル、ヘッダー、チェックサム、およびその他の情報は含まれません。
* [ScanDataType](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodescannerreport.scandatatype): バーコードがデコードされたラベルの種類。 設定可能な値は、 [BarcodeSymbologies](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodesymbologies)クラスで定義されます。

**ScanDataLabel**または**ScanDataType**のいずれかにアクセスする場合は、 **true**を[IsDecodeDataEnabled](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.claimedbarcodescanner.isdecodedataenabled#Windows_Devices_PointOfService_ClaimedBarcodeScanner_IsDecodeDataEnabled)を設定する必要があります。

```cs
claimedBarcodeScanner.IsDecodeDataEnabled = true;
```

### <a name="get-the-scan-data-type"></a>スキャン データの種類を取得します。

バーコードがデコードされたラベルの種類を取得するは非常に単純な&mdash; **ScanDataType**で[GetName](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodesymbologies.getname)を呼び出すことだけです。

```cs
private string GetSymbology(BarcodeScannerDataReceivedEventArgs args)
{
    return BarcodeSymbologies.GetName(args.Report.ScanDataType);
}
```

### <a name="get-the-scan-data-label"></a>スキャン データのラベルを取得します。

デコードされたバーコード ラベルを取得するのには、注意すべきがあるいくつかの点があります。 特定のデータ型のみ含めるエンコードされたテキスト、できないため、まずかどうか、シンボル体系は、文字列に変換でき、utf-8 エンコードされた文字列を**ScanDataLabel**から入手して、バッファーを変換をチェックする必要があります。

```cs
private string GetDataLabel(BarcodeScannerDataReceivedEventArgs args)
{
    uint scanDataType = args.Report.ScanDataType;

    // Only certain data types contain encoded text.
    // To keep this simple, we'll just decode a few of them.
    if (args.Report.ScanDataLabel == null)
    {
        return "No data";
    }

    // This is not an exhaustive list of symbologies that can be converted to a string.
    else if (scanDataType == BarcodeSymbologies.Upca ||
        scanDataType == BarcodeSymbologies.UpcaAdd2 ||
        scanDataType == BarcodeSymbologies.UpcaAdd5 ||
        scanDataType == BarcodeSymbologies.Upce ||
        scanDataType == BarcodeSymbologies.UpceAdd2 ||
        scanDataType == BarcodeSymbologies.UpceAdd5 ||
        scanDataType == BarcodeSymbologies.Ean8 ||
        scanDataType == BarcodeSymbologies.TfStd)
    {
        // The UPC, EAN8, and 2 of 5 families encode the digits 0..9
        // which are then sent to the app in a UTF8 string (like "01234").
        return CryptographicBuffer.ConvertBinaryToString(BinaryStringEncoding.Utf8, args.Report.ScanDataLabel);
    }

    // Some other symbologies (typically 2-D symbologies) contain binary data that
    // should not be converted to text.
    else
    {
        return "Decoded data unavailable.";
    }
}
```

### <a name="get-the-raw-scan-data"></a>スキャンの生データを取得します。

"完全"を取得するのに、バーコードからの生データしますだけ変換、バッファーの文字列に**ScanData**から取得します。

```cs
private string GetRawData(BarcodeScannerDataReceivedEventArgs args)
{
    // Get the full, raw barcode data.
    if (args.Report.ScanData == null)
    {
        return "No data";
    }

    // Just to show that we have the raw data, we'll print the value of the bytes.
    else
    {
        return CryptographicBuffer.ConvertBinaryToString(BinaryStringEncoding.Utf8, args.Report.ScanData);
    }
}
```

これらのデータには、一般に、ように、スキャナーから配信される形式です。 メッセージのヘッダーとトレーラーは削除されます。 ただし、ため、アプリケーションに関する有用な情報が含まれていませんがスキャナーに固有のする可能性があります。

一般的なヘッダー情報は、プレフィックス文字 (STX 文字の場合) などです。 一般的なトレーラー情報は、(ETX または変更リクエスト文字では) などの終端文字とブロック チェック文字場合は 1 つは、スキャナーによって生成されます。

いずれかがスキャナーで返された場合、このプロパティはシンボル体系の文字を含める必要があります (の**A**など、UPC A)。 ラベルに存在する場合も、チェック桁の数字を含める必要があります、スキャナーで返されます。 (するシンボル体系文字とチェック ディジットの両方かできない可能性がある、スキャナーの構成によってに注意してください。 スキャナーが戻す場合は、表示しますが、生成またはされませんこれらが存在しない場合は、それらを計算します)。

補足的なバーコードでは、いくつかの商品をマークする可能性があります。 このバーコードは通常、メインのバーコードの右側に配置され、情報の追加 2 または 5 文字で構成されます。 含むメインと補助の両方のバーコード スキャナーは、商品を読み取る場合、補足的な文字がメインの文字に付加され、結果は、アプリケーションを 1 つのラベルとに配信されます。 (メモ、スキャナーがまたは補足的なコードの読み取りを無効にする構成をサポート可能性があります。)

一部の商品は、 *multisymbol ラベル*または*階層型のラベル*とも呼ばれる、複数のラベルでマークする可能性があります。 これらのバーコードは、垂直方向に配置されて通常して、同じまたは別のシンボル体系の可能性があります。 スキャナーは、複数のラベルが含まれている商品を読み取り、各バーコードは、アプリケーションを別のラベルとに配信されます。 現在、これらのバーコードの種類の標準化不足のために必要です。 個々 のバーコード データに基づいてすべてのバリエーションを特定することがあります。 アプリケーションでは、複数のラベル バーコードがされて読み取り時から返されるデータに基づいて判断する必要があります。 (詳しくは、スキャナーが場合も、複数のラベルの読み取り値をサポートしていませんを注意してください)。

この値は、アプリケーションに発生する**DataReceived**イベントの前に設定されます。

[!INCLUDE [feedback](./includes/pos-feedback.md)]

## <a name="see-also"></a>関連項目
* [バーコード スキャナー](pos-barcodescanner.md)
* [ClaimedBarcodeScanner クラス](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodesymbologies.getname)
* [BarcodeScannerDataReceivedEventArgs クラス](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodescannerdatareceivedeventargs)
* [BarcodeScannerReport クラス](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodescannerreport)
* [BarcodeSymbologies クラス](https://docs.microsoft.com/uwp/api/windows.devices.pointofservice.barcodesymbologies)