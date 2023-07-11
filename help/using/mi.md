---
title: MI
description: パターン検出コードのヘルプページ
source-git-commit: aa05ebcb54c6945a903c76add4f31e3279cd05b5
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 38%

---

# MI {#mi}

設定ミスの問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="設定ミスの問題"
>abstract="MI が、AEM インスタンスの設定の問題を識別する"

`MI`  設定ミスの問題は、AEMインスタンスの設定の問題を特定します。

次のようなサブタイプを使用して、各種情報を識別します。

* `sling.job.max.parallel`:最大並列設定が —1 に設定されている Sling ジョブを特定します。
* `missing.maintenance.configuration`:不足しているメンテナンスタスク設定を特定します。

## 可能性のある影響およびリスク {#implications-and-risks}

* `sling.job.max.parallel`
   * -1 の値は、使用可能なプロセッサの数に置き換えられます。 その場合、AEMインスタンスでパフォーマンスの問題が発生する可能性があります。
* `missing.maintenance.configuration`
   * メンテナンスタスクの設定が見つからないと、パフォーマンスが低下したり、インスタンスが破損したりする可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="実装ガイダンス"
>abstract="カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* `sling.job.max.parallel`
   * 使用可能なプロセッサの半分を利用するには、値を 0.5 に設定することをお勧めします。
* `missing.maintenance.configuration`
   * リビジョンのクリーンアップ：詳しくは、 [リビジョンのクリーンアップ](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=ja). 設定に関する重要な部分は次のとおりです。 [リビジョンクリーンアップ — テールおよびフルコンパクションを設定](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html#how-to-configure-full-and-tail-compaction).
   * Lucene バイナリクリーンアップ：詳しくは、 [操作ダッシュボード — Lucene バイナリクリーンアップ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-dashboard.html#lucene-binaries-cleanup).
   * データストアのガベージコレクション：詳しくは、 [データストアのガベージコレクション](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/data-store-garbage-collection.html?lang=ja).
   * ワークフローのパージ：詳しくは、 [ワークフローインスタンスの定期的なパージ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/workflows-administering.html?lang=ja#regular-purging-of-workflow-instances).
   * 監査ログのメンテナンスタスク：詳しくは、 [監査ログのメンテナンス](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-audit-log.html?lang=ja).
* 不明な点や対処すべき懸念がある場合は、アドビの [Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。