---
title: WRK
description: パターン検出コードのヘルプページ。
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 56%

---

# WRK {#wrk}

ワークフロー

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="ワークフロー"
>abstract="WRK コードは、ワークフローモデルまたはランチャーに関連する情報を識別します。これらの識別は、AEM as a Cloud Serviceへのアップグレード時にカスタムアセットワークフローモデルを移行する必要があるために報告されます。 AEM as a Cloud Serviceを使用すると、アセットマイクロサービスがアセット処理を実行します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview" text="アセットマイクロサービス"

`WRK` は、ワークフローモデルまたはランチャーに関連する検出結果を識別します。これらの識別は、AEM as a Cloud Serviceへのアップグレード時にカスタムアセットワークフローモデルを移行する必要があるために報告されます。

サブタイプを使用して、現在検出されているワークフローの問題の種類を識別します。

* `custom.asset.workflow`：カスタムアセットワークフローモデル、ランチャーを検出しました。

## 考えられる影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="実装ガイダンス"
>abstract="標準のアセットワークフローは、アセットマイクロサービスで自動的にサポートされます。したがって、ベストプラクティスは、すべてのカスタムアセットワークフローモデルまたはランチャーを確認することです。 レビューする際は、AEMas a Cloud Service環境への移行後にそれらが必要かどうかを確認できます。 アセットワークフローをカスタマイズする場合は、アセットワークフロー移行ツールを使用してAEM as a Cloud Service環境と連携するように移行する必要があります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use" text="はじめに - アセットマイクロサービス"

* アセットの処理はこれまで、AEM オーサーインスタンス上で実行するアセットワークフローで実行されていました。AEM as a Cloud Serviceを使用すると、アセットマイクロサービスがアセット処理を実行します。 詳しくは、[アセットマイクロサービスの概要](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview)を参照してください。
* 標準のアセットワークフローは、アセットマイクロサービスで自動的にサポートされます。
* アセットワークフローをカスタマイズするには、AEM as a Cloud Service で操作するように移行する必要があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="ツールとリソース"
>abstract="カスタムのアセットワークフローモデルまたはランチャーが特定されたら、アセットワークフロー移行ツールを確認し実行計画を立てます。 ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool" text="アセットワークフロー移行ツール"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* カスタムアセットワークフローモデル、またはランチャーが識別された場合は、[アセットワークフロー移行ツール](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool)の実行を検討します。
* 詳細については、「[アセットマイクロサービスの概要](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use)」を参照してください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
