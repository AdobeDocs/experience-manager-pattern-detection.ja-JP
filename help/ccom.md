---
title: CCOM
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: ht
source-wordcount: '201'
ht-degree: 100%

---


# CCOM {#ccom}

カスタムコンポーネント

## 背景 {#background}

`CCOM` は、AEM にインストールされているカスタムコンポーネントを識別します。この情報は、ベストプラクティスの評価を目的として提供されます。

このコードのサブタイプは、コンポーネントのカテゴリの識別に使用されます。

* `custom.core`：コンポーネントのスーパータイプチェーン内のスーパータイプには「core/wcm/components/」が含まれ、コアコンポーネントから継承していることを示します。
* `custom.foundation`：コンポーネントのスーパータイプチェーン内のスーパータイプには「core/wcm/components/」が含まれ、コアコンポーネントから継承していることを示します。
* `custom.overlay.foundation`：コンポーネントパスには「wcm/foundation/components/」または「foundation/components/」が含まれ、基盤コンポーネントとオーバーレイすることを示します。
* `custom`：カスタムコンポーネントでは、コアコンポーネントまたは基盤コンポーネントの継承、オーバーレイは行われません。

## 可能性のある影響およびリスク {#implications-and-risks}

* ベストプラクティスは、カスタムコンポーネントの数を最小限に抑え、コアコンポーネントを活用し、スタイルシステムでコアコンポーネントを使用することにより、技術的負担を低減することです。

## 可能な解決策 {#solutions}

* コアコンポーネントの詳細については、「[コアコンポーネントの概要](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=ja)」を参照してください。
* スタイルシステムの詳細については、「[スタイルシステムの使用](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=ja#page-authoring)」を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
