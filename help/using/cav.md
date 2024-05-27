---
title: CAV
description: パターン検出コードのヘルプページ。
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: ht
source-wordcount: '316'
ht-degree: 100%

---

# CAV {#cav}

コンテンツ領域違反

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="コンテンツ領域違反"
>abstract="CAV コードは、コンテンツ分類ルールに違反する形でコンテンツ領域が使用されているパターンを識別します。この違反では、AEM as a Cloud Service への移行後に変更が必要になる可能性のあるオーバーレイや制限付きコンテンツの概要が示されます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Sling Resource Merger"

`CAV` は、コンテンツ分類のルールに違反する方法で使用される、様々なコンテンツ領域のパターンを識別します。

Sling リクエスト処理では、リソースのコンテンツ（特にリソースの `sling:resourceType` プロパティ）を使用して、コンテンツのレンダリングに用いるスクリプトを決定する方法を定義します。（詳しくは、[スクリプトの検索](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script)を参照してください）。また、Sling では、オーバーレイとオーバーライドを通じて、リソースにアクセスし、リソースを結合するテクニックも用意されています。これらのテクニックは、[Sling Resource Merger](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger) の一部として、および[オーバーレイ](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/platform/overlays)内で説明されています。

安全に使用およびオーバーレイできる `/libs` のどエリアをお客様に分かりやすくするため、`/libs` のコンテンツは次の「mixin」プロパティで分類されます。

* Public
* Abstract
* Final
* Internal

各分類は、コンテンツがどのように使用、継承、オーバーレイされるかを規定するルールを示します。詳細については、[持続可能なアップグレード](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades)を参照してください。

## 考えられる影響およびリスク {#implications-and-risks}

* AEM をアップグレードすると、ページレンダリングの問題が発生したりその他の意図しない動作をする可能性があります。
* セキュリティの更新が有効ではありません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="実装ガイダンス"
>abstract="様々なコンテンツ領域違反が存在するパターンが CAS で識別されたら、そのパターンを確認する必要があります。最終的および内部的なコンテンツ分類領域は避けてください。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="持続可能なアップグレード"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* コンテンツオーバーレイを使用する場合は、必要最小限にとどめてください。
* 特に、制限付きコンテンツ（分類が Final と Internal のコンテンツ）にはオーバーレイを使用しないでください。
* AEM のアップグレード、サービスパックまたは累積修正パックのインストール後に、`/libs` からの変更を適応することを検討してください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
