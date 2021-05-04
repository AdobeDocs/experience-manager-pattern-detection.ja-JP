---
title: CCOM
description: パターン検出コードのヘルプページ
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 91%

---

# CCOM {#ccom}

カスタムコンポーネント

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="カスタムコンポーネント"
>abstract="CCOMは、AEMにインストールされているカスタムコンポーネントを識別します。 この情報は、ベストプラクティス評価の目的で提供されます。"

`CCOM` は、AEM にインストールされているカスタムコンポーネントを識別します。この情報は、ベストプラクティスの評価を目的として提供されます。

このコードのサブタイプは、コンポーネントのカテゴリの識別に使用されます。

* `custom.core`：コンポーネントのスーパータイプチェーン内のスーパータイプには「core/wcm/components/」が含まれ、コアコンポーネントから継承していることを示します。
* `custom.foundation`：コンポーネントのスーパータイプチェーン内のスーパータイプには「core/wcm/components/」が含まれ、コアコンポーネントから継承していることを示します。
* `custom.overlay.foundation`：コンポーネントパスには「wcm/foundation/components/」または「foundation/components/」が含まれ、基盤コンポーネントとオーバーレイすることを示します。
* `custom`：カスタムコンポーネントでは、コアコンポーネントまたは基盤コンポーネントの継承、オーバーレイは行われません。

## 可能性のある影響およびリスク {#implications-and-risks}

* ベストプラクティスは、カスタムコンポーネントの数を最小限に抑え、コアコンポーネントを活用し、スタイルシステムでコアコンポーネントを使用することにより、技術的負担を低減することです。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="導入ガイダンス"
>abstract="ベストプラクティスは、カスタムコンポーネントの数を最小限に抑え、コアコンポーネントを活用し、スタイルシステムでコアコンポーネントを使用することにより、技術的負担を低減することです。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="コアコンポーネント"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring" text="スタイルシステム"

* コアコンポーネントの詳細については、「[コアコンポーネントの概要](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=ja)」を参照してください。
* スタイルシステムの詳細については、「[スタイルシステムの使用](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=ja#page-authoring)」を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
