---
description: 空白文字、改行、およびタブを処理するために XAML によって使用される規則について説明します。
title: XAML と空白
ms.assetid: 025F4A8E-9479-4668-8AFD-E20E7262DC24
ms.date: 02/08/2017
ms.topic: article
keywords: windows 10, uwp
ms.localizationpriority: medium
ms.openlocfilehash: 16d5b0b3faa4d356ced2eb352192bd1a91882475
ms.sourcegitcommit: 45dec3dc0f14934b8ecf1ee276070b553f48074d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "89094629"
---
# <a name="xaml-and-whitespace"></a>XAML と空白


XAML で使われる空白処理規則について説明します。

## <a name="whitespace-processing"></a>空白処理

XML との一貫性、XAML の空白文字は、スペース、改行、およびタブです。これらは、それぞれ Unicode 値0020、000A、および0009に対応します。 既定では、XAML プロセッサが XAML ファイル内の要素間にある内部テキストを検出すると、この空白の正規化が行われます。

-   東アジア言語の文字間の改行文字が削除されます。
-   すべての空白文字 (スペース、改行、タブ) は、スペースに変換されます。
-   連続した複数のスペースはすべて削除され、1 つのスペースに置換されます。
-   開始タグの直後にあるスペースは削除されます。
-   終了タグの直前にあるスペースは削除されます。
-   *東アジアの文字*は、Unicode 文字範囲 U+20000 から U+2FFFD と U+30000 から U+3FFFD のセットとして定義されます。 このサブセットは、 *CJK 表意文字*と呼ばれることもあります。 詳細については、「http://www.unicode.org」を参照してください。

"既定" とは、 **xml:space** 属性の既定値で表される状態に対応します。

### <a name="whitespace-in-inner-text-and-string-primitives"></a>内部テキスト内の空白と文字列のプリミティブ

上で説明した正規化規則は、XAML 要素内の内部テキストに適用されます。 正規化の後、XAML プロセッサが次のように内部テキストを適切な型に変換します。

-   プロパティの型がコレクションではないが、直接的には **Object** 型ではない場合、XAML プロセッサは型コンバーターを使って型の変換を試みます。 ここで変換が失敗すると、XAML 解析エラーになります。
-   プロパティの型がコレクションで、内部テキストが連続的である (介在する要素タグがない) 場合、内部テキストは単一の **String** として解析されます。 コレクションの型で **String** が許容されていない場合も、XAML 解析エラーになります。
-   プロパティの型が **Object** である場合、内部テキストは単一の **String** として解析されます。 介在する要素タグが存在する場合、XAML 解析エラーになります。これは、**Object** 型が単一のオブジェクト (**String** など) を前提としているためです。
-   プロパティの型がコレクションであり、内部テキストが連続していない場合、最初の部分文字列が **String** に変換され、コレクション項目として追加されます。介在する要素は、コレクション項目として追加されます。最後に終了の部分文字列 (ある場合) が 3 番目の **String** 項目としてコレクションに追加されます。

### <a name="whitespace-and-text-content-models"></a>空白とテキスト コンテンツのモデル

空白の保持は、実際には、考えられるすべてのコンテンツ モデルのサブセットに関してのみ関係するものです。 このサブセットは、特定の形式で単一の **String** 型を取ることができるコンテンツ モデルで構成されます。専用の **String** コレクション、**String** と一覧に記載されている他の型の混合、コレクション、または辞書で構成されます。

文字列をとることのできるコンテンツ モデルの場合でも、そのコンテンツ モデル内での既定の動作では、残っているすべての空白は、意味のある空白としては扱われません。

### <a name="preserving-whitespace"></a>空白の保持

最終的な表示に関して、ソース XAML 内の空白を保持するためのいくつかの手法は XAML プロセッサによる空白の正規化の影響を受けません。

`xml:space="preserve"`: この属性は、空白を保持する必要がある要素のレベルで指定します。 これを指定すると、見た目に直感的な入れ子としてマークアップ要素を配置するためにコード エディターまたはデザイン サーフェイスによって追加される場合があるスペースも含め、すべての空白が保持されることに注意してください。 これらのスペースのレンダリングは、包含要素のコンテンツ モデルの問題でもあります。 ルート レベルで `xml:space="preserve"` を指定することはお勧めしません。大半のオブジェクト モデルは、いずれにしても空白を重要なものと見なしていないためです。 この属性は、文字列内の空白を表示する必要のある要素のレベル、または空白が意味を持つコレクションである要素のレベルでのみ設定することをお勧めします。

エンティティと改行なしスペース: XAML は、テキスト オブジェクト モデル内への任意の Unicode エンティティの配置をサポートしています。 (UTF-8 エンコードでの) 改行なしスペースなど、専用のエンティティを使うことができます。 また、改行しないスペース文字をサポートするリッチ テキスト コントロールを使用することもできます。 インデントなどのレイアウト特性をシミュレートするのにエンティティを使っている場合は注意が必要です。その理由は、エンティティの実行時出力は、パネルや余白の適切な使用など、一般的なレイアウト機能よりも、数が多いほうの要因によって変わるためです。

