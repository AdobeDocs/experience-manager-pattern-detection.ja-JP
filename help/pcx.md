---
title: PCX
description: パターン検出コードのヘルプページ
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 74%

---

# PCX {#pcx}

ページの複雑さ

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="ページの複雑さ"
>abstract="PCXは、構造内に多数のノードを含むページを識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja" text="主な変更点 — AEMをCloud Serviceとして"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="AEMをCloud Serviceとして — リリースノート"

`PCX` は、構造中に多数のノードを含むページを識別します。

サブタイプを使用して、各種情報を識別します。

* `page.complexity.medium`：ページに、レンダリングパフォーマンスに影響する可能性のある比較的多くのノードが含まれています。
* `page.complexity.high`：ページに、レンダリングパフォーマンスに影響する可能性のあるきわめて多くのノードが含まれています。

## 可能性のある影響およびリスク {#implications-and-risks}

* ページに含まれる多数のノードが、レンダリングパフォーマンスに影響を及ぼす可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="導入ガイダンス"
>abstract="ベストプラクティスは、ページの複雑さを軽減するためのコンテンツ構造を確認することです。これにより、ページレンダリングのパフォーマンスが向上します。 ヘルプと説明を求めるAdobeサポートにご連絡ください。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* ページに含まれる総ノード数を減らすために次の手順を実行します。
   * 不要なコンテナがないことを確認します。
   * コンテナを減らしてもレイアウトが同じになるかどうかをテストします。
   * ページのコンテンツを簡素化します。
   * ノード構造の深さを減らします。
   * 簡素化のために、内部のエクスペリエンスフラグメントをリファクタリングします。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
