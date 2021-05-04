---
title: LOCP
description: パターン検出コードのヘルプページ
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 56%

---

# LOCP {#locp}

/libs カスタムパッケージの上書き

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs カスタムパッケージの上書き"
>abstract="LOCPは、アンチパターン（ACLを除く）の/libsにコンテンツを配信するカスタムパッケージの検出を識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html?lang=ja" text="持続可能なアップグレード"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling Resource Merger"

`LOCP` は、コンテンツを `/libs` に配信するカスタムパッケージを検出し識別します。これは、ACL の場合を除き、アンチパターンです。

## 可能性のある影響およびリスク {#implications-and-risks}

* カスタムコードは、CFP、SP または主要な AEM アップグレードで削除されたり置き換えられたりする場合があります。
* 新しいコンテンツが適切にインストールされない場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="導入ガイダンス"
>abstract="お客様は、カスタムコードとパッケージを確認して、コンテンツが/libsに配信されているかどうかを確認し、/appsの下のコンテンツをオーバーレイして、AEMとの互換性を持たせるようにリファクタリングする必要があります。 ヘルプと説明を求めるAdobeサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="オーバーレイ"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* カスタムパッケージでは、コンテンツは、`/libs` ではなく `/apps` にデプロイする必要があります。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
