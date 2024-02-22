---
title: MI
description: パターン検出コードのヘルプページ
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: efb06dc7e00f91d4c080553df3153deb90b093f2
workflow-type: ht
source-wordcount: '210'
ht-degree: 100%

---

# MI {#mi}

設定ミスの問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="設定ミスの問題"
>abstract="MI が、AEM インスタンスの設定の問題を識別する"

`MI` 設定ミスの問題は、AEM インスタンスの設定の問題を識別します。

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
   * 使用可能なプロセッサーの半分を利用するには、値を 0.5 に設定することをお勧めします。
* `missing.maintenance.configuration`
   * リビジョンクリーンアップ：[リビジョンクリーンアップ](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=ja)を参照してください。設定に関する重要な部分については、[リビジョンクリーンアップ - テールコンパクションおよびフルコンパクションの設定](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=ja#how-to-configure-full-and-tail-compaction)を参照してください。
   * Lucene バイナリクリーンアップ：[操作ダッシュボード - Lucene バイナリクリーンアップ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-dashboard.html?lang=ja#lucene-binaries-cleanup)を参照してください。
   * データストアのガベージコレクション：[データストアのガベージコレクション](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/data-store-garbage-collection.html?lang=ja)を参照してください。
   * ワークフローのパージ：[ワークフローインスタンスの定期的なパージ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/workflows-administering.html#regular-purging-of-workflow-instances?lang=ja)を参照してください。
   * 監査ログのメンテナンスタスク：[監査ログのメンテナンス](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-audit-log.html?lang=ja)を参照してください。
* 不明な点や対処すべき懸念がある場合は、アドビの [Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
