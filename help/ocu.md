---
title: OCU
description: パターン検出コードのヘルプページ
exl-id: cb28c727-415d-436c-ab74-cf7f1f34f7c7
translation-type: tm+mt
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 73%

---

# OCU {#ocu}

古いコードの使用

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_overview"
>title="古いコードの使用"
>abstract="OCUは、SlingやAEMコンポーネント、API OSGiエクスポートなど、一部のJCRノードが互換性のない方法で変更または削除される状況を識別します。 アップグレードの前に、お客様がこの変更について認識していないことがあります。その結果、互換性のないバージョンにアップグレードされたり、まったく使用できなくなったりする可能性があります。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja" text="主な変更点 — AEMをCloud Serviceとして"

`OCU` は、Sling や AEM のコンポーネント、または API OSGi のエクスポートなどの一部の JCR ノードが、互換性のない方法で変更または削除される状況を識別します。アップグレードの前に、お客様がこの変更について認識していないことがあります。その結果、互換性のないバージョンにアップグレードされたり、まったく使用できなくなったりする可能性があります。

古いバージョンはデフォルトではインストールされていないので、お客様のアプリケーションが正常に動作しない場合があります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 非推奨（廃止予定）のコンポーネントまたは API を使用するコンポーネントに依存する機能が破損して、アップグレード後に正しく解決されない場合があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しない場合やアクティブにならない場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_guidance"
>title="導入ガイダンス"
>abstract="ベストプラクティスは、最新バージョンのAEMコンポーネントまたはAPIを使用するように顧客コードを確認し、適応させることです。 ヘルプと説明については、Adobeサポートにお問い合わせください。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience ManagerSDK API"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* 短期的：互換パッケージのインストールが役立つ場合があります。
* 長期的：最新バージョンの AEM コンポーネントまたは API に合わせてカスタムコードを適合させます。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
