---
title: DM
description: パターン検出コードがAEM Assets - Dynamic Mediaの使用状況を識別する方法について説明します。
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 52%

---

# DM {#dm}

Dynamic Media

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM コードは、現在の実装における AEM Assets Dynamic Media の使用状況を識別します。Dynamic Media モードは、実行モードで検出されます。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM の開発 - ガイドラインとベストプラクティス"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service の開発ガイドライン"

`DM` （Dynamic Media）AEM Assets Dynamic Mediaが使用されている状況を識別します。 Dynamic Media モードは、実行モードで検出されます。

このコードには次のサブタイプが使用されます。

* `dynamic.media.runmode`：このサブタイプに関連する値が提供される場合は、次のいずれかです。
   * `dynamicmedia`：Dynamic Media - ハイブリッドモード
   * `dynamicmedia_scene7`:Dynamic Media - Scene7 モード

## 可能性のある影響およびリスク {#implications-and-risks}

* `dynamic.media.runmode`
   * アップグレードに伴い Dynamic Media に関連する問題が生じる可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="実装ガイダンス"
>abstract="AEM as a Cloud Serviceは dynamicmedia_scene7 実行モードのみをサポートします。 ヘルプおよび詳しい説明については、現在の設定を確認したうえで、Adobeサポートチームにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media" text="Dynamic Media のセットアップ"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"


* `dynamic.media.runmode`
   * 詳しくは、こちらを参照してください。 [Dynamic Mediaの設定](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media).

* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 詳しい説明や懸念に対処する必要がある場合。
