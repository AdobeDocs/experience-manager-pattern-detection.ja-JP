---
title: CIF
description: パターン検出コードのヘルプページ
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 84aea5b24e51ce5672826bad4ec126074bf24a09
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 10%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIFは、AEM as a Cloud Service as a Commerceと互換性のない、Commerce Integration Frameworkの従来のバージョンを識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/introduction.html" text=" コンテンツとコマース"

`CIF` CIFは、AEM as a Cloud Service as a Commerceと互換性のない、Commerce Integration Frameworkの従来のバージョンを識別します。各`CIF`の結果に関するメッセージは、使用状況を識別し、追加情報を提供します。

サブタイプを使用して、各種情報を識別します。

* `commerce.integration.framework.detected`:AEM as aとのCommerce Integration Frameworkの非互換性の従来のCloud Service。


## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、Commerce Integration Frameworkのすべてのクラシックバージョンの使用を確認することです。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/changes.html" text="CIFの主な変更点"

* AEM as a Commerceの従来のバージョンは、サポートされなくなりました。Cloud Service AEM as a Cloud Serviceへのアップグレードがブロックされます。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="ツールとリソース"
>abstract="このガイドは、Experience Manager Cloud Service移行の際に更新が必要な領域の特定に役立ちます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/migration.html" text="CIFの移行ガイド"

* Experience ManagerをCloud Serviceとして使用する場合、CIFアドオンは、Adobeコマースおよびサードパーティのコマースソリューションでサポートされる唯一のコマース統合ソリューションです。 CIFアドオンは、Cloud ServiceとしてExperience Manager上のお客様に対して自動的にデプロイされるので、手動でデプロイする必要はありません。 [AEM Commerce as aCloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/storefront/getting-started.html)を参照してください。
* CIFAdobeをデプロイするプロジェクトをサポートするために、[AEM CIFコアコンポーネント](https://github.com/adobe/aem-core-cif-components)が用意されています。
* CIFアドオンは、AEM 6.5でも[ソフトウェア配布ポータル](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)を介して使用できます。 互換性があり、Cloud ServiceとしてのExperience Manager用CIFアドオンと同じ機能を提供します。調整は不要です。
* 依存関係を持つ従来のCIFは使用できなくなりました。 com.adobe.cq.commerce.api Java APIを使用するこのCIFバージョンに依存するコードは、CIFアドオンとその原則に従って調整する必要があります。
