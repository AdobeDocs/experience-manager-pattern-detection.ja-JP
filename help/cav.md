---
title: CAV
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 2%

---


# CAV {#cav}

コンテンツ領域違反

## 背景 {#background}

`CAV` コンテンツ分類のルールに違反する方法で異なるコンテンツ領域が使用されるパターンを識別します。

Sling要求処理は、リソースのコンテンツ（特に`sling:resourceType`プロパティ）を、コンテンツのレンダリングに使用されるスクリプトを決定する際に使用する方法を定義します。 （詳しくは、[スクリプトの検索](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script)を参照してください）。 Slingは、「Overlays」と「Overrides」を使用して、リソースにアクセスして結合する方法も提供しています。 これらは、[Sling Resource Marge](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html)および[Overlays](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html)の一部として説明されています。

`/libs`が安全に使用できる領域を顧客が理解しやすく、より安全で簡単にするために、`/libs`のコンテンツを「mixin」プロパティで分類しました。Public、Abstract、Final、Internal。 各分類は、コンテンツがユーザー、継承、オーバーレイである方法に関するルールを意味します。 詳しくは、[持続可能なアップグレード](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html)を参照してください。

## 可能性のある影響およびリスク {#implications-and-risks}

* AEMをアップグレードすると、ページレンダリングの問題やその他の不適切な動作が発生する可能性があります。
* セキュリティ更新は有効ではありません。

## 可能な解決策 {#solutions}

* 必要に応じて、コンテンツオーバーレイの使用を最小限に抑えます。
* 特に、制限付きコンテンツ（最終的な分類と内部分類）のオーバーレイは避けてください。
* AEMのアップグレード後、ServicePackまたはCumulativeFixPackのインストール後に、`/libs`からの変更を適応させることを検討します。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
