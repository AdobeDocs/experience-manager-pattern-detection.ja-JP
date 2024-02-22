---
title: REP
description: パターン検出コードのヘルプページ
exl-id: e788deba-a301-404f-8e90-51f721409e69
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '410'
ht-degree: 100%

---

# [!DNL REP] {#rep}

レプリケーションエージェント

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="レプリケーションエージェント"
>abstract="REP は有効なレプリケーションエージェントを識別します。ここでは、AEM as a Cloud Service へのアップグレード時に対応しなければならない可能性がある問題について報告されています。AEM as Cloud Service では、Sling Content Distribution を使用して、作成者の設定したコンテンツを公開環境に配布します。これは、Adobe I/O のパイプラインサービスを使用して、AEM Runtime の外部で行われます。またプロビジョニングされた AEM as a Cloud Service 環境の内部で自動的に設定されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja#replication-agents" text="主要な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja#no-reverse-replication-agents" text="開発のガイドライン"

`REP` は有効なレプリケーションエージェントを識別します。ここでは、AEM as a Cloud Service へのアップグレード時に対応しなければならない可能性がある問題について報告されています。

サブタイプを使用して、各種情報を識別します。

* `forward.replication`：有効なフォワードレプリケーションエージェントを特定します。
* `reverse.replication`：有効なリバースレプリケーションエージェントを識別します。
* `standard.replication.agent.modification`：変更された有効な標準レプリケーションエージェントを特定します。
* `custom.replication.agent.detection`：有効なカスタムレプリケーションエージェントを特定します。

AEM as Cloud Service では、[Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html) を使用して、作成者の設定したコンテンツを公開環境に配布します。これは、Adobe I/O のパイプラインサービスを使用して、AEM Runtime の外部で行われます。またプロビジョニングされた AEM as a Cloud Service 環境の内部で自動的に設定されます。

## 考えられる影響およびリスク {#implications-and-risks}

* AEM as a Cloud Service ではレプリケーションの設定が変更されました。現在のレプリケーションエージェントをすべてレビューして、どの機能が標準機能に置き換えられているのか、どの設定をコードに移行する必要があるのか、またどの機能がサポートされていないのかを確認する必要があります。
* AEM as a Cloud Service へのアップグレード時に、カスタムコードまたはワークフローの中で何らかのレプリケーションエージェントが使用されていないかを確認する必要があります。
* AEM as a Cloud Service では初期段階で、リバースレプリケーションはサポートされていません。
* Dispatcher Flush エージェントを別途設定する必要はありません。Dispatcher Flush エージェントは、AEM as a Cloud Service 環境で自動的に設定されます。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、レプリケーションエージェントに直接依存しているカスタム機能を確認、リファクタリングおよび最適化し、AEM as a Cloud Service に対応させることをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=ja#replication" text="レプリケーション - AEM as a Cloud Service"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* [レプリケーションエージェント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja#replication-agents)については、AEM as a Cloud Service の[開発ガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja#no-reverse-replication-agents)およびリリースノートを参照してください。
* ビジネスタスクの実行にあたり、レプリケーションエージェントに直接依存する機能については、見直し、リファクタリング、最適化を行ってください。
* AEM as a Cloud Service でのデプロイメントによって[レプリケーション](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=ja#replication)がどのように影響されるかを確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
