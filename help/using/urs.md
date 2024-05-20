---
title: URS
description: パターン検出コードのヘルプページ。
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 100%

---

# URS {#urs}

サポートされていないリポジトリー構造

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="サポートされていないリポジトリー構造"
>abstract="URS はサポートされていないリポジトリー構造とノード文字のケースを特定します。これは、AEM 製品コードと顧客コードの競合や、コンテンツを /etc からリポジトリー内の他のフォルダーに再構成することなどを避けるための情報を示します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/restructuring/repository-restructuring" text="リポジトリーの再構築"

## 背景 {#background}

`URS` は、サポートされていないリポジトリ構造とノード特性のケースを識別します。AEM 6.4 以降、リポジトリーコンテンツの再構築に関するガイドラインが提供されています。AEM 製品コードとカスタムコードの階層を明確に区別して競合を避けることにより、次の高水準ルールに準拠して、コンテンツは `/etc` からリポジトリー内の別のフォルダーに再構築されます。

* AEM 製品コードは必ず `/libs` 下に配置されます。このフォルダーをカスタムコードで上書きしないようにしてください。
* カスタムコードは `/apps`、`/content` および `/conf` 下に配置する必要があります。
* AEM as a Cloud Service では、これらのガイドラインに準拠することを強くお勧めします。

サブタイプを使用して、対処が必要なリポジトリーの問題を識別します。

* `clientlibs.location`：パスで `/etc` を参照するクライアントライブラリ。
* `file.location`：インストールの後で変更された `/etc` 下のファイル。
* `node.location`：インストールの後で変更された `/etc` 下のノード。
* `workflow.location`：`/etc/workflow` 下のワークフローモデル、またはランチャー。
* `package.structure`：可変コンテンツと不変コンテンツを両方含むパッケージ
* `node.size`：サポートされていないサイズのノード。

## 考えられる影響およびリスク {#implications-and-risks}

* 古いパスに依存するカスタムコードは、意図しない動作をして製品の機能に影響を与えることがあります。
* パッケージに可変コンテンツと不変コンテンツの両方が含まれると、デプロイメント中に問題を引き起こす可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、コードプロジェクトを確認することです。AEM プロジェクト構造のガイドラインに従っていることを確認し、AEM as a Cloud Service で意図しない動作を引き起こす可能性のある古いリポジトリパスやサポートされていないリポジトリパスに基づいたコードを避けます。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure" text="AEM プロジェクト構造ガイドライン"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* AEM as a Cloud Service を準備する際のガイダンスについては、[リポジトリの再構築](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/restructuring/repository-restructuring)を参照してください。
* また、リポジトリの可変領域と不変領域について詳しくは、[AEM プロジェクトの構造](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure)も参照してください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
* [Repository Modernizer](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/repo-modernizer#refactoring-tools) を使用して、コンテンツとコードを個別のパッケージに分離して既存のプロジェクトパッケージを再構築することで、Adobe Experience Manager as a Cloud Service で定義されたプロジェクト構造と互換性を持たせることができます。
