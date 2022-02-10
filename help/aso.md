---
title: ASO
description: パターン検出コードのヘルプページ
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: ff4f798d540d52d7875e514a2edb959e64e068fb
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 83%

---

# 麻生 {#aso}

AEM システムの概要

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM システムの概要"
>abstract="ASO コードは、AEM インスタンスに関する一般的な情報を識別します。各検索結果には、移行計画やリファクタリング作業に役立つ、特定タイプのシステム情報の値が 1 つ示されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - リリースノート"

`ASO` は、AEM インスタンスに関する一般的な情報を識別します。各検索結果に、特定タイプのシステム情報の値が 1 つ示されます。

サブタイプを使用して、各種情報を識別します。

* `aem.version`：AEM のバージョン
* `aem.product`：使用されているAEM 製品（Commerce、Formsなど）の検出
* `node.count`：特定のタイプ（ページ、アセットなど）のノードの概算数とノードの総計。
* `node.store`：ノードストアの実装タイプ（SegmentNodeStore、DocumentNodeStore）とそのサイズ。
* `data.store`：データストアの実装タイプ（FileDataStore、S3DataStore、AzureDataStore）
* `maintenance.task`：メンテナンスタスク
* `slow.query`：低速のクエリ
* `group.membership`:グループ内のユーザーとサブグループ（ダイレクト／宣言されたメンバーのみ）の数。
* `cqtag.count`:CQ タグ付きアセットの数。
* `smarttag.count`:スマートタグ付きアセットの数。
* `ccom.version`:コアコンポーネントパッケージのバージョン。
* `instance.type`:AEMインスタンスのタイプ (author|publish)。
* `unprocessed.asset.count`:未処理のアセットの数。

## 可能性のある影響およびリスク {#implications-and-risks}

* AEMのバージョン、ノード数、グループメンバーシップ、ノードストア、データストアの実装タイプ、CQ タグ数、スマートタグ数、コアコンポーネントのバージョンおよびAEMインスタンスタイプは、情報提供を目的として提供されます。
* カスタムアプリケーションは、AEM as a Cloud Service で使用できない製品や機能に依存している場合があります。
* サポートされていない機能を使用したままアップグレードすると、アップグレードが失敗し、アプリケーションが機能しなくなることがあります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="実装ガイダンス"
>abstract="ASO コードで公開された情報には、バージョン、製品アドオン、システムレベル情報など、AEM 環境の一般的な情報が含まれています。AEM as a Cloud Service でサポートされていない製品や機能については、この情報を確認してください。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* サポートされていない製品や機能を含む AEM アップグレードは推奨されず、サポートの対象外となる場合があります。
* AEM as a Cloud Service における最新の変更事項については、[リリースノート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja)を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
