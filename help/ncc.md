---
title: NCC
description: パターン検出コードのヘルプページ
source-git-commit: fdc3e8bdef27de971743a9ecb04d3912cf8e60ad
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 70%

---

# NCC {#ncc}

互換性のない変更

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_overview"
>title="互換性のない変更"
>abstract="NCC は、一部の JCR ノードまたはバンドルが互換性のない方法で変更された状況を識別します。 アップグレードの前に、お客様がこの変更について認識していないことがあります。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja" text="主要な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="リリースノート - AEM as a Cloud Service"

`NCC` は、一部の JCR ノードやバンドルが、互換性のない方法で変更される状況を識別します。アップグレードの前に、お客様がこの変更について認識していないことがあります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 互換性のない変更を使用するコンポーネントに依存する機能は壊れ、正しく解決されない場合があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しなくなる場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、カスタムコードを確認し、互換性のある Sling コンポーネントのみがオーバーレイまたは参照されるようにすることです。 ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html?lang=ja#platform" text="オーバーレイ"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 互換性のある Sling コンポーネントのみをオーバーレイまたは参照します。
* AEM のアップグレード後、`/libs` またはバンドルに由来するリソースを適合させること検討してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
