---
title: INST
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: ht
source-wordcount: '315'
ht-degree: 100%

---


# INST {#inst}

インストール済みアーティファクト

## 背景 {#background}

`INST` は、お客様によって AEM にインストールされたカスタムパッケージおよびサードパーティ製パッケージのバンドルを識別します。こうした情報は、システムの状態やアップグレード作業の全般的な範囲を把握するために報告されます。

1 つのパッケージについて複数のバージョンがインストールされている場合は、最新バージョンだけが報告されます。

検出されたパッケージとバンドルは、必ずしも AEM as a Cloud Service に最適化されているわけではありません。サードパーティ製パッケージと AEM as a Cloud Service との互換性は、パッケージの作成者またはアドビに確認する必要があります。

サブタイプを使用して、各種情報を識別します。

* `custom.bundle`：AEM にインストールされたバンドル
* `custom.package`：AEM にインストールされたパッケージ

## 可能性のある影響およびリスク {#implications-and-risks}

* CRX パッケージマネージャーを使用してサードパーティ製パッケージを AEM as a Cloud Service にインストールすることはできません。
* サードパーティ製パッケージに依存するアプリケーションは、AEM as a Cloud Service での動作に合わせて正しくデプロイしない限り、期待通り動作しないことがあります。
* サードパーティベンダーのパッケージは、AEM as a Cloud Service 用に最適化されていないと、意図しない動作をする可能性があります。

## 可能な解決策 {#solutions}

* サードパーティ製パッケージは、Cloud Manager の[デプロイメントプロセス](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html?lang=ja#deployment-process)を使用して、プロジェクトの一部として AEM にデプロイする必要があります。
* AEM as a Cloud Service のプロジェクトに[サードパーティ製パッケージを組み込む](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#embedding-3rd-party-packages)方法を確認します。
* サードパーティ製パッケージは、AEM as a Cloud Service の[開発](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja)および[パッケージ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html?lang=ja)ガイドラインに準拠する必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [INST 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
