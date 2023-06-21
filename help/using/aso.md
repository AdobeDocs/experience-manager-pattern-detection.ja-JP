---
title: ASO
description: パターン検出コードのヘルプページ
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: a899311c975efee180bc1d3bc3c7bca30d429a22
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 93%

---

# ASO {#aso}

AEM システムの概要

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM システムの概要"
>abstract="ASO コードは、AEM インスタンスに関する一般的な情報を識別します。各検索結果には、移行計画やリファクタリング作業に役立つ、特定タイプのシステム情報の値が 1 つ示されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="AEM as a Cloud Service - リリースノート"

`ASO` は、AEM インスタンスに関する一般的な情報を識別します。各検索結果に、特定タイプのシステム情報の値が 1 つ示されます。

サブタイプを使用して、各種情報を識別します。

* `aem.version`：AEM のバージョン。
* `aem.product`：使用されているAEM 製品（Commerce、Formsなど）の検出。
* `node.count`：特定のタイプ（ページ、アセットなど）のノードの概算数とノードの総計。
* `node.store`：ノードストアの実装タイプ（SegmentNodeStore、DocumentNodeStore）とそのサイズ。
* `data.store`：データストアの実装タイプ（FileDataStore、S3DataStore、AzureDataStore）。
* `maintenance.task`：メンテナンスタスク。
* `slow.query`：低速のクエリ。
* `group.membership`：グループ内のユーザーとサブグループ（ダイレクト／宣言されたメンバーのみ）の数。
* `cqtag.count`：CQ タグ付きアセットの数。
* `smarttag.count`：スマートタグ付きアセットの数。
* `ccom.version`：コアコンポーネントパッケージのバージョン。
* `instance.type`：AEM インスタンスのタイプ（author|publish）。
* `unprocessed.asset.count`：未処理のアセットの数。
* `vanity.url.count`：バニティ URL の数です。
* `index.size`：移行可能な Lucene インデックスの合計サイズ。
* `workflow.count`：実行中で古い状態のオーサーワークフローの数。
* `jvm.arguments`:AEMの起動時にコマンドラインに追加された JVM 引数。

## 考えられる影響およびリスク {#implications-and-risks}

* AEM のバージョン、ノード数、グループメンバーシップ、ノードストア、データストアの実装タイプ、CQ タグ数、スマートタグ数、コアコンポーネントのバージョン、AEM インスタンスタイプ、および未処理のアセットカウントは、情報提供を目的として提供されます。
* バニティー URL の数が多い（1000 を超える）と、高コストなクエリにより、Dispatcher とパブリッシュサーバーに負荷がかかる場合があります。
* カスタムアプリケーションは、AEM as a Cloud Service で使用できない製品や機能に依存している場合があります。
* サポートされていない機能を使用したままアップグレードすると、アップグレードが失敗し、アプリケーションが機能しなくなることがあります。
* 実行中または古い状態のオーサーワークフローが多数あると、パフォーマンスが低下する可能性があります。
* クエリが遅いと、システムのパフォーマンスが低下する場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="実装ガイダンス"
>abstract="ASO コードで公開された情報には、バージョン、製品アドオン、システムレベル情報など、AEM 環境の一般的な情報が含まれています。AEM as a Cloud Service でサポートされていない製品や機能については、この情報を確認してください。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* サポートされていない製品や機能を含む AEM アップグレードは推奨されず、サポートの対象外となる場合があります。
* 未処理のアセットを処理し、アセットの jcr:content ノードで dam:assetState プロパティを「processed」に設定するか、AEMaaCS に移行する前に移行セットからこれらのアセットを削除する必要があります。
* バニティー URL は Apache Rewrites に置き換えることができます。
* 詳しくは、 [ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-65/developing/bestpractices/troubleshooting-slow-queries.html) を参照してください。
* AEM as a Cloud Service における最新の変更事項については、[リリースノート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja)を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
