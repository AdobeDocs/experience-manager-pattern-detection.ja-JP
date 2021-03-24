---
title: 麻生
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 7%

---


# ASO {#aso}

AEMシステムの概要

## 背景 {#background}

`ASO` AEMインスタンスに関する一般的な情報を識別します。各検索は、特定のタイプのシステム情報の1つの値を提供します。

サブタイプは、異なる種類の情報を識別するために使用されます。

* `aem.version`:AEMバージョン。
* `aem.product`:AEM製品の使用の検出(コマース、Formsなど)
* `node.count`:特定のタイプ（ページ、アセットなど）のノード数の概算。
* `node.store`:ノードストアの実装タイプ(SegmentNodeStore、DocumentNodeStore)。
* `data.store`:データストア実装の種類(FileDataStore、S3DataStore、AzureDataStore)。
* `maintenance.task`:メンテナンスタスク。
* `slow.query`:ゆっくりしたクエリ。

## 可能性のある影響およびリスク {#implications-and-risks}

* AEMバージョン、ノード数、ノードストアとデータストアの実装タイプは、情報提供を目的としています。
* カスタムアプリケーションは、AEMでCloud Serviceとして使用できない製品や機能に依存している場合があります。
* サポートされていない機能を使用してアップグレードすると、アップグレードに失敗し、アプリケーションが機能しなくなる場合があります。

## 可能な解決策 {#solutions}

* サポートされていない製品や機能を含むAEMアップグレードは推奨されないため、サポートされない場合があります。
* Cloud ServiceとしてのAEMの最新の変更点については、[リリースノート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja)を参照してください。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
