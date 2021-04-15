---
title: DG
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: ht
source-wordcount: '409'
ht-degree: 100%

---


# DG {#dg}

開発者ガイドライン

## 背景 {#background}

`DG` は、選択された開発ガイドラインの [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html?lang=ja) および [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja) に対する逸脱を識別します。ベストプラクティスに従うと、システムの保守性とパフォーマンスが向上します。これらの逸脱は、AEM の旧バージョンを含む他のアプリケーションコンテキストでは問題にならない場合もありますが、AEM as a Cloud Service で使用した場合に問題が起きる可能性があります。

サブタイプを使用して、検出された各種の違反を識別します。

* `java.io.inputstream`：アプリケーションコード中での `java.io.InputStream` の使用
* `maintenance.task.configuration`：特定の定期的なメンテナンスアクティビティの設定
* `sling.commons.scheduler`：スケジュールされたタスクでの Sling Commons Scheduler の使用

## 可能性のある影響およびリスク {#implications-and-risks}

* `java.io.inputstream`
   * `java.io.InputStream` を使用してバイナリデータのストリーミングを行うと、パフォーマンスに影響がほどメモリリソースを消費することがあります。これは、AEM as a Cloud Service で使用するコンテナで利用可能なメモリに制限があるため、特に問題になります。

* `maintenance.task.configuration`
   * 従来、明示的な設定が要求されたメンテナンスタスクの一部は、 AEM as a Cloud Service 内で自動的に設定、管理されるようになりました。
   * AEM as a Cloud Service でのメンテナンスタスク設定はソースコントロールに移行する必要があります。

* `sling.commons.scheduler`
   * [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) を使用するバックグラウンドタスクに依存するアプリケーションは、AEM as a Cloud Service での実行が保証されないため、期待通り動作しないことがあります。
   * [バックグラウンドタスクと長時間を要するジョブ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja#background-tasks-and-long-running-jobs)に関する AEM as a Cloud Service 開発ガイドラインでは、スケジュールされたタスクとして実行されるコードは、それが実行されているインスタンスがいつでも停止できることを前提にすべきであるとしています。したがって、コードには耐障害性と再開可能性が求められます。

## 可能な解決策 {#solutions}

* `java.io.inputstream`
   * バイナリをデータストアに直接追加するダイレクトバイナリアップロードアプローチを使用します。
   * アセットのユースケースには、[aem-upload](https://github.com/adobe/aem-upload) を使用してください。これ以外のバイナリタイプについても、同じパターンをモデルとしたカスタムアップロードロジックを作成できます。

* `maintenance.task.configuration`
   * AEM as a Cloud Service の[メンテナンスタスク](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html?lang=ja)に関するドキュメントを参照してください。
   * [メンテナンスタスク設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=ja#maintenance-tasks-configuration-in-source-control) がソースコントロールされていることを確認します。

* `sling.commons.scheduler`
   * [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) を、[Sling Jobs](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing) に置き換えます。これにより最低 1 回の実行が保証されます。
   * 長時間続くジョブは、可能な限り使用しないようにします。

* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
