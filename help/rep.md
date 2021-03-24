---
title: REP
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 7d05067fc624571e6fe520e2a1addd5dff8acbd8
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 5%

---


# [!DNL REP] {#rep}

レプリケーションエージェント

## 背景 {#background}

`REP` 有効なレプリケーションエージェントを識別します。これらの情報は、AEMにCloud Serviceとしてアップグレードする際に対処する必要がある問題が発生する可能性があることが原因で報告されます。

AEM asCloud Serviceは、[Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html)を使用して、作成者から環境へのコンテンツの配布を行います。 これは、Adobe I/Oのパイプラインサービスを使用して、AEMランタイムの外部で行われます。これは、プロビジョニングされたAEMでCloud Service環境として自動的に設定されます。

## 可能性のある影響およびリスク {#implications-and-risks}

* レプリケーションの構成は、AEMをCloud Serviceとして変更されました。 現在のすべてのレプリケーションエージェントを確認し、標準機能に置き換えられた構成、コードに移動する必要のある構成、サポートされていない構成を確認する必要があります。
* カスタムコードまたはワークフローでのレプリケーションエージェントの使用は、AEMにCloud Serviceとしてアップグレードする際に確認する必要があります。
* 逆複製は、AEMでは、Cloud Serviceとして最初はサポートされていません。
* 個別のディスパッチャーフラッシュエージェントを設定する必要はありません。 これは、AEMでCloud Service環境として自動的に設定されます。

## 可能な解決策 {#solutions}

* AEMをCloud Service[開発ガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents)として参照し、[複製エージェント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents)のリリースノートを参照してください。
* ビジネス・タスクの実行に必要なレプリケーション・エージェントに直接依存して、機能の確認、リファクタリング、最適化を行います。
* AEMでの展開が[レプリケーション](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication)に与える影響をCloud Serviceとして確認します。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
