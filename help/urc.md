---
title: URC
description: パターン検出コードのヘルプページ
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
translation-type: ht
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: ht
source-wordcount: '319'
ht-degree: 100%

---

# URC {#urc}

サポートされていない実行モードの設定

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="サポートされていない実行モードの設定"
>abstract="URC は、AEM as a Cloud Service でサポートされていない実行モード名に基づく設定の使用状況を識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja#custom-runmodes" text="サポートされている実行モード"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=ja#runmodes" text="実行モード"

`URC` は、AEM as a Cloud Service でサポートされていない実行モード名に基づく設定の使用状況を識別します。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、アプリケーションで使用されているすべての実行モードがサポートされているかどうかを確認し、実行モード解決ガイドラインに確実に従うようにすることをお勧めします。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html?lang=ja#deploying" text="実行モード解決ガイドライン"

* AEM as a Cloud Service では実行モードに使用できる名前は限られています。
* サポートされていない実行モード名に基づく設定は、AEM as a Cloud Service にデプロイしても何も影響がありません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認して、URC 違反を修正して AEM as a Cloud Service に対応させる方法を把握します。また、GitHub の URC 違反例を確認して、AEM as a Cloud Service に準拠するようにカスタム実行モードベースの OSGi 設定を更新する方法も理解します。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC 違反の例 - GitHub"

* この設定の用途を検証し、必要かどうかを判断します。
* 設定名をサポートされている[実行モード名](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja#custom-runmodes)に変更し、「[実行モード解決ガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html?lang=ja#runmode-resolution)」に従ってください。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [URC 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
