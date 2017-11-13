---
title: "スクロール画面を追加する | Microsoft Docs"
description: "スクロール可能な画面を作成します。スクロールすると、画面に一度に表示できるより多くのコンテンツが表示されます。"
services: 
suite: powerapps
documentationcenter: na
author: lonu
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: lonu
ms.openlocfilehash: 8441ac93c1d3f96e0316ff1f044dc58b800d4dd5
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="add-a-scrolling-screen-in-powerapps"></a>PowerApps でスクロール画面を追加する
スクロールするとさまざまな項目が表示される画面を作成します。 たとえば、縦棒グラフや折れ線グラフにデータを表示するアプリを作成するとします。 スクロール画面を追加すると、スクロールしたときに表示されるように複数のコントロールを追加できます。

1 つのセクションに複数のコントロールを追加すると、それがスマートフォン アプリであるか、タブレット アプリであるかに関係なく、そのセクション内でコントロールの相対位置が維持されます。 画面のサイズと方向によりセクションの配置が決まることがあります。  

&nbsp;

[!INCLUDE [app-customization-requirements](includes/app-customization-requirements.md)]

## <a name="create-a-scrolling-screen"></a>スクロール画面を作成する
1. **[ホーム]** タブで、**[新しい画面]** をクリックまたはタップします。
   
    ![アプリに画面を追加するオプション][1]
2. **[ホーム]** タブで **[レイアウト]** をクリックまたはタップし、無限スクロールのキャンバスを追加するオプションをクリックまたはタップします。  
   
    ![無限スクロールのキャンバスを追加するオプション][2]
   
    キャンバスが追加されます。  
   
    ![無限スクロールのキャンバスが追加された画面 (既定)][3]

## <a name="add-elements"></a>要素を追加する
それでは、キャンバスにコントロールをいくつか追加し、スクロール画面の動作を確認しましょう。

1. 追加したキャンバスで、**[[挿入] タブから項目を追加]** をクリックまたはタップします。
   
    ![][4]
2. **[挿入]** タブの **[グラフ]** をクリックまたはタップし、**[縦棒グラフ]** をクリックまたはタップします。
   
    ![縦棒グラフを追加するオプション][5]
   
    画面の最初のカードに縦棒グラフが表示されます。  
   
    ![既定の縦棒グラフ][7]
3. **[挿入]** タブの **[テキスト]** をクリックまたはタップし、**[ペン入力]** をクリックまたはタップします。  
   
    ![ペン コントロールを追加するオプション][8]
4. グラフの下にペン コントロールを移動し、ペン コントロールのサイズを変更してカードの下部を対象として含めます。  
   
    ![ペン コントロールを移動し、サイズを変更する][9]

## <a name="add-a-section"></a>セクションを追加する
それでは、別のコントロールで別のカードを追加してみましょう。

1. 画面の下部の近くにある **[セクションの追加]** をクリックまたはタップします。  
   
    ![セクションを追加するオプション][10]
   
    新しいカードが画面に追加されます。  
   
    ![既定のセクションの下の新しいカード][11]
2. カードが選択されている状態のまま、**[挿入]** タブに移動し、**[グラフ]** をクリックまたはタップし、**[折れ線グラフ]** をクリックまたはタップします。
   
    新しいグラフが大きすぎて他のコントロールがある画面に表示されません。  
   
    ![新しいカードの下部に追加された折れ線グラフ][12]
3. F5 キーを押して (または右上隅の再生アイコンをクリックまたはタップして) プレビュー モードを開始します。
   
    ![プレビュー モードを開始](./media/add-scrolling-screen/open-preview.png)
4. 下にスクロールし、新しい折れ線グラフを表示します。  
   
    ![プレビューに折れ線グラフが表示されます][13]

[1]: ./media/add-scrolling-screen/add-screen.png
[2]: ./media/add-scrolling-screen/add-canvas.png
[3]: ./media/add-scrolling-screen/default-canvas.png
[4]: ./media/add-scrolling-screen/insert-visual.png
[5]: ./media/add-scrolling-screen/add-chart.png
[7]: ./media/add-scrolling-screen/default-chart.png
[8]: ./media/add-scrolling-screen/add-pen.png
[9]: ./media/add-scrolling-screen/move-resize-pen.png
[10]: ./media/add-scrolling-screen/add-section.png
[11]: ./media/add-scrolling-screen/new-card.png
[12]: ./media/add-scrolling-screen/add-line-chart.png
[13]: ./media/add-scrolling-screen/line-chart-preview.png
