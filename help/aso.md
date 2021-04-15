---
title: ASO
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: ht
source-wordcount: '198'
ht-degree: 100%

---


# ASO {#aso}

AEM システムの概要

## 背景 {#background}

`ASO` は、AEM インスタンスに関する一般的な情報を識別します。各検索結果に、特定タイプのシステム情報の値が 1 つ示されます。

サブタイプを使用して、各種情報を識別します。

* `aem.version`：AEM のバージョン
* `aem.product`：使用されているAEM 製品（Commerce、Formsなど）の検出
* `node.count`：特定タイプ（ページ、アセットなど）のノードの概算数
* `node.store`：ノードストアの実装タイプ（SegmentNodeStore、DocumentNodeStore）
* `data.store`：データストアの実装タイプ（FileDataStore、S3DataStore、AzureDataStore）
* `maintenance.task`：メンテナンスタスク
* `slow.query`：低速のクエリ

## 可能性のある影響およびリスク {#implications-and-risks}

* AEM バージョン、ノード数、ノードストアとデータストアの実装タイプは、情報提供を目的として報告されます。
* カスタムアプリケーションは、AEM as a Cloud Service で使用できない製品や機能に依存している場合があります。
* サポートされていない機能を使用したままアップグレードすると、アップグレードが失敗し、アプリケーションが機能しなくなることがあります。

## 可能な解決策 {#solutions}

* サポートされていない製品や機能を含む AEM アップグレードは推奨されず、サポートの対象外となる場合があります。
* AEM as a Cloud Service における最新の変更事項については、[リリースノート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja)を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
