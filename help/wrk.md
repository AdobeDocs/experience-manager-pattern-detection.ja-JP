---
title: WRK
description: パターン検出コードのヘルプページ
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 70%

---

# WRK {#wrk}

ワークフロー

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="ワークフロー"
>abstract="WRKコードは、ワークフローモデルまたはランチャーに関連する検索を識別します。 これらの情報は、AEM as a Cloud Service へのアップグレード時にはカスタムアセットワークフローモデルの移行が必須になるため、報告されます。現在、AEM as a Cloud Service でのアセット処理は、アセットマイクロサービスによって実行されています"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="アセットマイクロサービス"

`WRK` は、ワークフローモデルまたはランチャーに関連する情報を識別します。これらの情報は、AEM as a Cloud Service へのアップグレード時にはカスタムアセットワークフローモデルの移行が必須になるため、報告されます。

サブタイプを使用して、現在検出されているワークフローの問題の種類を識別します。

* `custom.asset.workflow`：カスタムアセットワークフローモデル、ランチャーを検出しました。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="導入ガイダンス"
>abstract="標準のアセットワークフローは自動的にアセットマイクロサービスをサポートするので、ベストプラクティスは、AEMにCloud Serviceとしてトランジションした後、カスタムのアセットワークフローモデルまたはランチャーをすべて確認し、必要かどうかを確認することです。 アセットワークフローのカスタマイズは、Asset Workflow Migration Toolの支援を得てAEMをCloud Serviceとして操作するために、移行が必要です。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="はじめに — Asset Microservices"

* アセットの処理はこれまで、AEM オーサーインスタンス上で実行するアセットワークフローで実行されていました。現在、AEM as a Cloud Service でのアセット処理は、アセットマイクロサービスによって実行されています（詳細については、「[アセットマイクロサービスの概要](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=ja)」を参照してください）。
* 標準のアセットワークフローは、アセットマイクロサービスで自動的にサポートされます。
* アセットワークフローをカスタマイズする場合は、AEM as a Cloud Service に対応させるために移行が必要です。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="ツールとリソース"
>abstract="カスタムのアセットワークフローモデルまたはランチャーが識別されたら、アセットワークフロー移行ツールを確認し、実行する計画を立てます。 ヘルプと説明を求めるAdobeサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="アセットワークフロー移行ツール"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* カスタムアセットワークフローモデル、またはランチャーが識別された場合は、[アセットワークフロー移行ツール](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html?lang=ja)の実行を検討します。
* 詳細については、「[アセットマイクロサービスの概要](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html?lang=ja)」を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
