---
title: WRK
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: ht
source-wordcount: '197'
ht-degree: 100%

---


# WRK {#wrk}

ワークフロー

## 背景 {#background}

`WRK` は、ワークフローモデルまたはランチャーに関連する情報を識別します。これらの情報は、AEM as a Cloud Service へのアップグレード時にはカスタムアセットワークフローモデルの移行が必須になるため、報告されます。

サブタイプを使用して、現在検出されているワークフローの問題の種類を識別します。

* `custom.asset.workflow`：カスタムアセットワークフローモデル、ランチャーを検出しました。

## 可能性のある影響およびリスク {#implications-and-risks}

* アセットの処理はこれまで、AEM オーサーインスタンス上で実行するアセットワークフローで実行されていました。現在、AEM as a Cloud Service でのアセット処理は、アセットマイクロサービスによって実行されています（詳細については、「[アセットマイクロサービスの概要](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=ja)」を参照してください）。
* 標準のアセットワークフローは、アセットマイクロサービスで自動的にサポートされます。
* アセットワークフローをカスタマイズする場合は、AEM as a Cloud Service に対応させるために移行が必要です。

## 可能な解決策 {#solutions}

* カスタムアセットワークフローモデル、またはランチャーが識別された場合は、[アセットワークフロー移行ツール](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html?lang=ja)の実行を検討します。
* 詳細については、「[アセットマイクロサービスの概要](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html?lang=ja)」を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
