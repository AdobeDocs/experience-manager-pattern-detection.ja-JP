---
title: MI
description: パターン検出コードのヘルプページ
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 54%

---

# MI {#mi}

設定ミスの問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="設定ミスの問題"
>abstract="MI が、AEM インスタンスの設定の問題を識別する"

MI 設定ミスの問題は、AEM インスタンスの設定の問題を特定します。

次のようなサブタイプを使用して、各種情報を識別します。

* `sling.job.max.parallel`：最大並列設定が -1 に設定されている Sling ジョブを識別します。
* `missing.maintenance.configuration`：欠落しているメンテナンスタスクの設定を識別します。

## 可能性のある影響およびリスク {#implications-and-risks}

* `sling.job.max.parallel`
   * -1 の値は、使用可能なプロセッサの数に置き換えられます。これにより、AEM インスタンスでパフォーマンスの問題が発生する可能性があります。
* `missing.maintenance.configuration`
   * メンテナンスタスクの設定が欠落していると、パフォーマンスの低下やインスタンスの破損が発生する可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="実装ガイダンス"
>abstract="カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* `sling.job.max.parallel`
   * Adobeでは、使用可能なプロセッサーの半分を活用するために、値を 0.5 に設定することをお勧めします。
* `missing.maintenance.configuration`
   * リビジョンのクリーンアップ： [リビジョンのクリーンアップ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup). 設定に関する重要な部分については、[リビジョンクリーンアップ - テールコンパクションおよびフルコンパクションの設定](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)を参照してください。
   * Lucene バイナリクリーンアップ：を参照してください [操作ダッシュボード - Lucene バイナリクリーンアップ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-dashboard#lucene-binaries-cleanup).
   * データストアのガベージコレクション：を参照してください [データストアのガベージコレクション](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/data-store-garbage-collection).
   * ワークフローパージ：を参照してください [ワークフローインスタンスの定期的なパージ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/workflows-administering#regular-purging-of-workflow-instances).
   * 監査ログのメンテナンスタスク：を参照 [監査ログのメンテナンス](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-audit-log).
* に連絡してください [Experience Managerカスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
