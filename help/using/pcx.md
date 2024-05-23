---
title: PCX
description: パターン検出コードのヘルプページ。
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
source-git-commit: b77a168fc8c075e8e41149a38df4d83fd2504a14
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 89%

---

# PCX {#pcx}

ページの複雑さ

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="ページの複雑さ"
>abstract="PCX は、構造中に多数のノードを含むページを識別します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - リリースノート"

`PCX` は、構造中に多数のノードを含むページを識別します。

サブタイプを使用すると、様々なタイプの情報を識別できます。

* `page.complexity.medium`：ページに、レンダリングパフォーマンスに影響する可能性のある比較的多くのノードが含まれています。
* `page.complexity.high`：ページに、レンダリングパフォーマンスに影響する可能性のあるきわめて多くのノードが含まれています。

## 考えられる影響およびリスク {#implications-and-risks}

* ページに含まれる多数のノードが、レンダリングパフォーマンスに影響を及ぼす可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、コンテンツ構造を確認して、ページの複雑さを軽減することです。 これにより、ページのレンダリングパフォーマンスを向上できます。 ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 次のアクションを実行して、ページ内のノードの合計数を減らします。
   * 不要なコンテナがないことを確認します。
   * コンテナを減らしてもレイアウトが同じになるかどうかをテストします。
   * ページのコンテンツを簡素化します。
   * ノード構造の深さを減らします。
   * 簡素化のために、内部のエクスペリエンスフラグメントをリファクタリングします。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
