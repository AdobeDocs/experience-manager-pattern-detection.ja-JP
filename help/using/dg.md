---
title: DG
description: パターン検出コードのヘルプページ
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 76%

---

# DG {#dg}

開発者ガイドライン

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="開発者ガイドライン"
>abstract="DG コードは、選択された開発ガイドラインの AEM 6.5 および AEM as a Cloud Service に対する逸脱を識別します。ベストプラクティスに従うと、システムの保守性とパフォーマンスが向上します。これらの逸脱は、AEM の旧バージョンを含む他のアプリケーションコンテキストでは問題にならない場合もありますが、AEM as a Cloud Service で使用した場合に問題が起きる可能性があります。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM の開発 - ガイドラインとベストプラクティス"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service の開発ガイドライン"


DG は、次の項目について、選択された開発ガイドラインの逸脱を特定します [AEM 6.5](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices) および [AEMas a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines). ベストプラクティスに従うと、システムの保守性とパフォーマンスが向上します。これらの逸脱は、AEM の旧バージョンを含む他のアプリケーションコンテキストでは問題にならない場合もありますが、AEM as a Cloud Service で使用した場合に問題が起きる可能性があります。

サブタイプを使用して、検出された各種の違反を識別します。

* `java.io.inputstream`：アプリケーションコード中での `java.io.InputStream` の使用
* `maintenance.task.configuration`：特定の定期的なメンテナンスアクティビティの設定
* `sling.commons.scheduler`：スケジュールされたタスクでの Sling Commons Scheduler API の使用
* `unsupported.asset.api`：アプリケーションコードでのサポートされていない Asset Manager API の使用。
* `javax.jcr.observation.EventListener`：アプリケーションコードでのイベントリスナーの使用。
* `custom.guava.cache`：アプリケーションコードでの Guava キャッシュの使用。

## 考えられる影響およびリスク {#implications-and-risks}

* `java.io.inputstream`
   * `java.io.InputStream` を使用してバイナリデータのストリーミングを行うと、パフォーマンスに影響がほどメモリリソースを消費することがあります。これは、AEM as a Cloud Service で使用するコンテナで利用可能なメモリに制限があるため、特に問題になります。

* `maintenance.task.configuration`
   * 従来、明示的な設定が要求されたメンテナンスタスクの一部は、AEM as a Cloud Service 内で自動的に設定、管理されるようになりました。
   * AEM as a Cloud Service でのメンテナンスタスク設定はソースコントロールに移行する必要があります。

* `sling.commons.scheduler`
   * [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) を使用するバックグラウンドタスクに依存するアプリケーションは、AEM as a Cloud Service での実行が保証されないため、期待通り動作しないことがあります。
   * ガイドライン： [バックグラウンドタスクと長時間実行ジョブ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#background-tasks-and-long-running-jobs) また、スケジュールされたタスクとして実行するコードでは、コードを実行しているインスタンスがいつでも停止する可能性があることを前提にする必要があることを示します。 したがって、コードには耐障害性と再開可能性が求められます。

* `unsupported.asset.api`
   * 次の Asset Manager の API は、AEM as a Cloud Service ではサポート対象外とマークされています。
      * createAssetForBinary
      * getAssetForBinary
      * removeAssetForBinary
      * createAsset

* `javax.jcr.observation.EventListener`
   * イベントリスナーに依存するアプリケーションは、実行が保証されないので、期待どおりに動作しない可能性があります。

* `custom.guava.cache`
   * Guava キャッシュを使用すると、AEM でパフォーマンスの問題が発生する可能性があります。


## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="実装ガイダンス"
>abstract="Sling Commons Scheduler の使用について実装を確認します。 Sling ジョブに再構築し、システムメンテナンスタスクを再構築し、バイナリデータのストリーミングを確認し、AEMas a Cloud Service環境に準拠するようにコードをリファクタリングします。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling ジョブ"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/maintenance" text="AEM as a Cloud Service のメンテナンスタスク"

* `java.io.inputstream`
   * バイナリをデータストアに直接追加するダイレクトバイナリアップロードアプローチを使用します。
   * アセットのユースケースについては、を参照してください。 [aem-upload](https://github.com/adobe/aem-upload). これ以外のバイナリタイプについても、同じパターンをモデルとしたカスタムアップロードロジックを作成できます。

* `maintenance.task.configuration`
   * AEM as a Cloud Service の[メンテナンスタスク](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/maintenance)に関するドキュメントを参照してください。
   * [メンテナンスタスク設定](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/overview#maintenance-tasks-configuration-in-source-control) がソースコントロールされていることを確認します。

* `sling.commons.scheduler`
   * [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) を、[Sling ジョブ](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing) に置き換えます。これにより最低 1 回の実行が保証されます。
   * 長時間実行されているジョブは避ける必要があります。

* `unsupported.asset.api`
   * サポートされていない Asset Manager の API を使用する代わりに、を参照してください [aem-upload](https://github.com/adobe/aem-upload).

* `javax.jcr.observation.EventListener`
   * イベントリスナーを使用する代わりに、確実に処理を行うために、イベント処理メカニズムを [Sling ジョブ](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)にリファクタリングすることをお勧めします。

* `custom.guava.cache`
   * 必要に応じて、AEMの外部でキャッシュを作成してください。 外部キャッシュソリューションを検討することをお勧めします。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
