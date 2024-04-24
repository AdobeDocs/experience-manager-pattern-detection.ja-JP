---
title: URC
description: パターン検出コードのヘルプページ
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 24%

---

# URC {#urc}

サポートされていない実行モード設定

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="サポートされていない実行モードの設定"
>abstract="URC は、AEM as a Cloud Serviceでサポートされていない実行モード名に基づく設定の使用状況を特定します。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes" text="サポートされている実行モード"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/overview#runmodes" text="実行モード"

`URC`  AEM as a Cloud Serviceでサポートされていない実行モード名に基づく設定の使用状況を特定します。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、アプリケーションで使用されているすべての実行モードがサポートされているかどうかを確認し、実行モード解決ガイドラインに従うことです。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#deploying" text="実行モード解決ガイドライン"

* AEM as a Cloud Serviceで様々なモードを実行する際に使用できる名前のセットは限られています。
* サポートされていない実行モード名に基づく設定は、AEM as a Cloud Serviceにデプロイしても効果はありません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認して、URC 違反を修正して AEM as a Cloud Service に対応させる方法を把握します。また、GitHub の URC 違反例を確認して、AEM as a Cloud Serviceに準拠するようにカスタム実行モードベースの OSGi 設定を更新する方法も理解します。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC 違反の例 – GitHub"

* この設定の使用を確認して、必要かどうかを判断できるようにします。
* サポートされているのいずれかを使用して、設定の名前を変更します [実行モード名](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes) およびフォロー [実行モード解決ガイドライン](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#runmode-resolution).
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [URC 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)を修正および変更する方法を確認します。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
