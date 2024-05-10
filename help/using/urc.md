---
title: URC
description: パターン検出コードのヘルプページ。
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '261'
ht-degree: 100%

---

# URC {#urc}

サポートされていない実行モードの設定

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="サポートされていない実行モードの設定"
>abstract="URC は、AEM as a Cloud Service でサポートされていない実行モード名に基づく設定の使用状況を識別します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes" text="サポートされている実行モード"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/deploying/overview#runmodes" text="実行モード"

`URC` は、AEM as a Cloud Service でサポートされていない実行モード名に基づく設定の使用状況を識別します。

## 考えられる影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、アプリケーションで使用されているすべての実行モードがサポートされているかどうかを確認し、実行モード解決ガイドラインに確実に従うようにすることをお勧めします。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#deploying" text="実行モード解決ガイドライン"

* AEM as a Cloud Service で様々なモードを実行するために使用できる名前のセットは制限されています。
* サポートされていない実行モード名に基づく設定は、AEM as a Cloud Service にデプロイしても影響がありません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認して、URC 違反を修正して AEM as a Cloud Service に対応させる方法を把握します。また、GitHub の URC 違反例を確認して、AEM as a Cloud Service に準拠するようにカスタム実行モードベースの OSGi 設定を更新する方法も理解します。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC 違反の例 - GitHub"

* この設定の用途を検証し、必要かどうかを判断します。
* サポートされている[実行モード名](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes)のいずれかを使用して設定の名前を変更し、[実行モード解決ガイドライン](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#runmode-resolution)に従います。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc) プロジェクトを確認し、[URC 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)をどのように修正できるかおよびどのように AEM as a Cloud Service との互換性を維持できるかを理解します。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
