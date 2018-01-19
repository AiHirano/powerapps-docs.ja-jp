---
title: "HashTags 関数 | Microsoft Docs"
description: "構文と例を含む PowerApps の HashTags 関数の参照情報"
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: b2f79c55724d9dc0bc9cfaf9e2e462c646cddb85
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2018
---
# <a name="hashtags-function-in-powerapps"></a>PowerApps の HashTags 関数
テキストの文字列からハッシュタグ (#文字列) を抽出します。

## <a name="description"></a>説明
**HashTags** 関数はハッシュタグの文字列をスキャンします。 ハッシュタグはシャープ記号 (#) で始まり、その後に次の組み合わせでできた文字列が続きます。

* 大文字と小文字
* 数字
* アンダースコア
* 通貨記号 ($ など)

**HashTags** は、文字列内のハッシュタグが含まれた 1 列の[テーブル](../working-with-tables.md)を返します。  文字列にハッシュタグがない場合、この関数は 1 列の[空](function-isblank-isempty.md)のテーブルを返します。

## <a name="syntax"></a>構文
**HashTags**( *String* )

* *String* - 必須。  ハッシュタグをスキャンする文字列。

## <a name="examples"></a>例
### <a name="step-by-step"></a>ステップ バイ ステップ
1. **[テキスト入力](../controls/control-text-input.md)**コントロールを追加し、**Tweet** という名前を付けて、そこに次の文を入力します。
   
    **This #app is #AMAZING and can #coUnt123 or #123abc but not #1-23 or #$\*(#@")**
2. 垂直カスタム ギャラリーを追加し、**[Items](../controls/properties-core.md)** プロパティを次の関数に設定します。
   
    **HashTags(Tweet.Text)**
3. ギャラリー テンプレートに**[ラベル](../controls/control-text-box.md)**を追加します。
   
    次のハッシュタグがギャラリーに表示されます。
   
   * **\#app**
   * **\#AMAZING**
   * **\#coUnt123**
   * **\#123abc**
   * **\#1**

