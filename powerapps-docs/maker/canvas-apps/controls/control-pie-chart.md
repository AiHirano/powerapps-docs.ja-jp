---
title: '円グラフ コントロール: リファレンス | Microsoft Docs'
description: 各種プロパティとサンプルを含む円グラフ コントロールに関する情報
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 1388eac45e5086f677cb83c8db9593fe01a9819f
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="pie-chart-control-in-powerapps"></a>PowerApps の円グラフ コントロール
互いに比較した相対値を表示するコントロールです。

## <a name="description"></a>説明
左端の列にラベルを、左から 2 番目の列に値を含むテーブルの相対的なデータを表示する場合は、**円グラフ** コントロールを追加します。

## <a name="key-properties"></a>主要なプロパティ
**[Items](properties-core.md)** – ギャラリー、リスト、グラフなどのコントロールに表示されるデータのソースです。

**ShowLabels** – 円グラフに、各ウェッジに関連付けられた値を表示するかどうかを指定します。

## <a name="additional-properties"></a>その他のプロパティ
**[BorderColor](properties-color-border.md)** – コントロールの境界線の色です。

**[BorderStyle](properties-color-border.md)** – コントロールの境界線を **Solid** (実線)、**Dashed** (破線)、**Dotted** (点線)、**None** (なし) のいずれに指定します。

**[BorderThickness](properties-color-border.md)** – コントロールの境界線の太さです。

**[Color](properties-color-border.md)** – コントロールのテキストの色です。

**[DisplayMode](properties-core.md)** – コントロールで、ユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、許可しないか (**Disabled**) を設定します。

**[DisabledBorderColor](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロールの境界線の色です。

**Explode** – 円グラフ内のウェッジ間の距離です。

**[Font](properties-text.md)** – テキストを表記するフォントのファミリー名です。

**[Height](properties-size-location.md)** – コントロールの上端と下端の距離です。

**[HoverBorderColor](properties-color-border.md)** – コントロール上にユーザーがマウス ポインターを重ねているときのコントロールの境界線の色です。

**ItemBorderColor** – 円グラフ内の各ウェッジの周りの境界線の色です。

**ItemBorderThickness** – 円グラフ内の各ウェッジの周りの境界線の太さです。

**ItemColorSet** – グラフ内の各データ ポイントの色です。

**LabelPosition** – ウェッジを基準とした、円グラフ内のラベルの場所です。

**[OnSelect](properties-core.md)** – ユーザーがコントロールをタップまたはクリックした場合のアプリの反応を指定します。

**[PressedBorderColor](properties-color-border.md)** – コントロールをユーザーがタップまたはクリックしたときのコントロールの境界線の色です。

**[Size](properties-text.md)** – コントロールに表示されるテキストのフォント サイズです。

**[Visible](properties-core.md)** – コントロールを表示するか非表示にするかを指定します。

**[Width](properties-size-location.md)** – コントロールの左端と右端の間の距離です。

**[X](properties-size-location.md)** – コントロールの左端とその親コンテナー (親コンテナーがない場合は画面) の左端間の距離です。

**[Y](properties-size-location.md)** – コントロールの上端とその親コンテナー (親コンテナーがない場合は画面) の上端間の距離です。

## <a name="related-functions"></a>関連する関数
[**Max**( *DataSource*, *ColumnName* )](../functions/function-aggregates.md)

## <a name="example"></a>例
1. **[[ボタン]](control-button.md)** コントロールを追加し、**[OnSelect](properties-core.md)** プロパティに次の式を設定します。<br>
   **Collect(Revenue2015, {Product:"Europa", Revenue:27000}, {Product:"Ganymede", Revenue:26300}, {Product:"Callisto", Revenue:29200})**
   
    [コントロールの追加および構成](../add-configure-controls.md)についてはこちらをご覧ください。
   
    **[Collect](../functions/function-clear-collect-clearcollect.md)** 関数または[その他の関数](../formula-reference.md)については各関連記事を参照してください。
2. F5 キーを押して、**[ボタン](control-button.md)** コントロールをクリックまたはタップしてから、Esc キーを押して既定のワークスペースに戻ります。
3. **円グラフ** コントロールを追加し、その **[Items](properties-core.md)** プロパティを **Revenue2015** に設定します。
   
    **円グラフ** コントロールには、他の製品に関連した製品ごとの収益データが表示されます。

