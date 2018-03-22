---
title: 'HTML テキスト コントロール: リファレンス | Microsoft Docs'
description: 各種プロパティとサンプルを含む HTML テキスト コントロールに関する情報
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
ms.openlocfilehash: bb652f3ba6decad7cb6f93007eaec6340f230ca1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="html-text-control-in-powerapps"></a>PowerApps の HTML テキスト コントロール
テキストを表示し、書式設定のための HTML タグを変換するボックスです。

## <a name="description"></a>説明
**HTML テキスト** コントロールは、プレーンテキストや数値を表示するだけでなく、HTML タグ (改行なしスペースなど) の変換も行います。

## <a name="key-properties"></a>主要なプロパティ
**[Color](properties-color-border.md)** – コントロールのテキストの色です。

**[Font](properties-text.md)** – テキストを表記するフォントのファミリー名です。

**HTMLText** – HTML テキスト コントロールに表示される、HTML タグを含む可能性のあるテキストです。

## <a name="additional-properties"></a>その他のプロパティ
**[BorderColor](properties-color-border.md)** – コントロールの境界線の色です。

**[BorderStyle](properties-color-border.md)** – コントロールの境界線を **Solid** (実線)、**Dashed** (破線)、**Dotted** (点線)、**None** (なし) のいずれに指定します。

**[BorderThickness](properties-color-border.md)** – コントロールの境界線の太さです。

**[DisplayMode](properties-core.md)** – コントロールで、ユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、許可しないか (**Disabled**) を設定します。

**[DisabledBorderColor](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロールの境界線の色です。

**[DisabledFill](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロールの背景色です。

**[Fill](properties-color-border.md)** – コントロールの背景色です。

**[Height](properties-size-location.md)** – コントロールの上端と下端の距離です。

**[HoverBorderColor](properties-color-border.md)** – コントロール上にユーザーがマウス ポインターを重ねているときのコントロールの境界線の色です。

**[OnSelect](properties-core.md)** – ユーザーがコントロールをタップまたはクリックした場合のアプリの反応を指定します。

**[PaddingBottom](properties-size-location.md)** – コントロール内のテキストとそのコントロールの下端間の距離です。

**[PaddingLeft](properties-size-location.md)** – コントロール内のテキストとそのコントロールの左端間の距離です。

**[PaddingRight](properties-size-location.md)** – コントロール内のテキストとそのコントロールの右端間の距離です。

**[PaddingTop](properties-size-location.md)** – コントロール内のテキストとそのコントロールの上端間の距離です。

**[Size](properties-text.md)** – コントロールに表示されるテキストのフォント サイズです。

**[Tooltip](properties-core.md)** – ポインターをコントロールに合わせたときに表示される説明テキストです。

**[Visible](properties-core.md)** – コントロールを表示するか非表示にするかを指定します。

**[Width](properties-size-location.md)** – コントロールの左端と右端の間の距離です。

**[X](properties-size-location.md)** – コントロールの左端とその親コンテナー (親コンテナーがない場合は画面) の左端間の距離です。

**[Y](properties-size-location.md)** – コントロールの上端とその親コンテナー (親コンテナーがない場合は画面) の上端間の距離です。

## <a name="related-functions"></a>関連する関数
[**Find**( *FindString*, *WithinString* )](../functions/function-find.md)

## <a name="example"></a>例
1. **[ラベル](control-text-box.md)** コントロールを追加して **Source** という名前を付け、その **[Text](properties-core.md)** プロパティを次の文字列に設定します。

\<p> 私たちは、非常に \&nbsp; \&quot; 深い \&quot; グローバリゼーションおよびローカライズを行いました。 \<p>

[コントロールの追加、命名、構成についてはこちらをご覧ください](../add-configure-controls.md)。

1. **HTML テキスト** コントロールを追加し、その **HTMLText** プロパティを次の値に設定します。<br>
   **Source.Text**
   
     **HTML テキスト** コントロールは**[ラベル](control-text-box.md)** コントロールと同じテキストを表示しますが、タグを適切な文字に変換します。

