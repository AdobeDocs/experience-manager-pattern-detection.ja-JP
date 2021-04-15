---
title: OID
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: 5a83dd8d08da974a5d775032b8dbea2593be9d15
workflow-type: ht
source-wordcount: '298'
ht-degree: 100%

---


# OID {#oid}

Oak Index Definition

## 背景 {#background}

`OID` は、Oak インデックスの定義に関連する問題を識別します。標準 Oak インデックス定義に加えられた変更を識別します。AEM as a Cloud Service と互換性のないカスタム Oak インデックス定義も識別されます。`OID` の各検索結果に関するメッセージには、インデックスと追加情報が記載されます。

サブタイプを使用して、各種情報を識別します。

* `custom.index.violation`：カスタム Oak インデックスと AEM as a Cloud Service との非互換性
* `standard.index.modification`：標準 Oak インデックスに対する変更

## 可能性のある影響およびリスク {#implications-and-risks}

* 標準 Oak インデックス定義に対する変更は、AEM のアップグレード中に失われることがあります。
* Oak の定義は不変であるため、カスタムプロジェクトコードでパッケージ化します。またデプロイは Cloud Manager を使用してのみ行います。
* Oak インデックス定義はすべて、AEM as Cloud Service での Oak インデックスに関する命名規則、その他のルールに準拠する必要があります。準拠していない定義は、意図しない動作の原因になります。

## 可能な解決策 {#solutions}

* メッセージで特定されたインデックスルールの違反を解決します。
* Oak インデックスの新しい定義やカスタム定義をデプロイする場合は、AEM as a Cloud Service の[パッケージガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja)に従ってください。
* カスタマイズした AEM 標準インデックス、および新規のカスタム Oak インデックスの定義は、AEM as Cloud Service の「[コンテンツインデックス作成ガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=ja#preparing-the-new-index-definition)」に従う必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [OID 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
* [インデックスコンバーター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html?lang=ja#refactoring-tools)を使用して、既存のカスタム Oak インデックス定義を AEM as a Cloud Service と互換性のあるカスタム Oak インデックス定義に移行します。
