Social Engagement から [Azure Event Hubs](https://azure.microsoft.com/documentation/articles/event-hubs-overview/) への接続を有効にすると、オートメーション ルールを使用したイベント ハブへのソーシャル データのストリームを許可したことになります。 Social Engagement からストリームされたソーシャル データは、[事前に構成された期間](https://azure.microsoft.com/documentation/articles/event-hubs-availability-and-support-faq/) Azure Event Hubs に保存され、イベント ハブをリスニングできる任意のアプリケーションでアクセス、保存、処理することができます。  
  
 Social Engagement から送信されるソーシャル データには、ソーシャルの投稿に関する情報 (作成者と本文) や、言語、場所、センチメント、タグなどの拡充された情報が含まれることにご注意ください。Event Hubs に送信されるソーシャルの投稿の詳細については、[JSON のスキーマ定義](http://go.microsoft.com/fwlink/p/?LinkId=786643)を参照してください。