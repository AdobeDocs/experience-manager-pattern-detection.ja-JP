---
title: WRK
description: パターン検出コードのヘルプページ
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 100%

---

# WRK {#wrk}

ワークフロー

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="ワークフロー"
>abstract="WRK コードは、ワークフローモデルまたはランチャーに関連する情報を識別します。これらの情報は、AEM as a Cloud Service へのアップグレード時にはカスタムアセットワークフローモデルの移行が必須になるため、報告されます。現在、AEM as a Cloud Service でのアセット処理は、アセットマイクロサービスによって実行されています"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="アセットマイクロサービス"

`WRK` は、ワークフローモデルまたはランチャーに関連する情報を識別します。これらの情報は、AEM as a Cloud Service へのアップグレード時にはカスタムアセットワークフローモデルの移行が必須になるため、報告されます。

サブタイプを使用して、現在検出されているワークフローの問題の種類を識別します。

* `custom.asset.workflow`：カスタムアセットワークフローモデル、ランチャーを検出しました。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="実装ガイダンス"
>abstract="標準のアセットワークフローはアセットマイクロサービスで自動的にサポートされるので、ベストプラクティスとしては、すべてのカスタムアセットワークフローモデルまたはランチャーを調べて、AEM as a Cloud Service に移行した後もそれらが必要かどうかを確認することをお勧めします。アセットワークフローをカスタマイズする場合は、AEM as a Cloud Service と連携できるように、アセットワークフロー移行ツールを使用して移行する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="はじめに - アセットマイクロサービス"

* アセットの処理はこれまで、AEM オーサーインスタンス上で実行するアセットワークフローで実行されていました。現在、AEM as a Cloud Service でのアセット処理は、アセットマイクロサービスによって実行されています（詳細については、「[アセットマイクロサービスの概要](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=ja)」を参照してください）。
* 標準のアセットワークフローは、アセットマイクロサービスで自動的にサポートされます。
* アセットワークフローをカスタマイズする場合は、AEM as a Cloud Service に対応させるために移行が必要です。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="ツールとリソース"
>abstract="カスタムのアセットワークフローモデルまたはランチャーを識別したら、アセットワークフロー移行ツールを確認し実行計画を立てます。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="アセットワークフロー移行ツール"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* カスタムアセットワークフローモデル、またはランチャーが識別された場合は、[アセットワークフロー移行ツール](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html?lang=ja)の実行を検討します。
* 詳細については、「[アセットマイクロサービスの概要](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html?lang=ja)」を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
