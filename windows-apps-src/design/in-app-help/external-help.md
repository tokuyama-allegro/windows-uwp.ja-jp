---
author: QuinnRadich
Description: Design external help pages for detailed instructions and advice about your app.
title: 外部ヘルプ ページを設計するためのガイドライン
label: External help
template: detail.hbs
ms.author: quradic
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: windows 10, uwp
ms.assetid: 56afd553-c520-4a28-b63d-2e1b3c1d3606
ms.localizationpriority: medium
ms.openlocfilehash: c938eea2e7a161eedc94bbcd75fa567fb2a32025
ms.sourcegitcommit: f9a4854b6aecfda472fb3f8b4a2d3b271b327800
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2017
ms.locfileid: "1392511"
---
# <a name="external-help-pages"></a>外部ヘルプ ページ



アプリが、複雑なコンテンツを使った詳細なヘルプを必要とする場合は、それらの説明を Web ページでホストすることを検討します。

## <a name="when-to-use-external-help-pages"></a>外部ヘルプ ページを使用する状況

外部ヘルプ ページは、一般的な用途やクイック リファレンスとしては利便性が劣ります。 これはアプリ自体に組み込むには大きすぎるヘルプ コンテンツに適しています。またチュートリアルや、一般のユーザーにはあまり使われないアプリの高度な機能の説明などにも適しています。

ヘルプ コンテンツが簡潔な場合、またアプリ内の特定の場合に表示するのが望ましい場合には、アプリ内のヘルプを使います。 必要のない限り、ヘルプのためにユーザーをアプリの外部に誘導しないようにします。

## <a name="navigating-external-help-pages"></a>外部ヘルプ ページのナビゲーション

ユーザーを外部ヘルプ ページに転送する場合は、次の 2 つのシナリオのいずれかを使用します。
-   既知の問題に対応するページに直接リンクします。 これはコンテキスト ヘルプであり、可能な場合には使用する必要があります。
-   選択するカテゴリとサブカテゴリが明確に表示されている、一般的なヘルプページにリンクします。

ユーザーがヘルプを検索できるようにすることは有用ですが、検索がヘルプ操作の唯一の方法とならないようにします。 ユーザーが問題を記述しにくいこともあり、その場合には検索が困難になります。 ユーザーが検索をしなくても、問題に関連のあるページをすぐに見つけられるようにします。

## <a name="tutorials-and-detailed-walkthroughs"></a>チュートリアルと詳細なウォークスルー

外部ヘルプ ページは、ビデオやテキストを使って、ユーザーにチュートリアルや詳細なウォークスルーを提供するのに最適です。
-   チュートリアルでは、より複雑な用途や高度な機能に焦点を当てます。 ユーザーがアプリを使うためには、チュートリアルを必要としないようにします。
-   チュートリアルは標準のヘルプとは異なる方法で表示されるようにします。 高度な使い方を求めているユーザーは、問題に対する直接の解決策を求めるユーザーよりも、より進んで検索を行います。
-   ディレクトリと各チュートリアルに対応する個々のヘルプ ページの両方から、チュートリアルへのリンクを行うことを検討します。

## <a name="related-articles"></a>関連記事

* [アプリのヘルプのガイドライン](guidelines-for-app-help.md)