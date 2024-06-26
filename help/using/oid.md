---
title: OID
description: パターン検出コードのヘルプページ。
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 100%

---

# OID {#oid}

Oak インデックス定義

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak Index Definition"
>abstract="OID は、Oak インデックスの定義に関連する問題を識別します。標準 Oak インデックス定義に加えられた変更を識別します。AEM as a Cloud Service と互換性のないカスタム Oak インデックス定義も識別されます。OID の各検索結果に関するメッセージでは、インデックスを識別し、追加情報を追加します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/operations/indexing#how-to-use" text="コンテンツインデックス作成ガイドライン"

`OID` は、Oak インデックスの定義に関連する問題を識別します。標準 Oak インデックス定義に加えられた変更を識別します。AEM as a Cloud Service と互換性のないカスタム Oak インデックス定義も識別されます。各 `OID` 検出結果に関するメッセージでは、インデックスが識別され、追加情報が提供されます。

サブタイプを使用すると、様々なタイプの情報を識別できます。

* `index.rule.violation`：カスタム Oak インデックスと AEM as a Cloud Service との非互換性
* `standard.index.modification`：標準 Oak インデックスに対する変更

## 考えられる影響とリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、すべてのカスタムインデックスを確認し、コンテンツインデックス作成ガイドラインに従って再構築することをお勧めします。インデックスコンバーターを使用して、既存のカスタム Oak インデックス定義を AEM as a Cloud Service と互換性のあるカスタム Oak インデックス定義に移行します"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#oak-indexes" text="パッケージガイドライン"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools" text="インデックスコンバーター"

* 標準 Oak インデックス定義に対する変更は、AEM のアップグレード中に失われることがあります。
* Oak の定義は不変であるため、カスタムプロジェクトコードでパッケージ化します。またデプロイは Cloud Manager を使用してのみ行います。
* すべての Oak インデックス定義では、AEM as a Cloud Service の Oak インデックスに関する命名規則とその他のルールに従う必要があります。そうしないと、望ましくない動作が発生する可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認し、プロジェクトの OID 違反を解決する方法を把握します。また、GitHub の OID 違反の例も確認します。これは、インデックスコンバーターツールを使用して従来のインデックスを変換し、AEM as a Cloud Service と互換性を持たせる方法を把握するのに役立ちます。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID 違反の例 - GitHub"

* メッセージで特定されたインデックスルールの違反を解決します。
* 新しいまたはカスタムの Oak インデックス定義をデプロイするには、AEM as a Cloud Service の[パッケージ化ガイドライン](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure)に従ってください。
* カスタマイズした AEM 標準インデックスと新しいカスタム Oak インデックス定義では、AEM as a Cloud Service の[コンテンツインデックス作成ガイドライン](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/operations/indexing#preparing-the-new-index-definition)に従う必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [OID 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)を修正および変更する方法を確認します。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
* [インデックスコンバーター](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools)を使用して、既存のカスタム Oak インデックス定義を AEM as a Cloud Service と互換性のあるカスタム Oak インデックス定義に移行します。
