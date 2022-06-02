---
title: CDW
description: パターン検出コードのヘルプページ
source-git-commit: 04709ba74eedad903669aae589c605542e1e3b09
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 44%

---

# CDW {#cdw}

カスタムダイアログウィジェット

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_overview"
>title="カスタムダイアログウィジェット"
>abstract="CDW は、AEM as a Cloud Serviceとの互換性を持たせるために更新する必要がある Custom Dialog Widget を識別します。"

`CDW`  カスタムダイアログウィジェットは、カスタム CoralUI およびクラシックダイアログウィジェットを識別します。 AEM as a Cloud Serviceとの互換性を持たせるために、これらを更新する必要があります。

次のようなサブタイプを使用して、各種情報を識別します。

* `custom.coral.widget`:CoralUI 2 または CoralUI 3 に基づいてカスタムダイアログウィジェットを識別します。
* `custom.classic.widget`:ExtJs に基づいてカスタムダイアログウィジェットを識別します。

## 考えられる影響およびリスク {#implications-and-risks}

* AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスは、タッチ対応 UI です。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_guidance"
>title="実装ガイダンス"
>abstract="カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* Custom Classic Dialog Widgets は、ExtJS からに変換する必要があります [CoralUI](https://developer.adobe.com/experience-manager/reference-materials/6-5/coral-ui/coralui3/getting-started.html).
* CoralUI 3 への更新については、カスタム Coral ダイアログウィジェットを評価する必要があります。
* 不明な点や懸念を解決するため、アドビの [Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
