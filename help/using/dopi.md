---
title: DOPI
description: パターン検出コードのヘルプページ。
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '251'
ht-degree: 100%

---

# DOPI {#dopi}

非推奨（廃止予定）の順序付きプロパティインデックス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="非推奨（廃止予定）の順序付きプロパティインデックス"
>abstract="DOPI コードは、順序付きプロパティインデックス定義（`primaryType=oak:QueryIndexDefinition` AND type=&quot;ordered&quot;）の使用を識別します。この定義は 6.1 以降で非推奨となり、6.2 で削除されました。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#the-ordered-index" text="順序付きインデックス - 非推奨"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/operations/indexing" text="インデックス作成 - AEM as a Cloud Service"

`DOPI` は、使用されている順序付きプロパティインデックス定義（`primaryType=oak:QueryIndexDefinition` および `type="ordered"`）を識別します。これらは、AEM 6.1 以降非推奨となり、AEM 6.2 で削除されました。

## 考えられる影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、非推奨の順序付きインデックスをすべて確認し、サポートされている Lucene インデックス形式に移行して、パフォーマンス上の重大な問題や顧客要件が満たされないなどの問題を回避することをお勧めします。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/practices/best-practices-for-queries-and-indexing" text="ベストプラクティス - クエリとインデックス"

* クエリによっては、応答しない場合があります。
* お客様の機能が正しく動作しないことがあります。
* 非推奨（廃止予定）のインデックスは効果がないため、トラバーサル警告やエラーが発生し、著しいパフォーマンスペナルティを伴うことがあります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認し、DOPI 違反を修正して AEM as a Cloud Service に対応させる方法を把握します。また、GitHub の DOPI 違反例を確認して、従来の順序付きインデックスを AEM as a Cloud Service でサポートされている Lucene ベースのインデックスに変換する方法も理解します。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI 違反の例 - GitHub"

* インデックス定義を編集して、サポートされているインデックス定義になるようにするか、インデックスを置き換えます。（[Oak クエリとインデックス作成](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing)を参照）。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [DOPI 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)を修正および変更する方法を確認します。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
