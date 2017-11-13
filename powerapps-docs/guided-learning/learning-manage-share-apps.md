---
title: "アプリの共有 | Microsoft Docs"
description: "同僚や他のユーザーとアプリを共有します"
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: _nUU7oOy4oU
courseduration: 5m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: 67ed022be0cc4b1fc7d2d6acf7518c3526a54156
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="share-your-apps"></a>アプリの共有
独自のビジネス ニーズに対応するアプリを構築することは素晴らしいのですが、PowerApps の真価は構築したアプリを他のユーザーと共有できることで発揮されます。 アプリを構築する方法を理解したところで、このトピックでは、共有する方法を学習しましょう。 アプリは、特定のユーザーまたはグループと共有することも、組織全体で共有することもできます。 他のユーザーとアプリを共有すると、他のユーザーがアプリをブラウザーで Dynamics 365 から実行したり、PowerApps Mobile for Windows、iOS、Android で実行したりできるようになります。 他のユーザーに共同作成者権限を付与すると、付与されたユーザーはアプリを更新することもできます。

## <a name="prepare-to-share-an-app"></a>アプリを共有するための準備をする
他のユーザーとアプリを共有する前に、アプリをクラウドに保存する必要があります。 アプリにわかりやすい名前と説明を付けて、他のユーザーにアプリの目的をわかりやすくし、リストから容易に選択してもらえるようにします。 PowerApps Studio で **[File]** (ファイル) をクリックまたはタップして、説明を入力します。

![アプリの説明](./media/learning-manage-share-apps/app-description.png)

共有アプリに加えたあらゆる変更は、変更を保存するとすぐに、それを共有している他のユーザーに伝えられることに注意してください。 これはアプリを改善した場合は素晴らしいのですが、機能を削除したり大幅に変更したりした場合は他のユーザーに影響を与える可能性もあります。

## <a name="share-an-app"></a>アプリを共有する
web.powerapps.com のアプリのタイル上の省略記号 (. . .) をクリックして、**[Share]** (共有) をクリックします。

![web powerapps.com からアプリを共有する](./media/learning-manage-share-apps/share-app.png)

ここで、アプリを共有し、アプリのバージョンを管理できます。バージョン管理については、次のトピックで説明します。 アプリを共有するユーザーとグループ、それぞれに与える役割 (**ユーザー**または**共同作成者**) を指定します。 **[Save]** (保存) をクリックまたはタップします。

![ユーザーとグループを選択する](./media/learning-manage-share-apps/select-users.png)

メールでユーザーに通知すると、アプリを共有するすべてのユーザーに Dynamics 365 へのリンクを含むメールが送信されます。 アプリの共同作成者には、web.powerapps.com へのリンクも送信されます。Dynamics 365 へのリンクにアクセスしないユーザーには、アプリは表示されません。 アプリは AppSource にありますが、ユーザーが自分で Dynamics 365 に追加する必要があります。

![Dynamics 365 のアプリ](./media/learning-manage-share-apps/dynamics-365.png)

## <a name="permissions-and-licensing"></a>アクセス許可とライセンス
ここではアクセス許可とライセンスを詳しく説明することはしませんが、共有に関連する基本事項をいくつか説明します。

* ユーザーと共同作成者には、共有アプリが使用するすべてのデータ接続とゲートウェイへのアクセス許可が必要です。 一部のアクセス許可は暗黙的にアプリに付いていますが、それ以外のアクセス許可は明示的に付与する必要があります。
* アプリが Common Data Service のエンティティを使用している場合は、ユーザーと共同作成者は Common Data Service データベースへのアクセス権が必要です。 共同作成者は、エンティティを直接操作する場合、PowerApps の "P2" ライセンスも必要です。

アプリの共有は簡単で、役に立つと思うアプリを組織内のユーザーに利用可能にするための優れた方法です。 次のトピックでは、アプリを使用し共有しているときに、どのアプリのバージョンがアクティブになるかを制御する方法を説明します。

