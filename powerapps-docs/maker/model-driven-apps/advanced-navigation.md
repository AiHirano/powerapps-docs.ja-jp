---
title: PowerApps でアプリ、ソリューション エクスプローラー、設定にナビゲートする | Microsoft Docs
description: PowerApps で高度なアプリの作成とカスタマイズ領域を特定する方法を説明します
keywords: null
author: Mattp123
ms.author: matp
manager: kvivek
ms.custom: ''
ms.date: 10/30/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 60281cab-23d5-4421-ae51-f7e6c1176729
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="navigate-to-advanced-model-driven-app-making-and-customization-areas"></a>高度なモデル駆動型アプリの作成とカスタマイズ領域にナビゲートする

このトピックでは、PowerApps 環境内で使用された高度なカスタマイズおよび管理領域にアクセスする方法について説明します。

## <a name="solutions"></a>ソリューション 
ソリューション領域は、アンマネージド ソリューションの表示、編集、作成、インポート、エクスポート、および削除する場所です。 

1.  [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。
2.  左のナビゲーション ウィンドウで、**ソリューション** を選択します。 

## <a name="solution-explorer"></a>ソリューション エクスプローラー
PowerApps ホーム ページから完了できないアプリの作成およびカスタマイズ タスクを実行するには、ソリューション エクスプローラーを使用します。

1.  [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。 
2.  左のナビゲーション ウィンドウで、**ソリューション** を選択します。  
3.  ツール バーで**クラシックに切り替え**を選択して、ソリューション エクスプローラーを開きます。 

    リストでソリューションを選択する場合、**クラシックに切り替え**コマンドは使用できないことに注意してください。

## <a name="apps"></a>アプリ
アプリ領域では、環境内で特権のあるすべてのモデル駆動型およびキャンバスがリストされます。 アプリの起動に加えて、アプリ領域からセキュリティ ロールを割り当てることもできます。 

アプリを共有するには:
1.  [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。

2.  **アプリ**を選択します。
 
3.  **…** を選択します > **共有**:  

    > [!div class="mx-imgBorder"] 
    > ![アプリ リンクの共有](media/share-link.png) 

4. 次に、「[アプリにセキュリティ ロールを追加する](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app#add-security-roles-to-the-app)」を参照してください
 
## <a name="settings"></a>設定
環境設定の構成、プロセスのアクティブ化または非アクティブ化などを行うには、設定領域を使用します。 

まず、必要な設定が ![[設定] アイコン](media/powerapps-gear.png)  > **高度なカスタマイズ** メニューにあるかどうかを確認します。

**高度なカスタマイズ**から使用可能な設定を見つけるには:  
1.  Dynamics 365 Administration Center から環境にアクセスします。 北米にある環境の場合、[https://port.crm.dynamics.com/G/instances/InstancePicker.aspx](https://port.crm.dynamics.com/G/instances/InstancePicker.aspx) にアクセスします。 他の場所については、Dynamics 365 Administration Center に直接サインインします。
2.  対象の環境を選択し、**開く** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![環境のオープン](media/open-environment.png)

## <a name="see-also"></a>関連項目
[アプリ デザイナーを使用してモデル駆動型アプリを作成または編集](create-edit-app.md)
[Web 用 PowerApps Studio でアプリを作成または編集](../canvas-apps/create-app-browser.md)
