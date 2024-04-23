---
title: LOCP
description: パターン検出コードのヘルプページ…
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 57%

---

# LOCP {#locp}

/libs カスタムパッケージの上書き

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs カスタムパッケージの上書き"
>abstract="LOCP は、コンテンツを /libs に配信するカスタムパッケージを検出し識別します。これは、ACL の場合を除き、アンチパターンです。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="持続可能なアップグレード"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Sling Resource Merger"

LOCP は、コンテンツを配信するカスタムパッケージの検出を識別します `/libs`：アンチパターンです（ACL の場合を除く）。

## 可能性のある影響およびリスク {#implications-and-risks}

* CFP、SP、または大規模なAEM アップグレードの際に、カスタマーコードが削除または置き換えられる場合があります。
* 新しいコンテンツが正しくインストールされない場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="実装ガイダンス"
>abstract="カスタムコードおよびパッケージを確認して、コンテンツが /libs に配信されているかどうかを特定し、/apps 下のコンテンツを利用しオーバーレイするようにリファクタリングして、AEM as a Cloud Service に対応させてください。ヘルプまたは詳しい説明については、Adobeサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="オーバーレイ"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* カスタムパッケージでは、コンテンツは、`/libs` ではなく `/apps` にデプロイする必要があります。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 詳しい説明や懸念に対処する必要がある場合。
