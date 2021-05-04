---
title: REP
description: パターン検出コードのヘルプページ
exl-id: e788deba-a301-404f-8e90-51f721409e69
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 86%

---

# [!DNL REP] {#rep}

レプリケーションエージェント

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="レプリケーションエージェント"
>abstract="REPは、有効なレプリケーション・エージェントを識別します。 ここでは、AEM as a Cloud Service へのアップグレード時に対応しなければならない可能性がある問題について報告されています。AEM as Cloud Service では、Sling Content Distribution を使用して、作成者の設定したコンテンツを公開環境に配布します。これは、Adobe I/O のパイプラインサービスを使用して、AEM Runtime の外部で行われます。またプロビジョニングされた AEM as a Cloud Service 環境の内部で自動的に設定されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents" text="主な変更点 — AEMをCloud Serviceとして"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents" text="開発のガイドライン"

`REP` は有効なレプリケーションエージェントを識別します。ここでは、AEM as a Cloud Service へのアップグレード時に対応しなければならない可能性がある問題について報告されています。

AEM as Cloud Service では、[Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html) を使用して、作成者の設定したコンテンツを公開環境に配布します。これは、Adobe I/O のパイプラインサービスを使用して、AEM Runtime の外部で行われます。またプロビジョニングされた AEM as a Cloud Service 環境の内部で自動的に設定されます。

## 可能性のある影響およびリスク {#implications-and-risks}

* AEM as a Cloud Service ではレプリケーションの設定が変更されました。現在のレプリケーションエージェントをすべてレビューして、どの機能が標準機能に置き換えられているのか、どの設定をコードに移行する必要があるのか、またどの機能がサポートされていないのかを確認する必要があります。
* AEM as a Cloud Service へのアップグレード時に、カスタムコードまたはワークフローの中で何らかのレプリケーションエージェントが使用されていないかを確認する必要があります。
* AEM as a Cloud Service では初期段階で、リバースレプリケーションはサポートされていません。
* Dispatcher Flush エージェントを別途設定する必要はありません。Dispatcher Flush エージェントは、AEM as a Cloud Service 環境で自動的に設定されます。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="導入ガイダンス"
>abstract="ベスト・プラクティスは、レプリケーション・エージェントに直接依存してカスタム機能を確認、リファクタリング、最適化し、Cloud ServiceとしてAEMとの互換性を確保することです。 ヘルプと説明を求めるAdobeサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication" text="レプリケーション：Cloud ServiceとしてのAEM"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* [レプリケーションエージェント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja#replication-agents)については、AEM as a Cloud Service の[開発ガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=ja#no-reverse-replication-agents)およびリリースノートを参照してください。
* ビジネスタスクの実行にあたり、レプリケーションエージェントに直接依存する機能については、見直し、リファクタリング、最適化をおこなってください。
* AEM as a Cloud Service でのデプロイメントによって[レプリケーション](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=ja#replication)がどのように影響されるかを確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
