---
title: ASO
description: パターン検出コードのヘルプページ
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
translation-type: tm+mt
source-git-commit: 449288e567adda9998a89e0ad5198fd5a4e93f35
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 71%

---

# ASO {#aso}

AEM システムの概要

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM システムの概要"
>abstract="ASOコードは、AEMインスタンスに関する一般的な情報を識別します。 各検索結果には、移行計画やリファクタリング作業に役立つ、特定のタイプのシステム情報の1つの値が提供されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEMをCloud Serviceとして — リリースノート"

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

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="導入ガイダンス"
>abstract="ASOコードで公開された情報は、バージョン、製品アドオン、システムレベル情報など、AEM環境の一般的な情報を提供します。この情報は、AEMのCloud Serviceとしてサポートされていない製品や機能について確認する必要があります。 ヘルプと説明については、Adobeサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* サポートされていない製品や機能を含む AEM アップグレードは推奨されず、サポートの対象外となる場合があります。
* AEM as a Cloud Service における最新の変更事項については、[リリースノート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja)を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
