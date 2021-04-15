---
title: PCX
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: ht
source-wordcount: '149'
ht-degree: 100%

---


# PCX {#pcx}

ページの複雑さ

## 背景 {#background}

`PCX` は、構造中に多数のノードを含むページを識別します。

サブタイプを使用して、各種情報を識別します。

* `page.complexity.medium`：ページに、レンダリングパフォーマンスに影響する可能性のある比較的多くのノードが含まれています。
* `page.complexity.high`：ページに、レンダリングパフォーマンスに影響する可能性のあるきわめて多くのノードが含まれています。

## 可能性のある影響およびリスク {#implications-and-risks}

* ページに含まれる多数のノードが、レンダリングパフォーマンスに影響を及ぼす可能性があります。

## 可能な解決策 {#solutions}

* ページに含まれる総ノード数を減らすために次の手順を実行します。
   * 不要なコンテナがないことを確認します。
   * コンテナを減らしてもレイアウトが同じになるかどうかをテストします。
   * ページのコンテンツを簡素化します。
   * ノード構造の深さを減らします。
   * 簡素化のために、内部のエクスペリエンスフラグメントをリファクタリングします。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
