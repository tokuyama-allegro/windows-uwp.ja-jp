---
title: "タイル プールで利用可能な操作"
description: "タイル プールでの操作には、タイル プールのサイズ変更、リソースの提供 (タイル プール全体のためにメモリをシステムに一時的に生成)、リソースの解放などがあります。"
ms.assetid: 90347F7F-C991-4287-BD70-494533ECDC8A
keywords: "タイル プールで利用可能な操作"
author: PeterTurcan
ms.author: pettur
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
ms.openlocfilehash: e144b42782f8479bc55dc22f8505c7cfa4455713
ms.sourcegitcommit: 909d859a0f11981a8d1beac0da35f779786a6889
translationtype: HT
---
# <a name="operations-available-on-tile-pools"></a>タイル プールで利用可能な操作


タイル プールでの操作には、タイル プールのサイズ変更、リソースの提供 (タイル プール全体のためにメモリをシステムに一時的に生成)、リソースの解放などがあります。

-   タイル プールの有効期間は 他の Direct3D リソースと似ており、参照カウントによりサポートされています (この場合は、ストリーミング リソースからのマッピングの追跡を含む)。 アプリケーションがタイル プールを参照しなくなり、メモリへのタイル マッピングがなくなって、グラフィックス処理装置 (GPU) のアクセスが完了すると、オペレーティング システムはタイル プールの割り当てを解除します。
-   サーフェスの共有と同期に関連する API は、タイル プールで機能します (ただし、ストリーミング リソースでは直接機能しません)。 提供されたタイル プールの動作と同様、タイル プールが共有されており、現在別のデバイスとプロセスにより取得されている場合、タイル プールをポイントするストリーミング リソースにアクセスする Direct3D コマンドは破棄されます。
-   プールのサイズ変更。
-   リソースの提供とリソースの解放 - システムに一時的にメモリを生成するこれらの操作は、タイル プール全体で機能します (個々のストリーミング リソースでは使うことができません)。 提供されたタイル プール内のタイルをストリーミング リソースがポイントする場合、ストリーミング リソースは提供されているかのように動作します (たとえば、ランタイムはそれを参照するコマンドを破棄します)。

タイル プール メモリとの間で直接データをコピーすることはできません。 メモリへのアクセスは、常にストリーミング リソースを通じて行われます。

## <a name="span-idrelated-topicsspanrelated-topics"></a><span id="related-topics"></span>関連トピック


[ストリーミング リソースの作成](creating-streaming-resources.md)

 

 



