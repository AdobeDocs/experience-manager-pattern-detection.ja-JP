---
title: NBCC
description: パターン検出コードのヘルプページ。
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 67%

---

# NBCC {#nbcc}

非推奨（廃止予定）：下位互換性のない変更（NCC（互換性のない変更）に置き換え）

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="後方互換性のない変更"
>abstract="NBCC は、一部の JCR ノードやバンドルが、互換性のない方法で変更されている状況を特定します。 顧客はアップグレード前に、この変更について認識していないことがあります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="リリースノート - AEM as a Cloud Service"

`NBCC`  一部の JCR ノードやバンドルが、互換性のない方法で変更される状況を識別します。 顧客はアップグレード前に、この変更について認識していないことがあります。

## 考えられる影響およびリスク {#implications-and-risks}

* 下位互換性のない変更を使用するいずれかのコンポーネントに依存する機能は、動作しなくなったり、正しく解決されない可能性があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しなくなる場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、カスタムコードを確認し、後方互換性のある Sling コンポーネントのみオーバーレイまたは参照されるようにすることをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/platform/overlays#platform" text="オーバーレイ"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 後方互換性のある Sling コンポーネントだけをオーバーレイまたは参照の対象とします。
* から得られるリソースの適応を検討する `/libs` AEMのアップグレード後のまたはバンドル。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
