---
title: ECU
description: パターン検出コードのヘルプページ。
exl-id: fd061001-b00e-44ae-bd31-71bd2fa733cd
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 75%

---

# ECU {#ecu}

非推奨（廃止予定）：ECU（無関係なコンテンツの使用）は CAV（コンテンツ領域違反）に置き換えられています

## 背景 {#background}

`ECU` は、コンテンツ分類ルールに違反する形でコンテンツ領域が使用されているパターンを識別します。

Sling リクエスト処理では、リソースのコンテンツ（特にリソースの `sling:resourceType` プロパティ）を使用して、コンテンツのレンダリングに用いるスクリプトを決定する方法を定義します。（詳細については、「[スクリプトの検索](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script)」を参照してください）。Sling には、オーバーレイとオーバーライドを使用してリソースにアクセスし、マージする手法も用意されています。 これらの手法については、 [Sling Resource Merger](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger) および [オーバーレイ](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/platform/overlays).

お客様がより安全かつ簡単に以下の分野を理解できるようにする `/libs` 安全に使用してオーバーレイできる、コンテンツ： `/libs` は、「mixin」プロパティで分類されています。

* 公開
* 抽象
* 最終
* 内部

各分類は、コンテンツがどのように使用、継承、オーバーレイされるかを規定するルールを示します。詳細については、[持続可能なアップグレード](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades)を参照してください。

## 考えられる影響およびリスク {#implications-and-risks}

* AEM をアップグレードすると、ページレンダリングの問題が発生したりその他の意図しない動作をする可能性があります。
* セキュリティの更新が有効ではありません。

## 可能な解決策 {#solutions}

* コンテンツオーバーレイを使用する場合は、必要最小限にとどめてください。
* 特に、制限付きコンテンツ（分類が Final と Internal のコンテンツ）にはオーバーレイを使用しないでください。
* AEM のアップグレード、サービスパックまたは累積修正パックのインストール後に、`/libs` からの変更を適応することを検討してください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
