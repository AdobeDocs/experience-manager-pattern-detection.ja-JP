---
title: CCOM
description: パターン検出コードのヘルプページ
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 70%

---

# CCOM {#ccom}

カスタムコンポーネント

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="カスタムコンポーネント"
>abstract="CCOM は、AEM にインストールされているカスタムコンポーネントを識別します。この情報は、ベストプラクティスの評価を目的として提供されます。"

CCOM は、AEM にインストールされているカスタムコンポーネントを識別します。この情報は、ベストプラクティスの評価を目的として提供されます。

このコードのサブタイプは、コンポーネントのカテゴリの識別に使用されます。

* `custom.core`：コンポーネントのスーパータイプチェーン内のスーパータイプには「core/wcm/components/」が含まれ、コアコンポーネントから継承していることを示します。
* `custom.foundation`：コンポーネントのスーパータイプチェーン内のスーパータイプには「core/wcm/components/」が含まれ、コアコンポーネントから継承していることを示します。
* `custom.overlay.foundation`：コンポーネントパスには「wcm/foundation/components/」または「foundation/components/」が含まれ、基盤コンポーネントとオーバーレイすることを示します。
* `custom`：カスタムコンポーネントでは、コアコンポーネントまたは基盤コンポーネントの継承、オーバーレイは行われません。

## 可能性のある影響およびリスク {#implications-and-risks}

* ベストプラクティスは、カスタムコンポーネントの数を最小限に抑え、コアコンポーネントを使用し、スタイルシステムでコアコンポーネントを使用することにより、技術的負担を軽減することです。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、カスタムコンポーネントの数を最小限に抑え、コアコンポーネントを使用し、スタイルシステムでコアコンポーネントを使用することにより、技術的負担を軽減することです。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-core-components/using/introduction" text="コアコンポーネント"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring" text="スタイルシステム"

* コアコンポーネントの詳細については、「[コアコンポーネントの概要](https://experienceleague.adobe.com/ja/docs/experience-manager-core-components/using/introduction)」を参照してください。
* スタイルシステムの詳細については、「[スタイルシステムの使用](https://experienceleague.adobe.com/en/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring)」を参照してください。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
