---
title: URS
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 5a83dd8d08da974a5d775032b8dbea2593be9d15
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 2%

---


# URS {#urs}

サポートされていないリポジトリ構造

## 背景 {#background}

`URS` サポートされていないリポジトリ構造のケースを示します。AEM 6.4から、リポジトリコンテンツの再構築に関するガイドラインが提供されています。 AEM製品コードと顧客コードの階層を明確に説明し、それらの間の競合を避けることで、次の高レベルの規則に従って、`/etc`からリポジトリ内の他のフォルダにコンテンツが再構成されています。

* AEM製品コードは常に`/libs`に配置されます。これは、カスタムコードで上書きしないでください。カスタムコードは`/apps`、`/content`、および`/conf`に配置してください。
* AEMをCloud Serviceとして使用する場合は、次のガイドラインに従うことを強くお勧めします。

サブタイプは、対処する必要がある特定のタイプのリポジトリの問題を識別するために使用されます。
* `clientlibs.location`:パスで参照するクライアントライブラリ `/etc` です。
* `file.location`:の下のファイル `/etc` は、インストール後に変更されています。
* `node.location`:インストール後に変更 `/etc` された、下のノード。
* `workflow.location`:の下にあるワークフローモデルまたはランチャー `/etc/workflow`。
* `package.structure`:可変コンテンツと不変コンテンツの両方を含むパッケージです。

## 可能性のある影響およびリスク {#implications-and-risks}

* 古いパスに依存するカスタムコードは、意図しない動作の原因となり、製品の機能に影響を与える可能性があります。
* 可変コンテンツと不変コンテンツの両方を含むパッケージは、展開中に問題を引き起こす可能性があります。

## 可能な解決策 {#solutions}

* AEMをCloud Serviceとして使用するための準備手順については、[リポジトリの再構築](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html)を参照してください。
* リポジトリの可変領域と不変領域の詳細については、[AEMプロジェクト構造](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)も参照してください。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
* [Repository Modenizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools)を活用して、Cloud ServiceとしてAdobe Experience Managerに定義されたプロジェクト構造と互換性を持つように、コンテンツとコードを個別のパッケージに分けて、既存のプロジェクトパッケージを再構築します。