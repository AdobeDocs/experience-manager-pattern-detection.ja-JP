---
title: NBCC
description: パターン検出コードのヘルプページ
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
source-git-commit: fdc3e8bdef27de971743a9ecb04d3912cf8e60ad
workflow-type: ht
source-wordcount: '233'
ht-degree: 100%

---

# NBCC {#nbcc}

非推奨（廃止予定）：下位互換性のない変更（NCC（互換性のない変更）に置き換え）

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="後方互換性のない変更"
>abstract="NBCC は、一部の JCR ノードやバンドルが、互換性のない方法で変更されている状況を識別します。アップグレードの前に、お客様がこの変更について認識していないことがあります。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja" text="主要な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="リリースノート - AEM as a Cloud Service"

`NBCC` は、一部の JCR ノードやバンドルが、互換性のない方法で変更される状況を識別します。アップグレードの前に、お客様がこの変更について認識していないことがあります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 後方互換性のない変更を使用したいずれかのコンポーネントに依存する機能は、破損したり、正しく解決されない可能性があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しなくなる場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、カスタムコードを確認し、下位互換性のある Sling コンポーネントのみオーバーレイまたは参照されるようにすることをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html?lang=ja#platform" text="オーバーレイ"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 後方互換性のある Sling コンポーネントだけをオーバーレイまたは参照の対象とします。
* AEM のアップグレード後、`/libs` またはバンドルに由来するリソースを適合させること検討してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
