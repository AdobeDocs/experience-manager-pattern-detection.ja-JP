---
title: DG
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 4%

---


# DG {#dg}

開発者ガイドライン

## 背景 {#background}

`DG` は、 [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html) およびAEM用の選択した開発ガイドラインのCloud Serviceとしての偏差を示し [](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)ます。ベストプラクティスに従うと、システムの保守性とパフォーマンスが向上します。 これらの偏差の一部は、AEMの以前のバージョンを含む他のアプリケーションコンテキストでは問題にならない可能性がありますが、AEMをCloud Serviceとして使用する場合、問題の原因となる場合があります。

サブタイプは、検出された違反の異なるタイプを識別するために使用されます。

* `java.io.inputstream`:アプリケーションコード `java.io.InputStream` でのの使用。
* `maintenance.task.configuration`:特定の定期保守アクティビティの設定。
* `sling.commons.scheduler`:スケジュールされたタスクに対するSling CommonsスケジューラーAPIの使用。

## 可能性のある影響およびリスク {#implications-and-risks}

* `java.io.inputstream`
   * `java.io.InputStream`を使用してバイナリデータをストリーミングすると、パフォーマンスに影響を与えるまでメモリリソースを消費する可能性があります。 これは特に、AEMでCloud Serviceとして使用されるコンテナで使用できるメモリが制限されているために発生する問題です。

* `maintenance.task.configuration`
   * 以前は明示的な設定が必要だった一部のメンテナンスタスクは、AEM内でCloud Serviceとして自動的に設定および管理されるようになりました。
   * Cloud ServiceとしてのAEMでの保守タスク構成は、ソース管理に移動する必要があります。

* `sling.commons.scheduler`
   * [Sling Commonsスケジューラー](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)を使用するバックグラウンドタスクに依存するアプリケーションは、AEMでCloud Serviceとして実行を保証できないので、期待どおりに動作しない場合があります。
   * AEMは、[バックグラウンドタスクと長時間実行ジョブ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs)のCloud Service開発ガイドラインとして、スケジュールされたタスクとして実行されるコードは、いつでも実行中のインスタンスをダウンできると想定する必要があります。 したがって、コードは回復性があり、再開可能である必要があります。

## 可能な解決策 {#solutions}

* `java.io.inputstream`
   * バイナリがデータストアに直接追加される直接バイナリアップロードアプローチを使用します。
   * アセットの使用例については、[aem-upload](https://github.com/adobe/aem-upload)を使用してください。 他のタイプのバイナリの場合、カスタムアップロードロジックは、この同じパターンを基にモデル化できます。

* `maintenance.task.configuration`
   * AEMをCloud Service[メンテナンスタスク](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html)のドキュメントとして確認します。
   * [メンテナンスタスク構成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control)がソース管理にあることを確認してください。

* `sling.commons.scheduler`
   * [Sling Commonsスケジューラー](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)を[Slingジョブ](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)に置き換えます。このジョブは、少なくとも1回の実行が保証されています。
   * 長時間続くジョブは、可能であれば避ける必要があります。

* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
