---
title: CIF
description: パターン検出コードのヘルプページ
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: d50f278a5b74b625b650bca7af67dfd77283ad9e
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 100%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF は、AEM as a Cloud Service と互換性のない、Commerce Integration Framework の従来のバージョンを識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/introduction.html?lang=ja" text=" コンテンツとコマース"

`CIF` CIF は、AEM as a Cloud Service と互換性のない、Commerce Integration Framework の従来のバージョンを識別します。`CIF` の各検索結果に関するメッセージには、使用状況と追加情報が記載されます。

サブタイプを使用して、各種情報を識別します。

* `commerce.integration.framework.detected`：AEM as a Cloud Service と互換性のない Commerce Integration Framework の従来のバージョン。


## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、従来のバージョンの Commerce Integration Framework の使用状況をすべて確認することです。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/changes.html?lang=ja" text="CIF の主な変更点"

* AEM as a Cloud Service では、Commerce Integration Framework の従来のバージョンはサポートされなくなりました。これにより、AEM as a Cloud Service へのアップグレードがブロックされます。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="ツールとリソース"
>abstract="このガイドは、Experience Manager Cloud Service の移行時に、更新が必要な領域を特定するのに役立ちます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/migration.html?lang=ja" text="CIF の移行ガイド"

* Experience Manager as a Cloud Service では、CIF アドオンが、Adobe コマースおよびサードパーティのコマースソリューションでサポートされる唯一のコマース統合ソリューションです。CIF アドオンは、Experience Manager as a Cloud Service を使用するお客様の場合は自動的にデプロイされるので、手動でデプロイする必要はありません。[AEM Commerce as a Cloud Service の概要](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/storefront/getting-started.html?lang=ja)を参照してください。
* CIF をデプロイするプロジェクトをサポートするために、アドビでは、[AEM CIF コアコンポーネント](https://github.com/adobe/aem-core-cif-components)を提供しています。
* CIF アドオンは、AEM 6.5 で利用可能で、[ソフトウェア配布ポータル](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)からも入手できます。これは互換性があり、Experience Manager as a Cloud Service 用の CIF アドオンと同じ機能を提供します。調整は不要です。
* 依存関係を持つ従来の CIF 使用できなくなりました。com.adobe.cq.commerce.api Java API を使用するこの CIF バージョンに依存するコードは、CIF アドオンとその原則に従って調整する必要があります。
