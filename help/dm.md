---
title: DM
description: パターン検出コードのヘルプページ
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 100%

---

# DM {#dm}

Dynamic Media

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM コードは、現在の実装における AEM Assets Dynamic Media の使用状況を識別します。Dynamic Media モードは、実行モードで検出されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html?lang=ja" text="AEM の開発 - ガイドラインとベストプラクティス"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja" text="AEM as a Cloud Service の開発ガイドライン"

`DM` は、AEM Assets Dynamic Media が使用されている状況を識別します。Dynamic Media モードは、実行モードで検出されます。

このコードには次のサブタイプが使用されます。

* `dynamic.media.runmode`：このサブタイプに関連する値が提供される場合は、次のいずれかです。
   * `dynamicmedia`：Dynamic Media - ハイブリッドモード
   * `dynamicmedia_scene7`：Dynamic Media - Scene7 モード

## 考えられる影響およびリスク {#implications-and-risks}

* `dynamic.media.runmode`
   * アップグレードに伴い Dynamic Media に関連する問題が生じる可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="実装ガイダンス"
>abstract="AEM as a Cloud Service では dynamicmedia_scene7 実行モードのみサポートしています。ヘルプおよび詳しい説明については、現在の設定を確認したうえで、アドビサポートチームにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html?lang=ja" text="Dynamic Media のセットアップ"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"


* `dynamic.media.runmode`
   * 詳細については、[Dynamic Media の設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html?lang=ja)を参照してください。

* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
