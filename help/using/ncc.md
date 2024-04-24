---
title: NCC
description: パターン検出コードのヘルプページ
exl-id: 4a374956-c64e-43fc-8279-ed25f6ed5cb0
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 56%

---

# NCC {#ncc}

互換性のない変更

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_overview"
>title="互換性のない変更"
>abstract="NCC は、一部の JCR ノードやバンドルが、互換性のない形で変更される状況を表します。アップグレードの前に、お客様がこの変更について認識していないことがあります。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主要な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="リリースノート - AEM as a Cloud Service"

`NCC`  一部の JCR ノードやバンドルが、互換性のない方法で変更される状況を表します。 アップグレードの前に、お客様がこの変更について認識していないことがあります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 下位互換性のない変更を使用したいずれかのコンポーネントに依存する機能は、動作しなくなったり、問題を正しく解決できない可能性があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しなくなる場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、カスタムコードを確認し、必ず、互換性のある Sling コンポーネントのみをオーバーレイまたは参照するようにします。 ヘルプまたは詳しい説明については、Adobeサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/overlays#platform" text="オーバーレイ"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 下位互換性のある Sling コンポーネントのみをオーバーレイまたは参照します。
* AEM のアップグレード後、`/libs` またはバンドルに由来するリソースを適合させること検討してください。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
