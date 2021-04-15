---
title: DOPI
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: ht
source-wordcount: '143'
ht-degree: 100%

---


# DOPI {#dopi}

非推奨（廃止予定）の順序付きプロパティインデックス

## 背景 {#background}

`DOPI` は、6.1 以降で非推奨になり、6.2 で削除された順序付きプロパティインデックス（`primaryType=oak:QueryIndexDefinition` と `type="ordered"`）の使用を識別します。

## 可能性のある影響およびリスク {#implications-and-risks}

* クエリによっては、応答しない場合があります。
* お客様の機能が正しく動作しないことがあります。
* 非推奨（廃止予定）のインデックスは効果がないため、トラバーサル警告やエラーが発生し、著しいパフォーマンスペナルティを伴うことがあります。

## 可能な解決策 {#solutions}

* インデックス定義をサポートされている定義にするか、サポートされているインデックス定義を使って、インデックスを置き換えます（「[Oak クエリとインデックス作成](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=ja)」を参照）。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [DOPI 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
