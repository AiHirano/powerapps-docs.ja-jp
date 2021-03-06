---
title: 環境を作成する | Microsoft Docs
description: このクイック スタートでは、環境を作成する方法について説明します
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 08/29/2018
ms.author: jimholtz
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 9d7a2093c938658d6717157fc6bd683aa3a55bb6
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297476"
---
# <a name="create-an-environment"></a>環境の作成
環境とは、組織のビジネス データ、アプリ、フローを保管、管理、共有するためのスペースです。 環境は、ロール、セキュリティ要件または対象ユーザーが異なるアプリを分離するコンテナーとしても機能します。 PowerApps では、テナントごとに 1 つの既定の環境が自動的に作成されます。この環境は、そのテナント内のすべてのユーザーで共有されます。

それぞれの環境には、アプリのストレージを提供する Common Data Service データベースを配置できる場合と、1 つ配置できる場合があります。 ユーザーが環境内にアプリを作成すると、そのアプリは、接続、ゲートウェイ、フローなどのすべてのデータ ソースに接続できます。 ただし、同じ環境内の Common Data Service データベースに接続することのみがアプリに許可されます。 環境を活用する方法は、組織や構築するアプリによって変わります。 詳細については、[環境の概要](environments-overview.md)を参照してください。

このトピックでは、環境とその環境のデータベースを作成する方法について説明します。

## <a name="prerequisites"></a>前提条件
 このトピックを実行するには、次の項目が必要です。
 * PowerApps プラン 2 または Microsoft Flow プラン 2 のライセンス。 また、[PowerApps プラン 2 無料試用版](https://web.powerapps.com/signup?redirect=marketing&email=)にサインアップすることもできます。
 * PowerApps 環境管理者、Office 365 グローバル管理者、または Azure Active Directory テナント管理者のアクセス許可。 詳細については、[PowerApps の環境の管理](environments-administration.md)に関するページを参照してください。

## <a name="sign-in-to-the-powerapps-admin-center"></a>PowerApps 管理センターにサインインする
[https://admin.powerapps.com](https://admin.powerapps.com) で管理センターにサインインします。

## <a name="create-an-environment-and-database"></a>環境とデータベースの作成
1. ナビゲーション ウィンドウで、**[環境]**、**[新しい環境]** の順にクリックまたはタップします。

    ![ファイルと共有](./media/create-environment/new-environment.png)
2. **[新しい環境]** ダイアログ ボックスで環境の名前を入力し、ドロップダウン リストからリージョンと環境の種類を選択します。 リージョンの既定は Azure Active Directory テナントのホーム リージョンですが、ドロップダウン リストから任意のリージョンを選択できます。 環境の作成後にリージョンを変更することはできません。 完了したら、**[環境の作成]** をクリックまたはタップします。

    ![ファイルと共有](./media/create-environment/new-environment-dialog.png)

    **[プレビュー (米国)]** を選択すると、今後公開される予定の PowerApps 機能をいち早く体験できます。 PowerApps プレビュー プログラムの詳細は[こちら](preview-environments.md)でご覧ください。
3. 環境が作成されると、ダイアログ ボックスに確認メッセージが表示され、データベースの作成が求められます。 **[データベースの作成]** をクリックまたはタップし、Common Data Service へのアクセスを有効にします。

    **注:** この時点では、Azure Active Directory テナントのホーム リージョンにのみデータベースを作成できます。

    ![ファイルと共有](./media/create-environment/create-database-dialog.png)
4. データベースの格納データの通貨と言語を選択します。 データベースの作成後に通貨や言語を変更することはできません。 完了したら、**[データベースの作成]** をクリックまたはタップします。

    ![ファイルと共有](./media/create-environment/create-database-dialog2.png)

    Common Data Service にデータベースが作成されるまでに数分かかることがあります。 データベースが作成されると、新しい環境が **[環境]** ページの環境の一覧に表示されます。

    ![ファイルと共有](./media/create-environment/new-environment-created.png)

    環境の詳細を表示するには、環境をクリックまたはタップします。

## <a name="next-steps"></a>次の手順
このトピックでは、環境とその環境のデータベースを作成する方法について説明します。 次は、組織内の環境を管理する方法について説明します。

> [!div class="nextstepaction"]
> [PowerApps での環境の管理](environments-administration.md)
