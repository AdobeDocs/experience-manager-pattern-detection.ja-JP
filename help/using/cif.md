---
title: CIF
description: パターン検出コードのヘルプページ。
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 76%

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


## 考えられる影響とリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、従来のバージョンの Commerce Integration Framework の使用状況をすべて確認することです。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/content-and-commerce/changes" text="CIF の主な変更点"

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

また、次の様々なサブタイプに対して考えられるソリューションも参照してください。

* `commerce.bundles.detected` – これらのバンドルはアップグレード時にアンインストールされます
* `commerce.packages.detected` – これらのパッケージはアップグレード中に削除されます
* `commerce.packages.dependency` - カスタムパッケージからCommerceへの依存関係を削除します
* `commerce.nodes.detected` - CQ Commerce ノードを作成しないようにカスタムコードを更新します
* `commerce.configs.detected` - カスタムコードで CQ Commerce設定プロパティを使用しない
* `commerce.users.detected` - カスタムコードで CQ Commerce サービスユーザーを使用しない
* `commerce.overlays.detected` - CQ Commerce オーバーレイの使用を削除
* `commerce.paths.detected` - コマースパスを削除するには、これらのパスがAEMで使用されていないことを確認します
* `commerce.resource.type.detected` - コマースリソースタイプの使用状況を削除
* `commerce.usage` - カスタムコードから CQ Commerce API を削除します。
