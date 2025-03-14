---
title: DG
description: パターン検出コードのヘルプページ。
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 80%

---

# DG {#dg}

開発者ガイドライン

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="開発者ガイドライン"
>abstract="DG コードは、選択された開発ガイドラインの AEM 6.5 および AEM as a Cloud Service に対する逸脱を識別します。ベストプラクティスに従うと、システムの保守性とパフォーマンスが向上します。これらの逸脱は、AEM の旧バージョンを含む他のアプリケーションコンテキストでは問題にならない場合もありますが、AEM as a Cloud Service で使用した場合に問題が起きる可能性があります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM の開発 - ガイドラインとベストプラクティス"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service の開発ガイドライン"


`DG` は、[AEM 6.5](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices) および [AEM as a Cloud Service](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines) に関して選択された開発ガイドラインの逸脱を識別します。ベストプラクティスに従うと、システムの保守性とパフォーマンスが向上します。これらの逸脱は、AEM の旧バージョンを含む他のアプリケーションコンテキストでは問題にならない場合もありますが、AEM as a Cloud Service で使用した場合に問題が起きる可能性があります。

サブタイプを使用して、検出された各種の違反を識別します。

* `java.io.inputstream`：アプリケーションコード中での `java.io.InputStream` の使用
* `maintenance.task.configuration`：特定の定期的なメンテナンスアクティビティの設定
* `sling.commons.scheduler`：スケジュールされたタスクでの Sling Commons Scheduler API の使用
* `unsupported.asset.api`：アプリケーションコードでのサポートされていない Asset Manager API の使用。
* `javax.jcr.observation.EventListener`：アプリケーションコードでのイベントリスナーの使用。
* `custom.guava.cache`：アプリケーションコードでの Guava キャッシュの使用。
* `java.api`：一部の Java API は、Java 11 から Java 17 に削除されました。
* `configuration.admin`：設定にアクセスしているカスタムコードはフラグ付けされます。
* `guava.api`:AEM 6.5 LTS では、Guava は標準ではサポートされていません。
* `com.day.cq.dam.scene7.api.model`: `package com.day.cq.dam.scene7.api.model` のメジャーバージョンが変更されました。

## 考えられる影響とリスク {#implications-and-risks}

* `java.io.inputstream`
   * `java.io.InputStream` を使用してバイナリデータのストリーミングを行うと、パフォーマンスに影響を与えるほどメモリリソースを消費する場合があります。この問題は、AEM as a Cloud Service で使用するコンテナで利用可能なメモリが限られているため発生します。

* `maintenance.task.configuration`
   * 従来、明示的な設定が要求されたメンテナンスタスクの一部は、AEM as a Cloud Service 内で自動的に設定、管理されるようになりました。
   * AEM as a Cloud Service でのメンテナンスタスク設定はソースコントロールに移行する必要があります。

* `sling.commons.scheduler`
   * [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) を使用するバックグラウンドタスクに依存するアプリケーションは、AEM as a Cloud Service での実行が保証されないため、期待通り動作しないことがあります。
   * [バックグラウンドタスクと長時間実行されているジョブ](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#background-tasks-and-long-running-jobs)に関するガイドラインでは、スケジュールされたタスクとして実行されるコードは、実行されているインスタンスがいつでも停止される可能性があることも前提にする必要があることを示しています。したがって、コードには耐障害性と再開可能性が求められます。

* `unsupported.asset.api`
   * 次の AssetManager の API は、AEM as a Cloud Service ではサポート対象外とマークされています。
      * createAssetForBinary
      * getAssetForBinary
      * removeAssetForBinary
      * createAsset

* `javax.jcr.observation.EventListener`
   * イベントリスナーに依存するアプリケーションは、実行が保証されないので、期待どおりに動作しない可能性があります。

* `custom.guava.cache`
   * Guava キャッシュを使用すると、AEM でパフォーマンスの問題が発生する可能性があります。

* `java.api`
   * JRE17 上のAEM 6.5 LTS では、これらの削除された Java API は使用できなくなり、使用も失敗します。

* `configuration.admin`
   * サポートされていない設定（ソーシャルなど）を使用していないことを確認するために、使用状況を調べる必要があります。

* `guava.api`
   * Guava はAEM 6.5 LTS ではサポートされていないので、guava を使用しているカスタムコードはアクティブになりません。

* `com.day.cq.dam.scene7.api.model`
   * カスタムバンドル内の読み込まれたパッケージ `com.day.cq.dam.scene7.api.model` は、メジャーバージョンの変更が原因で解決されません。


## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="実装ガイダンス"
>abstract="Sling Commons Scheduler の使用について実装を確認します。これらを Sling ジョブに再構造化し、システムメンテナンスタスクを再構造化し、バイナリデータのストリーミングを確認し、AEM as a Cloud Service に準拠するようにコードをリファクタリングします。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling ジョブ"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/operations/maintenance" text="AEM as a Cloud Service のメンテナンスタスク"

* `java.io.inputstream`
   * バイナリをデータストアに直接追加するダイレクトバイナリアップロードアプローチを使用します。
   * アセットのユースケースについては、[aem-upload](https://github.com/adobe/aem-upload) を参照してください。これ以外のバイナリタイプについても、同じパターンをモデルとしたカスタムアップロードロジックを作成できます。

* `maintenance.task.configuration`
   * AEM as a Cloud Service の[メンテナンスタスク](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/operations/maintenance)に関するドキュメントを参照してください。
   * [メンテナンスタスク設定](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/deploying/overview#maintenance-tasks-configuration-in-source-control) がソースコントロールされていることを確認します。

* `sling.commons.scheduler`
   * [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) を、[Sling ジョブ](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing) に置き換えます。これにより最低 1 回の実行が保証されます。
   * 長時間実行されているジョブは、回避する必要があります。

* `unsupported.asset.api`
   * Asset Manager のサポートされていない API を使用する代わりに、[aem-upload](https://github.com/adobe/aem-upload) を参照してください。

* `javax.jcr.observation.EventListener`
   * イベントリスナーを使用する代わりに、確実に処理を行うために、イベント処理メカニズムを [Sling ジョブ](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)にリファクタリングすることをお勧めします。

* `custom.guava.cache`
   * キャッシュは、必要に応じて AEM の外部で作成する必要があります。外部キャッシュソリューションを検討することをお勧めします。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。

* `configuration.admin`
   * サポートされていない機能（ソーシャルなど）の設定使用を削除します。

* `guava.api`
   * Guava をインストールするか、カスタムコードで Guava が使用されている場合は使用状況を削除します。

* `com.day.cq.dam.scene7.api.model`
   * 読み込んだパッケージ `com.day.cq.dam.scene7.api.model` のバージョン範囲を **3.0.4** に更新します。