---
title: WRK
description: パターン検出コードのヘルプページ。
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 100%

---

# WRK {#wrk}

ワークフロー

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="ワークフロー"
>abstract="WRK コードは、ワークフローモデルまたはランチャーに関連する情報を識別します。これらの情報は、AEM as a Cloud Service へのアップグレード時にはカスタムアセットワークフローモデルの移行が必須になるため、報告されます。現在、AEM as a Cloud Service でのアセット処理は、アセットマイクロサービスによって実行されています"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview" text="アセットマイクロサービス"

`WRK` は、ワークフローモデルまたはランチャーに関連する検出結果を識別します。これらの情報は、AEM as a Cloud Service へのアップグレード時にはカスタムアセットワークフローモデルの移行が必須になるため、報告されます。

サブタイプを使用して、現在検出されているワークフローの問題の種類を識別します。

* `custom.asset.workflow`：カスタムアセットワークフローモデル、ランチャーを検出しました。

## 考えられる影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="実装ガイダンス"
>abstract="標準のアセットワークフローは、アセットマイクロサービスで自動的にサポートされます。そのため、ベストプラクティスは、すべてのカスタムアセットワークフローモデルまたはランチャーを確認して、AEMas a Cloud Service 環境に移行した後も必要かどうかを確認することです。アセットワークフローをカスタマイズするには、アセットワークフロー移行ツールを使用して AEM as a Cloud Service と連携するように移行する必要があります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use" text="はじめに - アセットマイクロサービス"

* アセットの処理はこれまで、AEM オーサーインスタンス上で実行するアセットワークフローで実行されていました。現在、AEM as a Cloud Service でのアセット処理は、アセットマイクロサービスによって実行されています詳しくは、[アセットマイクロサービスの概要](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview)を参照してください。
* 標準のアセットワークフローは、アセットマイクロサービスで自動的にサポートされます。
* アセットワークフローをカスタマイズするには、AEM as a Cloud Service で操作するように移行する必要があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="ツールとリソース"
>abstract="カスタムのアセットワークフローモデルまたはランチャーを識別したら、アセットワークフロー移行ツールを確認し実行計画を立てます。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool" text="アセットワークフロー移行ツール"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* カスタムアセットワークフローモデル、またはランチャーが識別された場合は、[アセットワークフロー移行ツール](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool)の実行を検討します。
* 詳細については、「[アセットマイクロサービスの概要](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use)」を参照してください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
