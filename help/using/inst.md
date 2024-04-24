---
title: INST
description: パターン検出コードのヘルプページ
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 73%

---

# INST {#inst}

インストール済みアーティファクト

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="インストール済みアーティファクト"
>abstract="INST は、ユーザーによって AEM にインストールされたカスタムおよびサードパーティ製のパッケージおよびバンドルを識別します。こうした情報は、システムの状態やアップグレード作業の全般的な範囲を把握するために報告されます。サードパーティ製パッケージは、AEM as a Cloud Service の開発およびパッケージガイドラインに準拠する必要があります。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="開発ガイドライン - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package" text="パッケージガイドライン - AEM as a Cloud Service"

`INST`  は、ユーザーによってAEMにインストールされたカスタムおよびサードパーティ製のパッケージおよびバンドルを識別します。 こうした情報は、システムの状態やアップグレード作業の全般的な範囲を把握するために報告されます。

1 つのパッケージについて複数のバージョンがインストールされている場合は、最新バージョンだけが報告されます。

検出されたパッケージとバンドルは、必ずしも AEM as a Cloud Service に最適化されているわけではありません。サードパーティ製パッケージと AEM as a Cloud Service の互換性については、パッケージの作成者またはアドビに確認してください。

サブタイプを使用して、各種情報を識別します。

* `custom.bundle`：AEM にインストールされたバンドル
* `custom.package`：AEM にインストールされたパッケージ

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="実装ガイダンス"
>abstract="CRX パッケージマネージャーを使用してサードパーティパッケージをインストールすることはできなくなりました。 構造化が必要なこれらのインストール済みアーティファクトを確認し、AEM as a Cloud Serviceと連携するように最適化する必要があります。 AEM as a Cloud Serviceと互換性を持たせるために、サードパーティ製パッケージの作成者またはAdobeを確認します。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embeddeds" text="コンテナパッケージへのサブパッケージの埋め込み"


* CRX パッケージマネージャーを使用してサードパーティ製パッケージを AEM as a Cloud Service にインストールすることはできません。
* サードパーティ製パッケージに依存するアプリケーションは、AEM as a Cloud Service での動作に合わせて正しくデプロイしない限り、期待通り動作しないことがあります。
* サードパーティベンダーのパッケージは、AEM as a Cloud Service 用に最適化されていないと、意図しない動作をする可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認し、INST 違反を修正して AEM as a Cloud Service に対応させる方法を把握します。また、GitHub の INST 違反例を確認し、問題を修正してAEMas a Cloud Service環境にデプロイする方法も理解します。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST 違反の例 – GitHub"

* サードパーティ製パッケージは、Cloud Manager の[デプロイメントプロセス](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/deploy-code#deployment-process)を使用して、プロジェクトの一部として AEM にデプロイする必要があります。
* AEM as a Cloud Service のプロジェクトに[サードパーティ製パッケージを組み込む](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embedding-3rd-party-packages)方法を確認します。
* サードパーティ製パッケージは、AEM as a Cloud Service の[開発](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines)および[パッケージ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package)ガイドラインに準拠する必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [INST 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)を修正および変更する方法を確認します。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
