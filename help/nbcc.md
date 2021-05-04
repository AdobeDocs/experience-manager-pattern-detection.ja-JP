---
title: NBCC
description: パターン検出コードのヘルプページ
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 69%

---

# NBCC {#nbcc}

後方互換性のない変更

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="後方互換性のない変更"
>abstract="NBCCは、一部のJCRノードまたはバンドルが互換性のない方法で変更される状況を識別します。 アップグレードの前に、お客様がこの変更について認識していないことがあります。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja" text="主な変更点 — AEMをCloud Serviceとして"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="リリースノート —Cloud ServiceとしてのAEM"

`NBCC` は、一部の JCR ノードやバンドルが、互換性のない方法で変更される状況を識別します。アップグレードの前に、お客様がこの変更について認識していないことがあります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 後方互換性のない変更を使用したいずれかのコンポーネントに依存する機能は、破損したり、正しく解決されない可能性があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しなくなる場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="導入ガイダンス"
>abstract="ベストプラクティスは、カスタムコードを確認し、下位互換性のあるSlingコンポーネントのみがオーバーレイまたは参照されるようにすることです。 ヘルプと説明を求めるAdobeサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="オーバーレイ"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* 後方互換性のある Sling コンポーネントだけをオーバーレイまたは参照の対象とします。
* AEM のアップグレード後、`/libs` またはバンドルに由来するリソースを適合させること検討してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
