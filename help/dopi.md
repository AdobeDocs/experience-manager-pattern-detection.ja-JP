---
title: DOPI
description: パターン検出コードのヘルプページ
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 55%

---

# DOPI {#dopi}

非推奨（廃止予定）の順序付きプロパティインデックス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="非推奨（廃止予定）の順序付きプロパティインデックス"
>abstract="DOPIコードは、6.1以降で廃止され、6.2で削除された、順序付けられたプロパティインデックス定義(primaryType=oak:QueryIndexDefinition AND type=&quot;ordered&quot;)の使用を識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=en#the-ordered-index" text="順序付きインデックス — 廃止"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=ja" text="インデックス作成 — AEMをCloud Serviceとして"

`DOPI` は、6.1 以降で非推奨になり、6.2 で削除された順序付きプロパティインデックス（`primaryType=oak:QueryIndexDefinition` と `type="ordered"`）の使用を識別します。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="導入ガイダンス"
>abstract="ベストプラクティスは、非推奨となった注文されたインデックスをすべて確認し、サポートされている形式のluceneインデックスに移動して、重要なパフォーマンスの問題や機能しないお客様の要件を回避することです。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/practices/best-practices-for-queries-and-indexing.html" text="ベストプラクティス —クエリとインデックス作成"

* クエリによっては、応答しない場合があります。
* お客様の機能が正しく動作しないことがあります。
* 非推奨（廃止予定）のインデックスは効果がないため、トラバーサル警告やエラーが発生し、著しいパフォーマンスペナルティを伴うことがあります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="ツールとリソース"
>abstract="WKND-legacyプロジェクトを見直し、DOPI違反がAEMCloud Serviceとどのように互換性を持つかを理解します。 また、GithubのDOPI違反の例を見て、従来の順序付けられたインデックスが、AEMでCloud ServiceとしてサポートされているLuceneベースのインデックスに変換される方法を理解してください。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND — レガシープロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI違反の例 — Github"

* インデックス定義をサポートされている定義にするか、サポートされているインデックス定義を使って、インデックスを置き換えます（「[Oak クエリとインデックス作成](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=ja)」を参照）。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [DOPI 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
