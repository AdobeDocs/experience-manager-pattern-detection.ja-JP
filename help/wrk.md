---
title: WRK
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 10%

---


# WRK {#wrk}

ワークフロー

## 背景 {#background}

`WRK` ワークフローモデルまたはランチャーに関連する検索を識別します。これらは、AEMにCloud Serviceーとしてアップグレードする場合、カスタムアセットワークフローモデルを移行する必要があるので、レポートされます。

サブタイプは、現在検出されているワークフローの問題の種類を識別するために使用されます。

* `custom.asset.workflow`:カスタムアセットワークフローモデルまたはランチャーの検出。

## 可能性のある影響およびリスク {#implications-and-risks}

* アセットの処理は、従来、AEM Authorインスタンスで実行されるアセットワークフローで実行されてきました。 AEMをCloud Serviceとして、アセットマイクロサービスによってアセット処理が実行されるようになりました。 (詳しくは、[アセットのマイクロサービスの概要](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=ja)を参照してください。
* 標準のアセットワークフローは、自動的にアセットマイクロサービスに対応します。
* アセットワークフローのカスタマイズは、AEMをCloud Serviceとして操作するために、移行する必要があります。

## 可能な解決策 {#solutions}

* カスタムアセットワークフローモデルまたはランチャーが識別された場合は、[アセットワークフロー移行ツール](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html)を実行することを計画します。
* 詳しくは、[Asset microservices](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html?lang=ja)を使用する前にを参照してください。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
