---
title: "環境の概要 | Microsoft Docs"
description: "環境とその使用方法"
services: 
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/01/2016
ms.author: jamesol
ms.openlocfilehash: 425376f218b01a9edab4dae90555b33cd1d26a80
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="environments-overview"></a>環境の概要
環境は、PowerApps の新しい概念です。 簡単に言うと、環境は組織のビジネス データ、アプリ、およびフローを格納、管理、および共有するスペースです。 ロール、セキュリティ要件または対象ユーザーが異なるアプリを分離するコンテナーとしても機能します。 環境を活用する方法は、組織や構築するアプリによって変わります。 例:

1. 単一の環境でのみアプリを構築することもできます。
2. アプリのテスト バージョンと製品バージョンをグループ化する個別の環境を作成できます。
3. 会社の特定のチームや部門に対応する個別の環境を作成し、それぞれのユーザーに関連するデータとアプリを、それぞれの環境に配置できます。
4. 会社のグローバルに展開する支店ごとに、個別の環境を作成することもできます。  

## <a name="environment-scope"></a>環境のスコープ
それぞれの環境は Azure AD テナントに作成され、そのリソースには、そのテナント内のユーザーのみがアクセスできます。 環境は、米国などの地理的な場所にも結び付けられています。 環境でアプリを作成すると、アプリはその地理的な場所にあるデータセンターにのみルーティングされます。 その環境で作成するすべての項目 (接続、ゲートウェイ、Microsoft Flow を使用するフローなど) は、それぞれの環境の場所にも結び付けられます。

それぞれの環境には、アプリのストレージを提供する Common Data Service データベースを配置できる場合と、1 つ配置できる場合があります。 環境にデータベースを作成できるかどうかは、購入する PowerApps のライセンスとその環境内のアクセス許可によります。 詳細については、[料金の情報](pricing-billing-skus.md)に関するページを参照してください。

アプリを環境に作成する場合、そのアプリは、接続、ゲートウェイ、フロー、Common Data Service データベースなど、同じ環境にもデプロイされているデータ ソースへの接続のみ許可されます。  たとえば、'Test' および 'Dev' という名前の 2 つの環境を作成し、それぞれの環境に Common Data Service データベースを作成したシナリオについて考えてみましょう。 'Test' 環境でアプリを作成する場合は、そのアプリは 'Test' データベースへの接続のみ許可され、'Dev' データベースに接続することはできません。

環境間でリソースを移動するプロセスもあります。 詳細については、[リソースの移行](environment-and-tenant-migration.md)に関するページを参照してください。

![](./media/environments-overview/Environments.png)

## <a name="environment-permissions"></a>環境のアクセス許可
環境には、環境内でのアクセス許可を提供する 2 つの組み込みの役割があります。

* Environment Admin ロールは、環境に対して、次を含むすべての管理操作を実行できます。
  
  o   環境管理者ロールまたは環境作成者ロールのいずれかからユーザーまたはグループを追加または削除する
  
  o   環境に Common Data Service データベースをプロビジョニングする
  
  o   環境内で作成されたすべてのリソースを表示し、管理する
  
  o   データ損失防止ポリシーを設定する 詳細については、[データ損失防止ポリシー](prevent-data-loss.md)に関するページを参照してください。
* Environment Maker ロールは、アプリ、接続、カスタム コネクタ、ゲートウェイ、および Microsoft Flow を使用するフローなど、環境内のリソースを作成できます。

Environment Maker は、組織内の個々のユーザー、セキュリティ グループ、またはすべてのユーザーとアプリを共有することにより、環境に構築するアプリを組織の他のユーザーに配布することもできます。 詳細については、[PowerApps でのアプリの共有](share-app.md)に関するページを参照してください。

これらの環境のロールに割り当てられているユーザーまたはグループには、環境のデータベース (存在する場合) へのアクセス権が自動的に付与されるわけではありません。データベース所有者が個別にアクセス権を付与する必要があります。 詳細については、「[Configure database security (データベース セキュリティの構成)](database-security.md)」を参照してください。

環境管理者は、[PowerApps 管理センター][1]から、ユーザーまたはセキュリティ グループに、これらの 2 つのロールのいずれかを割り当てることができます。 詳細については、「[Environment Administration (環境の管理)](environments-administration.md)」を参照してください。

![](./media/environments-overview/EnvironmentRoles.png)

## <a name="the-default-environment"></a>既定の環境
既定の環境は、PowerApps によって各テナントに対して自動的に 1 つ作成され、そのテナント内のすべてのユーザーが共有します。 新しいユーザーは、PowerApps にサインアップすると、既定の環境の Maker ロールに自動的に追加されます。 既定の環境は、AAD テナントの既定のリージョンに最も近いリージョンに作成されます。

> [!NOTE]
> 既定の環境の Environment Admin ロールに自動的に追加されるユーザーはいません。 詳細については、「[Environment Administration (環境の管理)](environments-administration.md)」を参照してください。
> 
> 

既定の環境の名前は、"{Azure AD テナント名} (既定)" となります。

![](./media/environments-overview/DefaultEnvironment.png)

## <a name="choosing-an-environment"></a>環境の選択
環境の導入に伴い、[https://web.powerapps.com](https://web.powerapps.com) では、新しいエクスペリエンスを実現しています。このサイトに表示されるアプリ、接続、およびその他の項目は、選択している現在の環境に基づいて、フィルターされるようになりました。  現在の環境は、ヘッダーの右端近くにある環境選択リストで指定します。 別の環境を選択するには、選択リストをクリックまたはタップして、使用可能な環境のリストを表示します。 使用する環境をクリックまたはタップします。

次の条件のいずれかを満たしている場合、環境が選択リストに表示されます。

1. 環境の Environment Admin ロールのメンバーである。
2. 環境の Environment Maker ロールのメンバーである。
3. 環境の Environment Admin または Environment Maker ではないが、環境内で少なくとも 1 つのアプリに対する '共同作業者’ アクセスが付与されている。 詳細については、「[share an app (アプリの共有)](share-app.md)」を参照してください。 **注**: この場合は、この環境にアプリを作成できません。 自分と共有している既存のアプリの変更だけが可能です。

![](./media/environments-overview/EnvironmentPicker.png)

## <a name="creating-an-environment"></a>環境の作成
### <a name="who-can-create-environments"></a>環境を作成できるユーザー
環境を作成できるかどうかは、ライセンスによって決まります。

| ライセンス | 環境の作成が可能 |
| --- | --- |
| PowerApps P2 |○ |
| PowerApps P2 試用版 |○ |
| PowerApps P1 |x |
| PowerApps P1 試用版 |x |
| Dynamics 365 プラン |x |
| Office 365 プラン |x |
| Dynamics 365 アプリおよびチーム プラン |x |

各ユーザーは、最大で 2 つの環境を作成できます。

### <a name="where-can-environments-be-created"></a>環境を作成できる場所
新しい環境は、[PowerApps.com][2] および [PowerApps 管理センター][1]で作成できます。 環境を作成すると、作成者はその環境の Environment Admin ロールに自動的に登録されます。 Environment Admin ロールまたは Environment Maker ロールのメンバーとして参加できる環境の数に制限はありません。 詳細については、「[Environment Administration (環境の管理)](environments-administration.md)」を参照してください。

![](./media/environments-overview/CreateEnvironmentDialog.png)

## <a name="what-will-change-for-powerapps-preview-users"></a>PowerApps プレビュー版のユーザーに対する変更点
PowerApps プレビュー版に参加しているすべてのユーザーに対して、環境の導入に伴いエクスペリエンスにおいていくつかの変更があります。  次の表は、米国および米国以外のユーザーに対する変更点を示します。

| User | 変更点 |
| --- | --- |
| Common Data Service データベースを作成したプレビュー版ユーザー |このユーザーには "{ユーザー名} の環境" と呼ばれる環境が表示され、プレビュー版の Common Data Service データベースとそれに対して構築したすべてのアプリが含まれています。  このユーザーは、この環境の Environment Maker ロールと Environment Admin ロールに追加されます。また、このデータベースのデータベース所有者として追加されます。 PowerApps が一般公開されると、Common Data Service のメタデータはアップグレードされます。 この変更によって次の影響があります。プレビュー版の Common Data Service データベースに対して構築済みのエンティティとアプリは引き続き使用できます。ただし、そのデータベース内にフィールドまたはエンティティを作成することはできなくなります。 アップグレードしたメタデータを格納したデータベースを含む環境を作成して、その環境にアプリを移行する方法については、近くガイダンスを公開する予定です。<br>**注**: プレビュー版の Common Data Service に対して構築したアプリが、データ ソースとしてカスタム コネクタも活用している場合、アプリはこの環境では一時的に機能しなくなります。これは、すべてのカスタム コネクタが既定の環境に移行されるためです。 影響を受けたアプリを修復するには、この環境でカスタム コネクタを再作成する必要があります。 |
| 米国のプレビュー版ユーザー |PowerApps プレビュー期間中に作成した次のリソースは、テナントの既定の環境で利用可能になります。<br>- 作成したすべてのアプリ (プレビュー版の Common Data Service データベースに接続されるアプリを除く)<br>- 作成したすべての接続およびカスタム コネクタ<br>- インストールしたすべてのオンプレミス データ ゲートウェイ |
| 米国以外のプレビュー版ユーザー |既定の環境に加え、"{Azure AD テナント} (プレビュー版から)" と呼ばれる環境も表示され、PowerApps プレビュー期間中に作成した次のリソースが格納されています。<br>- 作成したすべてのアプリ (プレビュー版の Common Data Service データベースに接続されるアプリを除く)<br>- 作成したすべての接続およびカスタム コネクタ<br>- インストールしたすべてのオンプレミス データ ゲートウェイ<br>このユーザーは、この環境の Environment Maker ロールに追加されます。 |

*プレビュー版ユーザー* とは、一般公開 (GA) としてリリースされる前に Microsoft PowerApps を使用したユーザーです。

PowerApps が一般公開 (GA) されてから 2 週間後に、プレビュー版のコンテンツが含まれている環境は、読み取り専用としてマークされます (既定の環境を除く)。既存のすべてのアプリとフローは引き続きこれらの環境で動作しますが、アプリまたはフローを作成することはできなくなります。 これらの環境のユーザーは既定の環境または別のカスタム環境にコンテンツを移行することを強くお勧めします。 移行プロセスの詳細については、次のブログ (今週、投稿予定) を参照してください: [Common Data Service サービス機能の発表に関するブログ][3]。

### <a name="example-environments-for-a-preview-user-in-us"></a>米国のプレビュー版ユーザーの環境の例
![](./media/environments-overview/USuser1.png)

### <a name="example-environments-for-a-preview-user-not-in-us"></a>米国以外のプレビュー版ユーザーの環境の例
![](./media/environments-overview/non-USuser1.png)

## <a name="managing-environments-for-your-organization"></a>組織の環境の管理
環境の導入に伴い、PowerApps 管理センターも運用を開始しました。PowerApps 管理センターでは、ユーザーが作成した環境、またはユーザーが Environment Admin ロールに追加された環境をすべて管理できます。 管理センターでは、環境に対して、次を含むすべての管理操作を実行できます。

* Environment Admin ロールまたは Environment Maker ロールのいずれかからユーザーまたはグループを追加または削除する。  詳細については、「[Environment Administration (環境の管理)](environments-administration.md)」を参照してください。
* 環境に Common Data Service データベースをプロビジョニングする。 詳細については、「[Create a Common Data Service database (Common Data Service サービスの作成)](create-database.md)」を参照してください。
* データ損失防止ポリシーを設定する。 詳細については、[データ損失防止ポリシー](prevent-data-loss.md)に関するページを参照してください。
* データベースのセキュリティ ポリシーを設定する (オープン ポリシーまたは制限付きポリシー)。 詳細については、「[Configure database security (データベース セキュリティの構成)](database-security.md)」を参照してください。
* Azure AD テナントのグローバル管理者ロールのメンバー (Office 365 のグローバル管理者を含む) も、PowerApps 管理センターで、テナントに作成したすべての環境を管理し、テナント全体のポリシーを設定できます。

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://aka.ms/cdspreviewtoga
