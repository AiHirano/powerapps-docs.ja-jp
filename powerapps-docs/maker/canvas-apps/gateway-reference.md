---
title: オンプレミス データ ゲートウェイについて | Microsoft Docs
description: オンプレミス データ ゲートウェイのインストールやトラブルシューティングを含む参照情報
services: ''
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/20/2017
ms.author: sharik
ms.openlocfilehash: 1b17c7007ad87fa2a1801473a977fd8ec94ffdea
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="understand-on-premises-data-gateways-for-microsoft-powerapps"></a>Microsoft PowerApps のオンプレミス データ ゲートウェイについて
## <a name="installation-and-configuration"></a>インストールと構成
**前提条件**

最小:

* .NET 4.5 Framework
* 64 ビット バージョンの Windows 7 または Windows Server 2008 R2 (またはそれ以降)

推奨:

* 8 コア CPU
* 8 GB のメモリ
* 64 ビット バージョンの Windows 2012 R2 (またはそれ以降)

関連する考慮事項:

* ゲートウェイをドメイン コントローラーにインストールすることはできません。
* ゲートウェイは、電源オフ、スリープ状態、インターネット未接続状態になる可能性があるコンピューター (ノート PC など) にインストールしないでください。このような状況では、ゲートウェイは動作できません。 さらに、ワイヤレス ネットワーク経由ではゲートウェイのパフォーマンスが低下する可能性があります。

**ゲートウェイのインストール**

1. [インストーラーをダウンロード](http://go.microsoft.com/fwlink/?LinkID=820931)し、実行します。

    ![インストーラーの実行](./media/gateway-reference/run-installer.png)

2. インストール ウィザードの最初の画面で、ノート PC へのゲートウェイのインストールに関する注意事項を確認の上、**[次へ]** をクリックまたはタップします。

    ![確認画面](./media/gateway-reference/laptop-reminder.png)

3. ゲートウェイをインストールする場所を指定し、使用条件とプライバシーに関する声明に同意するチェック ボックスをオンにして、**[インストール]** をクリックまたはタップします。

4. **[ユーザー アカウント制御]**ダイアログ ボックスで、**[はい]** をクリックまたはタップして続行します。

5. ウィザードの次の画面で、**[サインイン]** をクリックまたはタップします。

    ![サインイン](./media/gateway-reference/sign-in.png)

6. 新しいゲートウェイを登録するか、それとも既存のゲートウェイを移行、復元、置き換えるかを選ぶオプションをクリックまたはタップし、**[次へ]** をクリックまたはタップします。

    ![新規または既存の選択](./media/gateway-reference/new-existing.png)

   * ゲートウェイを構成するには、その**名前**と**回復キー**を入力し、**[構成]** をクリックまたはタップしてから、**[閉じる]** をクリックまたはタップします。

       ![新しいゲートウェイの構成](./media/gateway-reference/configure-new.png)

       8 文字以上の回復キーを指定し、安全な場所に保存しておきます。 このキーは、ゲートウェイを移行、復元、置き換える場合に必要になります。

   * 既存のゲートウェイを移行、復元、置き換えるには、ゲートウェイの名前と回復キーを指定し、**[構成]** をクリックまたはタップして、追加の指示に従います。

       ![既存のゲートウェイの回復](./media/gateway-reference/recover-existing.png)

**ゲートウェイの再起動**

このゲートウェイは Windows サービスとして実行されるため、複数の方法で開始および停止できます。 たとえば、ゲートウェイが実行されているマシンに対する管理者特権のアクセス許可を使用してコマンド プロンプトを開き、次のコマンドのいずれかを実行できます。

* サービスを停止するには、次のコマンドを実行します。<br>
  **net stop PBIEgwService**

* サービスを開始するには、次のコマンドを実行します。<br>
  **net start PBIEgwService**

**ファイアウォールまたはプロキシの構成**

ゲートウェイのプロキシ情報を指定する方法については、[プロキシ設定の構成](https://docs.microsoft.com/power-bi/service-gateway-proxy)に関するページをご覧ください。

PowerShell プロンプトから次のコマンドを実行することで、ファイアウォールまたはプロキシが接続をブロックしている可能性があるかどうかを確認できます。 これにより、Azure Service Bus への接続がテストされます。 これはネットワーク接続をテストするだけで、クラウド サーバー サービスまたはゲートウェイとは関係ありません。 マシンが実際にインターネットに接続できるかどうかを確認する際に役立ちます。

**Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350**

結果は、次の例のようになります。 **TcpTestSucceeded** が **True** ではない場合は、ファイアウォールによってブロックされている可能性があります。

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

徹底的に調査する場合は、**ComputerName** と **Port** の値を、このトピックの「**ポートの構成**」に記載されている値に置き換えます。

ファイアウォールが Azure Service Bus から Azure データ センターへの接続をブロックしている場合もあります。 そのような場合は、ご自分の地域のこれらのデータ センターの IP アドレスすべてをホワイトリスト登録 (ブロック解除) します。 Azure IP アドレスの一覧は、[こちら](https://www.microsoft.com/download/details.aspx?id=41653)で入手できます。

**ポートの構成**

このゲートウェイは、Azure Service Bus に対する送信接続を作成します。 通信は、送信ポート TCP 443 (既定)、5671、5672、9350 から 9354 で行われます。 ゲートウェイには受信ポートが必要ありません。

[ハイブリッド ソリューション](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/)の詳細をご確認ください。

ファイアウォールでは、データ リージョンの IP アドレスをホワイトリスト登録しておくことをお勧めします。 [Microsoft Azure データセンター IP 一覧](https://www.microsoft.com/download/details.aspx?id=41653)をダウンロードできます。これは毎週更新されています。

> [!NOTE]
> Azure データセンター IP 一覧では、アドレスは [CIDR 表記法](http://whatismyipaddress.com/cidr)で表示されます。 たとえば、10.0.0.0/24 は 10.0.0.0 から 10.0.0.24 を意味していません。

ここで、ゲートウェイで使用される完全修飾ドメイン名の一覧を示します。

| ドメイン名 | 送信ポート | 説明 |
| --- | --- | --- |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |TCP を経由する Service Bus Relay 上のリスナー (Access Control のトークン取得には 443 が必要) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *.msftncsi.com |443 |Power BI サービスがゲートウェイに到達できない場合にインターネット接続をテストするために使用されます。 |

**サインイン アカウント**

ユーザーは、職場または学校アカウントのいずれかでサインインします。 これは組織のアカウントです。 Office 365 製品にサインアップしても、実際の勤務先メール アドレスを指定しなかった場合は、nancy@contoso.onmicrosoft.com のようになります。クラウド サービス内では、お使いのアカウントが Azure Active Directory (AAD) のテナント内に保存されます。 ほとんどの場合、AAD アカウントの UPN はメール アドレスと一致します。

**Windows サービス アカウント**

オンプレミス データ ゲートウェイは、Windows サービスのログオン資格情報に *NT SERVICE\PBIEgwService* を使用するよう構成されています。 既定では、この資格情報には、サービスとしてログオンの権限があります。 これは、ゲートウェイのインストール先マシンに当てはまります。

これは、オンプレミスのデータ ソースへの接続に使用するアカウントでも、クラウド サービスへのサインインに使用する職場または学校アカウントでもありません。

認証によってプロキシ サーバーに問題が発生した場合は、[プロキシの構成](https://docs.microsoft.com/power-bi/service-gateway-proxy#changing-the-gateway-service-account-to-a-domain-user)に関するページの説明に従い、Windows サービス アカウントをドメイン ユーザーまたは管理されたサービス アカウントに切り替えることができます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問
#### <a name="general"></a>全般
**質問:** ゲートウェイではどのデータ ソースがサポートされていますか。  
**回答:** この記事の執筆時点では、次のデータ ソースがサポートされています。

* SQL Server
* SharePoint
* Oracle
* Informix
* ファイル システム
* DB2

**質問:** SQL Azure など、クラウド内のデータ ソースにはゲートウェイが必要ですか。  
**回答:** いいえ。 ゲートウェイは、オンプレミスのデータ ソースのみに接続します。

**質問:** 実際の Windows サービスはどのように呼ばれていますか。  
**回答:** [サービス] では、このゲートウェイは **Power BI Enterprise Gateway** サービスという名前で表示されます。

**質問:** クラウドからゲートウェイへの受信接続はありますか。  
**回答:** いいえ。 ゲートウェイは、Azure Service Bus への送信接続を使用します。

**質問:** 送信接続をブロックしたらどうなりますか。 何を開く必要がありますか。  
**回答:** ゲートウェイが使用するポートとホストの一覧 (上記) を参照してください。

**質問:** ゲートウェイをデータ ソースと同じマシンにインストールする必要がありますか。  
**回答:** いいえ。 ゲートウェイは、指定された接続情報を使用してデータ ソースに接続します。 この意味では、ゲートウェイをクライアント アプリケーションと考えてください。 ゲートウェイで必要なのは、指定されたサーバー名に接続できることだけです。

**質問:** ゲートウェイからデータ ソースに対してクエリを実行するための待ち時間はどのくらいですか。 最適なアーキテクチャはどのようなものですか。  
**回答:** ネットワーク待ち時間を短縮するには、できる限りデータ ソースの近くにゲートウェイをインストールしてください。 実際のデータ ソース上にゲートウェイをインストールできると、発生する待ち時間は最小限に抑えられます。 データ センターについてもご検討ください。 たとえば、サービスで米国西部のデータ センターを使用していて、SQL Server を Azure VM でホストしている場合は、この Azure VM も米国西部に配置することをお勧めします。 そうすることで、待ち時間が最小限に抑えられ、Azure VM での送信料金が回避されます。

**質問:** ネットワーク帯域幅に関する要件はありますか。  
**回答:** ネットワーク接続に十分なスループットを確保することをお勧めします。 環境はどれも異なり、送信されるデータの量によっても結果に影響があります。 ExpressRoute を使用すると、オンプレミスと Azure データ センター間にある程度のスループットを保証できるようになります。

サードパーティ製のツール [Azure Speed Test アプリ](http://azurespeedtest.azurewebsites.net/)を使用すると、スループットを正確に計ることができます。

**質問:** ゲートウェイ Windows サービスを Azure Active Directory アカウントで実行できますか。  
**回答:** いいえ。 Windows サービスには、有効な Windows アカウントが必要です。 既定では、サービスの SID *NT SERVICE\PBIEgwService* を使用して実行されます。

**質問:** 結果はどのようにクラウドに送り返されますか。  
**回答:** これは、Azure Service Bus を使用して行われます。 詳細については、「[ゲートウェイのしくみ](gateway-reference.md#how-the-gateway-works)」を参照してください。

**質問:** 資格情報はどこに保存されていますか。  
**回答:** データ ソース用に入力した資格情報は、暗号化されて、ゲートウェイ クラウド サービスに保存されています。 資格情報は、オンプレミスのゲートウェイで暗号化が解除されます。

**質問:** ゲートウェイは境界ネットワーク (DMZ、非武装地帯、スクリーン サブネットとも呼ばれます) に配置できますか。  
**回答:** ゲートウェイは、データ ソースに接続できる必要があります。 データ ソースが境界ネットワークに配置されていない場合、ゲートウェイから接続できない場合があります。 たとえば、境界ネットワークに SQL Server を実行中のコンピューターがない場合、境界ネットワークからそのコンピューターには接続できません。 境界ネットワークにゲートウェイを配置すると、ゲートウェイから SQL Server を実行中のコンピューターに到達できなくなります。

#### <a name="high-availabilitydisaster-recovery"></a>高可用性とディザスター リカバリー
**質問:** ゲートウェイで高可用性のシナリオを実現するためのプランはありますか。  
**回答:** これはロードマップにはありますが、まだ予定が決まっていません。

**質問:** ディザスター リカバリーにはどのオプションを使用できますか。  
**回答:** ゲートウェイの復元または移動には、回復キーを使用できます。 ゲートウェイをインストールするときに、回復キーを指定してください。

**質問:** 回復キーの利点は何ですか。  
**回答:** 障害発生後にゲートウェイの設定を移行または回復する方法が用意されています。

#### <a name="troubleshooting"></a>トラブルシューティング
**質問:** ゲートウェイ ログはどこにありますか。  
**回答:** このトピックの後半にある「[ツール](gateway-reference.md#tools)」を参照してください。

**質問:** オンプレミスのデータ ソースにどのようなクエリが送信されているかを確認する方法を教えてください。  
**回答:** クエリ トレースを有効にすることができます。このトレースには、送信されるクエリが含まれます。 トラブルシューティングが完了したら、忘れずに元の値に戻してください。 クエリ トレースを有効な状態にしておくと、ログの容量が大きくなります。

クエリをトレースするためにデータ ソースに用意されているツールを確認することもできます。 たとえば、SQL Server と Analysis Services に拡張イベントまたは SQL Profiler を使用できます。

## <a name="how-the-gateway-works"></a>ゲートウェイのしくみ
![しくみ](./media/gateway-reference/gateway-arch.png)

オンプレミスのデータ ソースに接続されている要素をユーザーが操作すると、次のようになります。  

1. クラウド サービスによってデータ ソース用に暗号化された資格情報と共にクエリが作成され、ゲートウェイで処理するためにキューに送信されます。

2. ゲートウェイ クラウド サービスは、クエリを分析し、要求を [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/) にプッシュします。

3. オンプレミス データ ゲートウェイは、Azure Service Bus へのポーリングを実行して保留中の要求があるかどうかを確認します。

4. ゲートウェイはクエリを取得して、資格情報の暗号化を解除し、その資格情報を使用してデータ ソースに接続します。

5. ゲートウェイは、クエリを実行するためにデータ ソースに送信します。

6. 結果は、データ ソースからゲートウェイに返され、さらにクラウド サービスに送信されます。 その後、その結果がサービスで使用されます。

## <a name="troubleshooting"></a>トラブルシューティング
#### <a name="update-to-the-latest-version"></a>最新バージョンに更新する
多くの問題は、ゲートウェイのバージョンが最新でない場合に発生します。  一般的には、常に最新バージョンにしておくことをお勧めします。  ゲートウェイを 1 か月 (またはそれ以上) 更新していない場合は、ゲートウェイの最新バージョンのインストールを検討し、問題が再現されるかどうかを確認することをお勧めします。

#### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>エラー: ユーザーをグループに追加できませんでした。  (-2147463168   PBIEgwService   Performance Log Users   )
ドメイン コントローラーにゲートウェイをインストールしようとすると、このエラーが発生することがあります。ドメイン コントローラーへのインストールはサポートされていません。 ゲートウェイは、ドメイン コントローラーではないマシン上にデプロイする必要があります。

## <a name="tools"></a>ツール
#### <a name="collecting-logs-from-the-gateway-configurator"></a>ゲートウェイ構成からのログ収集
ゲートウェイのログをいくつか収集することができます。 必ず最初にログをご確認ください。

**インストーラーのログ**

%localappdata%\Temp\On-premises_data_gateway_*.log

**構成のログ**

%localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log

**エンタープライズ ゲートウェイ サービスのログ**

C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log

**イベント ログ**

**On-premises data gateway service** のイベント ログは、**[アプリケーションとサービス ログ]** に表示されています。

![イベント ログ](./media/gateway-reference/event-logs.png)

#### <a name="fiddler-trace"></a>Fiddler のトレース
[Fiddler](http://www.telerik.com/fiddler) は、HTTP トラフィックを監視する Telerik 提供の無償ツールです。  クライアント マシンから、Power BI サービスとのやりとりを確認できます。 これにより、エラーやその他の関連情報が表示される場合もあります。
