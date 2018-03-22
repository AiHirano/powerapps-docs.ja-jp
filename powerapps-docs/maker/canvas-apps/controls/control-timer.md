---
title: 'タイマー コントロール: リファレンス | Microsoft Docs'
description: 各種プロパティとサンプルを含むタイマー コントロールに関する情報
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
ms.openlocfilehash: 008c992ad3452c1844064335a51593c222fb1ac1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="timer-control-in-powerapps"></a>PowerApps のタイマー コントロール
一定の時間が経過した後のアプリの反応を決定できるコントロールです。

## <a name="description"></a>説明
タイマーは、たとえば、コントロールが表示される時間の長さを決定したり、一定の時間が経過した後にコントロールの他のプロパティを変更したりできます。

タイマーをデザイナーで実行するためには、アプリをプレビューする必要があることに注意してください。  これにより、ユーザーは時間制限がない状態で、デザイナーでタイマーを構成できます。

## <a name="key-properties"></a>主要なプロパティ
**Duration** - タイマーを実行する時間の長さを、ミリ秒単位で指定します。  最大値はありません。

**OnTimerEnd** – タイマーが実行を完了した場合のアプリの反応を指定します。

**Repeat** – タイマーが実行を完了したときに自動的に再開されるかどうかを指定します。

## <a name="additional-properties"></a>その他のプロパティ
**[Align](properties-text.md)** – コントロールの水平方向の中心に対するテキストの位置です。

**AutoPause** – ユーザーが別の画面に移動した場合、オーディオまたはビデオ クリップを自動的に一時停止するかどうかを指定します。

**AutoStart** – ユーザーがオーディオまたはビデオ コントロールを含む画面に移動したときに、自動的にクリップの再生を開始するかどうかを指定します。

**[BorderColor](properties-color-border.md)** – コントロールの境界線の色です。

**[BorderStyle](properties-color-border.md)** – コントロールの境界線を **Solid** (実線)、**Dashed** (破線)、**Dotted** (点線)、**None** (なし) のいずれに指定します。

**[BorderThickness](properties-color-border.md)** – コントロールの境界線の太さです。

**[Color](properties-color-border.md)** – コントロールのテキストの色です。

**[DisplayMode](properties-core.md)** – コントロールで、ユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、許可しないか (**Disabled**) を設定します。

**[DisabledBorderColor](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロールの境界線の色です。

**[DisabledColor](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロール内のテキストの色です。

**[DisabledFill](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロールの背景色です。

**[Fill](properties-color-border.md)** – コントロールの背景色です。

**[Font](properties-text.md)** – テキストを表記するフォントのファミリー名です。

**[FontWeight](properties-text.md)** – コントロール内のテキストの太さです。**Bold** (太字)、**Semibold** (中太)、**Normal** (標準)、**Lighter** (細字) から指定します。

**[Height](properties-size-location.md)** – コントロールの上端と下端の距離です。

**[HoverBorderColor](properties-color-border.md)** – コントロール上にユーザーがマウス ポインターを重ねているときのコントロールの境界線の色です。

**[HoverColor](properties-color-border.md)** – コントロールにユーザーがマウス ポインターを重ねているときのコントロール内のテキストの色です。

**[HoverFill](properties-color-border.md)** – コントロールにユーザーがマウス ポインターを重ねているときのコントロールの背景色です。

**[Italic](properties-text.md)** – コントロール内のテキストを斜体にするかどうかを指定します。

**[OnSelect](properties-core.md)** – ユーザーがコントロールをタップまたはクリックした場合のアプリの反応を指定します。

**OnTimerStart** – タイマーが実行を開始した場合のアプリの反応を指定します。

**[PressedBorderColor](properties-color-border.md)** – コントロールをユーザーがタップまたはクリックしたときのコントロールの境界線の色です。

**[PressedColor](properties-color-border.md)** – コントロールをユーザーがタップまたはクリックしたときのコントロール内のテキストの色です。

**[PressedFill](properties-color-border.md)** – コントロールをユーザーがタップまたはクリックしたときのコントロールの背景色です。

**[Reset](properties-core.md)** – コントロールを既定値に戻すかどうかを指定します。

**[Size](properties-text.md)** – コントロールに表示されるテキストのフォント サイズです。

**Start** – オーディオまたはビデオ クリップを再生するかどうかを指定します。

**[Strikethrough](properties-text.md)** – コントロールに表示されるテキストに取り消し線を付けるかどうかを指定します。

**[Text](properties-core.md)** – コントロールに表示されるテキスト、またはコントロールにユーザーが入力するテキストです。

**[Tooltip](properties-core.md)** – ポインターをコントロールに合わせたときに表示される説明テキストです。

**[Underline](properties-text.md)** – コントロールに表示されるテキストの下に線を引くかどうかを指定します。

**[Visible](properties-core.md)** – コントロールを表示するか非表示にするかを指定します。

**[Width](properties-size-location.md)** – コントロールの左端と右端の間の距離です。

**[X](properties-size-location.md)** – コントロールの左端とその親コンテナー (親コンテナーがない場合は画面) の左端間の距離です。

**[Y](properties-size-location.md)** – コントロールの上端とその親コンテナー (親コンテナーがない場合は画面) の上端間の距離です。

## <a name="related-functions"></a>関連する関数
[**Refresh**( *DataSource* )](../functions/function-refresh.md)

## <a name="examples"></a>例
### <a name="show-a-countdown"></a>カウントダウンの表示
1. タイマーを追加して **Countdown** という名前を付けます。

    [コントロールの追加、命名、構成についてはこちらをご覧ください](../add-configure-controls.md)。
2. タイマーの **Duration** プロパティを **10000** に、その **Repeat** および **Autostart** プロパティを **true** に設定します。
3. (オプション) **[Height](properties-size-location.md)** プロパティを **160** に、**[Width](properties-size-location.md)** プロパティを **600** に、**[Size](properties-text.md)** プロパティを **60** に設定して、タイマーを読み取りやすくします。
4. ラベルを追加し、その **[Text](properties-core.md)** プロパティを次の数式に設定します。
   <br>**"残りの秒数: " & RoundUp(10-Countdown.Value/1000, 0)**

    **[RoundUp](../functions/function-round.md)** 関数または[その他の関数](../formula-reference.md)については各関連記事を参照してください。

    ラベルには、タイマーが再開されるまでの秒数が表示されます。
5. (オプション) タイマーの **[Visible](properties-core.md)** プロパティを **false** に設定します。

### <a name="animate-a-control"></a>コントロールのアニメーション
1. タイマーを追加して **FadeIn** という名前を付けます。

    [コントロールの追加、命名、構成についてはこちらをご覧ください](../add-configure-controls.md)。
2. タイマーの **Duration** プロパティを **5000** に、その **Repeat** および **Autostart** プロパティを **true** に設定します。
3. (オプション) **[Height](properties-size-location.md)** プロパティを **160** に、**[Width](properties-size-location.md)** プロパティを **600** に、**[Size](properties-text.md)** プロパティを **60** に設定して、タイマーを読み取りやすくします。
4. ラベルを追加し、その **[Text](properties-core.md)** プロパティを設定して "**ようこそ!**" を表示し、 その **[Color](properties-color-border.md)** プロパティを次の数式に設定します。
   <br>**ColorFade(Color.BlueViolet, FadeIn.Value/5000)**

    **[ColorFade](../functions/function-colors.md)** 関数または[その他の関数](../formula-reference.md)については各関連記事を参照してください。

    ラベル内のテキストが白色にフェードした後、最大輝度に戻り、このプロセスが繰り返されます。
5. (オプション) タイマーの **[Visible](properties-core.md)** プロパティを **false** に設定します。
