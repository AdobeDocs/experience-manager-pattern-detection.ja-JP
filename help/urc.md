---
title: URC
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: ht
source-wordcount: '176'
ht-degree: 100%

---


# URC {#urc}

サポートされていない実行モードの設定

## 背景 {#background}

`URC` は、AEM as a Cloud Service でサポートされていない実行モード名に基づく設定の使用状況を識別します。

## 可能性のある影響およびリスク {#implications-and-risks}

* AEM as a Cloud Service では実行モードに使用できる名前は限られています。
* サポートされていない実行モード名に基づく設定は、AEM as a Cloud Service にデプロイしても何も影響がありません。

## 可能な解決策 {#solutions}

* この設定の用途を検証し、必要かどうかを判断します。
* 設定名をサポートされている[実行モード名](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja#custom-runmodes)に変更し、「[実行モード解決ガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html?lang=ja#runmode-resolution)」に従ってください。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [URC 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
