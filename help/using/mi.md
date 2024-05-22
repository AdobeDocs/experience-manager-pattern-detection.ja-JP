---
title: MI
description: パターン検出コードのヘルプページ。
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 85%

---

# MI {#mi}

設定ミスの問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="設定ミスの問題"
>abstract="MI が、AEM インスタンスの設定の問題を識別する"

`MI`（設定ミスの問題）は、AEM インスタンスの設定の問題を識別します。

次のようなサブタイプを使用して、各種情報を識別します。

* `sling.job.max.parallel`：最大並列設定が -1 に設定されている Sling ジョブを識別します。
* `missing.maintenance.configuration`：不足しているメンテナンスタスク設定を特定します。

## 考えられる影響およびリスク {#implications-and-risks}

* `sling.job.max.parallel`
   * -1 の値は、使用可能なプロセッサの数に置き換えられます。そのため、AEM インスタンスのパフォーマンスに問題が生じる可能性があります。
* `missing.maintenance.configuration`
   * メンテナンスタスクの設定が見つからない場合、パフォーマンスの損失やインスタンスの破損が発生する可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="実装ガイダンス"
>abstract="カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* `sling.job.max.parallel`
   * アドビでは、使用可能なプロセッサーの半分を活用するために、値を 0.5 に設定することをお勧めします。
* `missing.maintenance.configuration`
   * リビジョンのクリーンアップ：詳しくは、[リビジョンのクリーンアップ](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)を参照してください。設定に関する重要な部分について詳しくは、[リビジョンクリーンアップ - テールコンパクションおよびフルコンパクションの設定](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)を参照してください。
   * Lucene バイナリクリーンアップ：詳しくは、[操作ダッシュボード - Lucene バイナリクリーンアップ](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/sites/administering/operations/operations-dashboard#lucene-binaries-cleanup)を参照してください。
   * データストアのガベージコレクション：詳しくは、[データストアのガベージコレクション](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/sites/administering/operations/data-store-garbage-collection)を参照してください。
   * ワークフローのパージ：詳しくは、[ワークフローインスタンスの定期的なパージ](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/sites/administering/operations/workflows-administering#regular-purging-of-workflow-instances)を参照してください。
   * 監査ログのメンテナンスタスク：詳しくは、[監査ログのメンテナンス](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/sites/administering/operations/operations-audit-log)を参照してください。
* 詳しい説明や懸念事項の対応については、[Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
