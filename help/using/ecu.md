---
title: ECU
description: パターン検出コードのヘルプページ
exl-id: fd061001-b00e-44ae-bd31-71bd2fa733cd
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 50%

---

# ECU {#ecu}

非推奨（廃止予定）：ECU（無関係なコンテンツの使用）は CAV（コンテンツ領域違反）に置き換えられています

## 背景 {#background}

`ECU`  コンテンツ領域がコンテンツ分類ルールに違反する形で使用されているパターンを識別します。

Sling のリクエスト処理では、リソースのコンテンツとそのプロパティを定義します `sling:resourceType` プロパティは、特に、コンテンツのレンダリングに使用するスクリプトを決定するために使用されます。 （詳細については、「[スクリプトの検索](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script)」を参照してください）。Sling では、「オーバーレイ」や「オーバーライド」を使用して、リソースにアクセスしたり、結合したりすることもできます。これらの方法は、[Sling Resource Merger](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger) および[オーバーレイ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/overlays)で説明されています。

お客様がより安全かつ簡単に以下の分野を理解できるようにする `/libs` 安全に使用でき、コンテンツをにオーバーレイできる `/libs` は、「Public」、「Abstract」、「Final」、「Internal」の各プロパティで分類されています。 各分類は、コンテンツがどのように使用、継承、オーバーレイされるかを規定するルールを示します。詳細については、[持続可能なアップグレード](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades)を参照してください。

## 可能性のある影響およびリスク {#implications-and-risks}

* AEM をアップグレードすると、ページレンダリングの問題が発生したりその他の意図しない動作をする可能性があります。
* セキュリティの更新が有効ではありません。

## 可能な解決策 {#solutions}

* コンテンツオーバーレイを使用する場合は、必要最小限にとどめてください。
* 特に、制限付きコンテンツ（分類が Final と Internal のコンテンツ）にはオーバーレイを使用しないでください。
* から得られた変更を適応させることを検討する `/libs` AEMのアップグレード、サービスパック、または累積修正パックのインストール後。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
