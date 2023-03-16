---
title: CAV
description: パターン検出コードのヘルプページ
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: 1966a3e83ab6b2247d9f1095c8965eac399e3b6e
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 100%

---

# CAV {#cav}

コンテンツ領域違反

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="コンテンツ領域違反"
>abstract="CAV コードは、コンテンツ分類ルールに違反する形でコンテンツ領域が使用されているパターンを識別します。この違反では、AEM as a Cloud Service への移行後に変更が必要になる可能性のあるオーバーレイや制限付きコンテンツの概要が示されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html?lang=ja#platform" text="Sling Resource Merger"

`CAV` は、コンテンツ分類ルールに違反する形でコンテンツ領域が使用されているパターンを識別します。

Sling リクエスト処理では、リソースのコンテンツ（特にリソースの `sling:resourceType` プロパティ）を使用して、コンテンツのレンダリングに用いるスクリプトを決定する方法を定義します（詳しくは、[スクリプトの検索](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html?lang=ja#locating-the-script)を参照してください）。Sling では、「オーバーレイ」や「オーバーライド」を使用して、リソースにアクセスしたり、結合したりすることもできます。これらの方法は、[Sling Resource Merger](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html?lang=ja) および[オーバーレイ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html?lang=ja)で説明されています。

お客様が `/libs` のどの領域を安全に使用でき、オーバーレイできるのかを容易に把握できるように、`/libs` の コンテンツは「mixin」プロパティ（Public、Abstract、Final、および Internal）で分類されています。各分類は、コンテンツがどのように使用、継承、オーバーレイされるかを規定するルールを示します。詳細については、[持続可能なアップグレード](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html?lang=ja)を参照してください。

## 考えられる影響およびリスク {#implications-and-risks}

* AEM をアップグレードすると、ページレンダリングの問題が発生したりその他の意図しない動作をする可能性があります。
* セキュリティの更新が有効ではありません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="実装ガイダンス"
>abstract="様々なコンテンツ領域違反が存在するパターンが CASで識別されたら、それらを確認する必要があります。最終的および内部的なコンテンツ分類領域は避けてください。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html?lang=ja" text="持続可能なアップグレード"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* コンテンツオーバーレイを使用する場合は、必要最小限にとどめてください。
* 特に、制限付きコンテンツ（分類が Final と Internal のコンテンツ）にはオーバーレイを使用しないでください。
* AEM のアップグレード後、あるいは ServicePack または CumulativeFixPack のインストール後に、`/libs` に由来する変更を適合させることを検討してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
