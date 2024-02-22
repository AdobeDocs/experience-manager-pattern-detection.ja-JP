---
title: INST
description: パターン検出コードのヘルプページ
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '449'
ht-degree: 100%

---

# INST {#inst}

インストール済みアーティファクト

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="インストール済みアーティファクト"
>abstract="INST は、ユーザーによって AEM にインストールされたカスタムおよびサードパーティ製のパッケージおよびバンドルを識別します。こうした情報は、システムの状態やアップグレード作業の全般的な範囲を把握するために報告されます。サードパーティ製パッケージは、AEM as a Cloud Service の開発およびパッケージガイドラインに準拠する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja" text="開発ガイドライン - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html?lang=ja" text="パッケージガイドライン - AEM as a Cloud Service"

`INST` は、お客様によって AEM にインストールされたカスタムパッケージおよびサードパーティ製パッケージのバンドルを識別します。こうした情報は、システムの状態やアップグレード作業の全般的な範囲を把握するために報告されます。

1 つのパッケージについて複数のバージョンがインストールされている場合は、最新バージョンだけが報告されます。

検出されたパッケージとバンドルは、必ずしも AEM as a Cloud Service に最適化されているわけではありません。サードパーティ製パッケージと AEM as a Cloud Service の互換性については、パッケージの作成者またはアドビに確認してください。

サブタイプを使用して、各種情報を識別します。

* `custom.bundle`：AEM にインストールされたバンドル
* `custom.package`：AEM にインストールされたパッケージ

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="実装ガイダンス"
>abstract="CRX パッケージマネージャーを使用してサードパーティ製パッケージをインストールすることはできなくなりました。これらのインストール済みアーティファクトを確認し、AEM as a Cloud Service と連携できるように再構成および最適化する必要があります。サードパーティ製パッケージと AEM as a Cloud Service の互換性については、パッケージの作成者またはアドビに確認してください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#embeddeds" text="コンテナパッケージへのサブパッケージの埋め込み"


* CRX パッケージマネージャーを使用してサードパーティ製パッケージを AEM as a Cloud Service にインストールすることはできません。
* サードパーティ製パッケージに依存するアプリケーションは、AEM as a Cloud Service での動作に合わせて正しくデプロイしない限り、期待通り動作しないことがあります。
* サードパーティベンダーのパッケージは、AEM as a Cloud Service 用に最適化されていないと、意図しない動作をする可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認し、INST 違反を修正して AEM as a Cloud Service に対応させる方法を把握します。また、GitHub の INST 違反例を確認し、問題を修正してアーティファクトを AEM as a Cloud Service にデプロイする方法も理解します。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST 違反の例 - GitHub"

* サードパーティ製パッケージは、Cloud Manager の[デプロイメントプロセス](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html?lang=ja#deployment-process)を使用して、プロジェクトの一部として AEM にデプロイする必要があります。
* AEM as a Cloud Service のプロジェクトに[サードパーティ製パッケージを組み込む](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#embedding-3rd-party-packages)方法を確認します。
* サードパーティ製パッケージは、AEM as a Cloud Service の[開発](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja)および[パッケージ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html?lang=ja)ガイドラインに準拠する必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [INST 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
