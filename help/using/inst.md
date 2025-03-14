---
title: INST
description: パターン検出コードのヘルプページ。
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 90%

---

# INST {#inst}

インストール済みのアーティファクト

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="インストール済みのアーティファクト"
>abstract="INST は、お客様が AEM にインストールしたカスタムおよびサードパーティのパッケージとバンドルを識別します。このようなパッケージとバンドルは、システムの状態やアップグレード作業の一般的な範囲の特徴を把握するために報告されます。サードパーティ製パッケージは、AEM as a Cloud Service の開発およびパッケージガイドラインに準拠する必要があります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="開発ガイドライン - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package" text="パッケージガイドライン - AEM as a Cloud Service"

`INST` は、お客様が AEM にインストールしたカスタムおよびサードパーティのパッケージとバンドルを識別します。このようなパッケージとバンドルは、システムの状態やアップグレード作業の一般的な範囲の特徴を把握するために報告されます。

1 つのパッケージについて複数のバージョンがインストールされている場合は、最新バージョンだけが報告されます。

検出されたパッケージとバンドルは、必ずしも AEM as a Cloud Service に最適化されているわけではありません。サードパーティ製パッケージと AEM as a Cloud Service の互換性については、パッケージの作成者またはアドビに確認してください。

次のサブタイプを使用して、各種情報を識別します。

* `custom.bundle`：AEM にインストールされたバンドル
* `custom.package`：AEM にインストールされたパッケージ

## 考えられる影響とリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="実装ガイダンス"
>abstract="お客様は CRX パッケージマネージャーを使用してサードパーティ製パッケージをインストールできなくなりました。これらのインストール済みアーティファクトを確認し、AEM as a Cloud Service と連携できるように再構成および最適化する必要があります。サードパーティパッケージの作成者またはアドビに、AEM as a Cloud Service との互換性を確認します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embeddeds" text="コンテナパッケージへのサブパッケージの埋め込み"


* CRX パッケージマネージャーを使用してサードパーティ製パッケージを AEM as a Cloud Service にインストールすることはできません。
* サードパーティ製パッケージに依存するアプリケーションは、AEM as a Cloud Service での動作に合わせて正しくデプロイしない限り、期待通り動作しないことがあります。
* サードパーティベンダーのパッケージは、AEM as a Cloud Service 用に最適化されていないと、意図しない動作をする可能性があります。

また、次の特定のサブタイプにも注意を払うことを検討してください。

* `guava.bundle` - Guava はAEM 6.5 LTS の標準ではサポートされておらず、アップグレード後はバンドルを使用できなくなります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="ツールとリソース"
>abstract="WKND-legacy プロジェクトを確認し、INST 違反を修正して AEM as a Cloud Service と互換性を持たせる方法を把握します。また、GitHub の INST 違反例を確認し、この問題を修正して AEM as a Cloud Service にデプロイする方法を把握します。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST 違反の例 - GitHub"

* サードパーティ製パッケージは、Cloud Manager の[デプロイメントプロセス](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/deploy-code#deployment-process)を使用して、プロジェクトの一部として AEM にデプロイする必要があります。
* AEM as a Cloud Service のプロジェクトに[サードパーティ製パッケージを組み込む](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embedding-3rd-party-packages)方法を確認します。
* サードパーティ製パッケージは、AEM as a Cloud Service の[開発](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines)および[パッケージ](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package)ガイドラインに準拠する必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [INST 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)を修正および変更する方法を確認します。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
* `guava.bundle` サブタイプの場合は、Guava をインストールするか、カスタムコードで Guava が使用されている場合は使用状況を削除します。
