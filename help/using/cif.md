---
title: CIF
description: パターン検出コードのヘルプページ。
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '307'
ht-degree: 100%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF は、AEM as a Cloud Service と互換性のない、クラシックバージョンの Commerce Integration Framework の使用状況を特定します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/content-and-commerce/introduction" text=" コンテンツとコマース"

`CIF` は、AEM as a Cloud Service と互換性のない、クラシックバージョンの Commerce Integration Framework の使用状況を識別します。各 `CIF` 検索結果に関するメッセージでは、使用状況が識別され、追加情報が提供されます。

サブタイプを使用すると、様々なタイプの情報を識別できます。

* `commerce.integration.framework.detected`：AEM as a Cloud Service と互換性のない Commerce Integration Framework の従来のバージョン。


## 考えられる影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、従来のバージョンの Commerce Integration Framework の使用状況をすべて確認することです。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/content-and-commerce/change" text="CIF の主な変更点"

* AEM as a Cloud Service では、Commerce Integration Framework の従来のバージョンはサポートされなくなりました。これにより、AEM as a Cloud Service へのアップグレードがブロックされます。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="ツールとリソース"
>abstract="このガイドは、Experience Manager Cloud Service の移行のために更新する必要がある領域を識別するのに役立ちます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/content-and-commerce/migration" text="CIF の移行ガイド"

* Experience Manager as a Cloud Service の場合、CIF アドオンは、Adobe Commerce およびサードパーティのコマースソリューションでサポートされる、唯一のコマース統合ソリューションです。CIF アドオンは、Experience Manager as a Cloud Service を使用するお客様の場合は自動的にデプロイされるので、手動でデプロイする必要はありません。[AEM Commerce as a Cloud Service - はじめに](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/content-and-commerce/storefront/getting-started)を参照してください。
* CIF をデプロイするプロジェクトをサポートするために、アドビでは [AEM CIF コアコンポーネント](https://github.com/adobe/aem-core-cif-components)を提供しています。
* AEM 6.5 用の CIF アドオンは、[ソフトウェア配布ポータル](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)を通じて入手できます。これは互換性があり、Experience Manager as a Cloud Service 用の CIF アドオンと同じ機能を提供します。調整は不要です。
* 依存関係を持つクラシック CIF は使用できなくなりました。com.adobe.cq.commerce.api Java™ API を使用しているこの CIF バージョンに依存するコードは、CIF アドオンとその原則に従って調整する必要があります。
