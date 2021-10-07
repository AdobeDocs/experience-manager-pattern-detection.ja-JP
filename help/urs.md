---
title: URS
description: パターン検出コードのヘルプページ
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: 9d92254d2f5e84f833ed6926a0ae69b334730d21
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 87%

---

# URS {#urs}

サポートされていないリポジトリー構造

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="サポートされていないリポジトリー構造"
>abstract="URS は、サポートされないリポジトリ構造とノード特性の事例を特定します。 これは、AEM 製品コードと顧客コードの競合、コンテンツを /etc からリポジトリー内の他のフォルダーに再構成することなどを避けるための情報を示します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html" text="リポジトリーの再構築"

## 背景 {#background}

`URS` は、サポートされないリポジトリ構造とノード特性のケースを示します。AEM 6.4 以降、リポジトリーコンテンツの再構築に関するガイドラインが提供されています。AEM 製品コードとカスタムコードの階層を明確に区別して競合を避けることにより、次の高水準ルールに準拠して、コンテンツは `/etc` からリポジトリー内の別のフォルダーに再構築されます。

* AEM製品コードは常に `/libs` に配置されます。カスタムコードで上書きしてはいけません。
* カスタムコードは、`/apps`、`/content` および `/conf` に配置する必要があります。
* AEM as a Cloud Serviceでは、長いノード名（150 バイトを超える）はサポートされません。
* AEM as a Cloud Service では、これらのガイドラインに準拠することを強くお勧めします。

サブタイプを使用して、対処が必要なリポジトリーの問題を識別します。
* `clientlibs.location`：パスで `/etc` を参照するクライアントライブラリ。
* `file.location`：インストールの後で変更された `/etc` 下のファイル。
* `node.location`：インストールの後で変更された `/etc` 下のノード。
* `workflow.location`：`/etc/workflow` 下のワークフローモデル、またはランチャー。
* `package.structure`：可変コンテンツと不変コンテンツを両方含むパッケージ
* `node.name.length`：サポートされていない長さのノード名。

## 可能性のある影響およびリスク {#implications-and-risks}

* 古いパスに依存するカスタムコードは、意図しない動作をして製品の機能に影響を与えることがあります。
* パッケージ中に可変コンテンツと不変コンテンツの両方が含まれていると、デプロイメント中に問題が起こることがあります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、コードプロジェクトをレビューして、コードが AEM プロジェクト構造のガイドラインに従っていることを確認し、AEM as a Cloud Service で意図しない動作を引き起こす可能性のある古いリポジトリーパスやサポートされていないリポジトリーパスに基づいたコードを避けることをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html" text="AEM プロジェクト構造ガイドライン"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* AEM as a Cloud Service を準備する際のガイダンスとして、[リポジトリーの再構築](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html?lang=ja)を参照してください。
* リポジトリーの可変領域と不変領域の詳細については、[AEM プロジェクト構造](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja)も参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
* [Repository Modernizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html?lang=ja#refactoring-tools) を利用して、コンテンツとコードを個別のパッケージに分離して既存のプロジェクトパッケージを再構築することで、Adobe Experience Manager as a Cloud Service で定義されたプロジェクト構造と互換性を持たせることが出来ます。
