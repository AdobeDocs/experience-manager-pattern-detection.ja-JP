---
title: CDW
description: パターン検出コードのヘルプページ。
exl-id: a9e9dae8-0aa2-4679-a3c1-418cab01cfda
source-git-commit: d1c652a8a45a081661ffe4443f85fcc932947541
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

---

# CDW {#cdw}

カスタムダイアログウィジェット

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_overview"
>title="カスタムダイアログウィジェット"
>abstract="CDW は、AEM as a Cloud Service との互換性を確保するために更新が必要なカスタムダイアログウィジェットを識別します。"

`CDW`（`Custom Dialog Widgets`）は、カスタムクラシックダイアログウィジェットを識別します。これらのウィジェットは、AEM as a Cloud Service との互換性を持つために更新する必要があります。

次のようなサブタイプを使用して、情報を識別します。

* `custom.classic.widget`：ExtJS に基づくカスタムダイアログウィジェットを識別します。

## 考えられる影響およびリスク {#implications-and-risks}

* AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスは、タッチ対応 UI です。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_guidance"
>title="実装ガイダンス"
>abstract="カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* カスタムクラシックダイアログウィジェットは、ExtJS から [CoralUI](https://developer.adobe.com/experience-manager/reference-materials/6-5/coral-ui/coralui3/getting-started.html) に変換する必要があります。
* 詳しい説明や懸念事項の対応については、[Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
