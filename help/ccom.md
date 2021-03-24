---
title: CCOM
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 6%

---


# CCOM {#ccom}

カスタムコンポーネント

## 背景 {#background}

`CCOM` AEMにインストールされているカスタムコンポーネントを識別します。この情報は、ベストプラクティス評価の目的で提供されます。

サブタイプは、次のコードで使用して、コンポーネントのカテゴリを識別します。

* `custom.core`:コンポーネントのスーパータイプチェーン内のスーパータイプには「core/wcm/components/」が含まれ、これはコアコンポーネントから継承していることを示します。
* `custom.foundation`:コンポーネントのスーパータイプチェーン内のスーパータイプには「core/wcm/components/」が含まれ、これはコアコンポーネントから継承していることを示します。
* `custom.overlay.foundation`:コンポーネントパスには「wcm/foundation/components/」または「foundation/components/」が含まれ、基礎コンポーネントがオーバーレイされていることを示します。
* `custom`:カスタムコンポーネントは、コアまたは基礎コンポーネントを継承またはオーバーレイしません。

## 可能性のある影響およびリスク {#implications-and-risks}

* ベストプラクティスは、カスタムコンポーネントの数を最小限に抑え、コアコンポーネントを活用し、スタイルシステムでコアコンポーネントを使用して技術的な債務を削減することです。

## 可能な解決策 {#solutions}

* コアコンポーネントの詳細については、[コアコンポーネントの紹介](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=ja)を参照してください。
* スタイルシステムの詳細については、[スタイルシステムの使用](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring)を参照してください。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
