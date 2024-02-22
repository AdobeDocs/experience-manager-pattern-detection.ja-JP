---
title: ECU
description: パターン検出コードのヘルプページ
exl-id: fd061001-b00e-44ae-bd31-71bd2fa733cd
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '235'
ht-degree: 100%

---

# ECU {#ecu}

非推奨（廃止予定）：ECU（無関係なコンテンツの使用）は CAV（コンテンツ領域違反）に置き換えられています

## 背景 {#background}

`ECU` は、コンテンツ分類ルールに違反する形でコンテンツ領域が使用されているパターンを識別します。

Sling リクエスト処理では、リソースのコンテンツ（特にリソースの `sling:resourceType` プロパティ）を使用して、コンテンツのレンダリングに用いるスクリプトを決定する方法を定義します（詳細については、「[スクリプトの検索](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html?lang=ja#locating-the-script)」を参照してください）。Sling では、「オーバーレイ」や「オーバーライド」を使用して、リソースにアクセスしたり、結合したりすることもできます。これらの方法は、[Sling Resource Merger](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html?lang=ja) および[オーバーレイ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html?lang=ja)で説明されています。

お客様が `/libs` のどの領域を安全に使用でき、オーバーレイできるのかを容易に把握できるように、`/libs` の コンテンツは「mixin」プロパティ（Public、Abstract、Final、および Internal）で分類されています。各分類は、コンテンツがどのように使用、継承、オーバーレイされるかを規定するルールを示します。詳細については、[持続可能なアップグレード](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html?lang=ja)を参照してください。

## 可能性のある影響およびリスク {#implications-and-risks}

* AEM をアップグレードすると、ページレンダリングの問題が発生したりその他の意図しない動作をする可能性があります。
* セキュリティの更新が有効ではありません。

## 可能な解決策 {#solutions}

* コンテンツオーバーレイを使用する場合は、必要最小限にとどめてください。
* 特に、制限付きコンテンツ（分類が Final と Internal のコンテンツ）にはオーバーレイを使用しないでください。
* AEM のアップグレード後、あるいは ServicePack または CumulativeFixPack のインストール後に、`/libs` に由来する変更を適合させることを検討してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
