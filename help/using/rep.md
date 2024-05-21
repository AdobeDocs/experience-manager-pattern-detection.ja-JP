---
title: REP
description: パターン検出コードのヘルプページ。
exl-id: e788deba-a301-404f-8e90-51f721409e69
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 57%

---

# [!DNL REP] {#rep}

レプリケーションエージェント

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="レプリケーションエージェント"
>abstract="REP は有効なレプリケーションエージェントを識別します。これらのエージェントについては、AEM as a Cloud Serviceへのアップグレード時に対応しなければならない問題が発生する可能性があるため報告されています。 AEM as Cloud Service では、Sling Content Distribution を使用して、作成者の設定したコンテンツを公開環境に配布します。この配布は、Adobe Developer上のAdobe I/O Runtimeのパイプラインサービスを使用して、AEM Runtime の外部で行われます。 このワークフローは、プロビジョニングされたAEMas a Cloud Service環境で自動的に設定されます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#replication-agents" text="主な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#no-reverse-replication-agents" text="開発のガイドライン"

`REP` は有効なレプリケーションエージェントを識別します。これらのエージェントについては、AEM as a Cloud Serviceへのアップグレード時に対応しなければならない問題が発生する可能性があるため報告されています。

次のサブタイプを使用して、各種情報を識別します。

* `forward.replication`：有効なフォワードレプリケーションエージェントを特定します。
* `reverse.replication`：有効なリバースレプリケーションエージェントを識別します。
* `standard.replication.agent.modification`：変更された有効な標準レプリケーションエージェントを特定します。
* `custom.replication.agent.detection`：有効なカスタムレプリケーションエージェントを特定します。

AEM as Cloud Service では、[Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html) を使用して、作成者の設定したコンテンツを公開環境に配布します。この配布は、Adobe Developer上のAdobe I/O Runtimeのパイプラインサービスを使用して、AEM Runtime の外部で行われます。 このワークフローは、プロビジョニングされたAEMas a Cloud Service環境で自動的に設定されます。

## 考えられる影響およびリスク {#implications-and-risks}

* AEM as a Cloud Service ではレプリケーションの設定が変更されました。現在のすべてのレプリケーションエージェントを確認する必要があります。 このレビューは、次の項目を確認するのに役立ちます。
   * 標準機能で置き換えることができるもの、
   * どの設定をコードに移動する必要があるか
   * （はサポートされていません）。
* AEM as a Cloud Service へのアップグレード時に、カスタムコードまたはワークフローの中で何らかのレプリケーションエージェントが使用されていないかを確認する必要があります。
* AEM as a Cloud Service では初期段階で、リバースレプリケーションはサポートされていません。
* 個別の Dispatcher フラッシュエージェントを設定する必要はありません。代わりに、AEMas a Cloud Service環境で自動的に設定されます。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、レプリケーションエージェントに直接依存しているカスタム機能を確認、リファクタリングおよび最適化し、AEM as a Cloud Service に対応させることをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/deploying/overview#replication" text="レプリケーション - AEM as a Cloud Service"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* [レプリケーションエージェント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#replication-agents)については、AEM as a Cloud Service の[開発ガイドライン](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#no-reverse-replication-agents)およびリリースノートを参照してください。
* ビジネスタスクの実行にあたり、レプリケーションエージェントに直接依存する機能については、見直し、リファクタリング、最適化を行ってください。
* 方法を参照 [複製](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/deploying/overview#replication) は、AEMas a Cloud Service環境でのデプロイメントを通じて影響を受けます。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
