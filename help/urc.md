---
title: URC
description: パターン検出コードのヘルプページ
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 63%

---

# URC {#urc}

サポートされていない実行モードの設定

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="サポートされていない実行モードの設定"
>abstract="URCは、AEMでCloud Serviceとしてサポートされていないランモード名に基づく設定の使用を識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes" text="サポートされる実行モード"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes" text="実行モード"

`URC` は、AEM as a Cloud Service でサポートされていない実行モード名に基づく設定の使用状況を識別します。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="導入ガイダンス"
>abstract="ベストプラクティスは、アプリケーションで使用されるすべての実行モードがサポートされているかどうかを確認し、実行モード解決のガイドラインに従うことです"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#deploying" text="Runmode解決のガイドライン"

* AEM as a Cloud Service では実行モードに使用できる名前は限られています。
* サポートされていない実行モード名に基づく設定は、AEM as a Cloud Service にデプロイしても何も影響がありません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="ツールとリソース"
>abstract="WKND-legacyプロジェクトを見直し、URC違反をAEMCloud Serviceと互換性のあるものにする方法を理解します。 また、GithubでのURC違反の例を確認し、カスタム実行モードベースのOSGi設定を、AEMをCloud Serviceとして使用して更新する方法を理解してください。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND — レガシープロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC違反の例 — Github"

* この設定の用途を検証し、必要かどうかを判断します。
* 設定名をサポートされている[実行モード名](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja#custom-runmodes)に変更し、「[実行モード解決ガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html?lang=ja#runmode-resolution)」に従ってください。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [URC 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
