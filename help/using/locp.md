---
title: LOCP
description: パターン検出コードのヘルプページ。
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '169'
ht-degree: 100%

---

# LOCP {#locp}

/libs カスタムパッケージの上書き

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs カスタムパッケージの上書き"
>abstract="LOCP は、コンテンツを /libs に配信するカスタムパッケージを検出し識別します。これは、ACL の場合を除き、アンチパターンです。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="持続可能なアップグレード"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Sling Resource Merger"

`LOCP` は、コンテンツを `/libs` に配信するカスタムパッケージを検出し識別します。これは、ACL の場合を除き、アンチパターンです。

## 考えられる影響およびリスク {#implications-and-risks}

* カスタムコードは、CFP、SP または主要な AEM アップグレードで削除されたり置き換えられたりする場合があります。
* 新しいコンテンツが適切にインストールされない場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="実装ガイダンス"
>abstract="カスタムコードおよびパッケージを確認して、コンテンツが /libs に配信されているかどうかを特定し、/apps 下のコンテンツを利用しオーバーレイするようにリファクタリングして、AEM as a Cloud Service に対応させてください。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="オーバーレイ"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* カスタムパッケージでは、コンテンツは、`/libs` ではなく `/apps` にデプロイする必要があります。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
