---
title: PCX
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 4%

---


# PCX {#pcx}

ページの複雑さ

## 背景 {#background}

`PCX` 構造内に多数のノードを含むページを識別します。

サブタイプは、異なる種類の情報を識別するために使用されます。

* `page.complexity.medium`:ページには、レンダリングのパフォーマンスに影響を与える可能性のある、ある程度高い数のノードが含まれています。
* `page.complexity.high`:ページには非常に多くのノードが含まれており、レンダリングのパフォーマンスに影響を与える可能性があります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 1つのページ内に大量のノードを配置すると、そのノードのレンダリングパフォーマンスに影響を与える場合があります。

## 可能な解決策 {#solutions}

* ページ内のノードの合計数を減らす手順を実行します。次に例を示します。
   * 不要なコンテナがないことを確認します。
   * コンテナ数を減らして同じレイアウトを実現できるかどうかをテストします。
   * ページのコンテンツを簡略化します。
   * ノード構造の深さを減らします。
   * 含まれる任意のエクスペリエンスフラグメントをリファクタリングして、簡単にします。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
