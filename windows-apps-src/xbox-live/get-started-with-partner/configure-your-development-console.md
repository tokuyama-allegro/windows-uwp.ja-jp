---
title: "Xbox 開発機本体を構成する"
author: KevinAsgari
description: "Xbox Live の開発をサポートするように Xbox 開発機本体を構成する方法について説明します。"
ms.assetid: f8fd1caa-b1e9-4882-a01f-8f17820dfb55
ms.author: kevinasg
ms.date: 04-04-2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: "Xbox Live, Xbox, ゲーム, UWP, Windows 10, Xbox One"
ms.openlocfilehash: 63577723e4786ce1c8bd4ca1397daefaed8accb2
ms.sourcegitcommit: 90fbdc0e25e0dff40c571d6687143dd7e16ab8a8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2017
---
# <a name="configure-your-xbox-development-console"></a>Xbox 開発機本体を構成する

開発機本体を構成するには:
- ID を取得する
- 開発キットにサンドボックスを設定する
- 開発アカウントでサインインする

## <a name="get-your-ids"></a>ID を取得する
サンドボックスと Xbox Live サービスを有効にするには、開発キットとタイトルを構成するためのいくつかの ID を取得する必要があります。 これらは同じプロセスで行うことができます。

「[Xbox Live サービス構成](../xbox-live-service-configuration.md)」に従って ID を取得します。

## <a name="set-your-sandbox-on-your-development-kits"></a>開発キットにサンドボックスを設定する
開発キットを起動するには、サンドボックス ID を設定する必要があります。 これを行うには、XDK で PC にインストールした "Xbox One Manager" を使用することも、XDK コマンド ウィンドウを開き、次のように構成コマンド (xbconfig.exe) を使用することもできます。

現在のサンドボックスを確認します。 コマンド プロンプトで「xbconfig sandboxid」と入力します。

想定したものでない場合は、サンドボックス ID を変更します。 コマンド プロンプトで「xbconfig sandboxid=<your sandbox id>」と入力します。

コマンド プロンプトで Reboot (xbreboot.exe) を使用してコンソールを再起動します。

サンドボックスが正しくリセットされたことを確認します。 コマンド プロンプトで「xbconfig sandboxid」と入力します。

## <a name="sign-in-with-a-development-account"></a>開発アカウントでサインインする

サインインに使用する開発アカウントは、[Xbox デベロッパー ポータル (XDP)](https://xdp.xboxlive.com/User/Contact/MyAccess?selectedMenu=devaccounts) または [Windows デベロッパー センター](https://developer.microsoft.com/en-us/windows)で作成できます。