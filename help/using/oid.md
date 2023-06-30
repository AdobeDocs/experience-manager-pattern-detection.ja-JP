---
title: OID
description: パターン検出コードのヘルプページ
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: d3e518cf8ad53a2cd28d4eea7f9b75c672881507
workflow-type: ht
source-wordcount: '485'
ht-degree: 100%

---

# OID {#oid}

Oak インデックス定義

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak Index Definition"
>abstract="OID は、Oak インデックスの定義に関連する問題を識別します。標準 Oak インデックス定義に加えられた変更を識別します。AEM as a Cloud Service と互換性のないカスタム Oak インデックス定義も識別されます。OID の各検索結果に関するメッセージには、インデックスと追加情報が記載されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=ja#how-to-use" text="コンテンツインデックス作成ガイドライン"

`OID` は、Oak インデックスの定義に関連する問題を識別します。標準 Oak インデックス定義に加えられた変更を識別します。AEM as a Cloud Service と互換性のないカスタム Oak インデックス定義も識別されます。`OID` の各検索結果に関するメッセージには、インデックスと追加情報が記載されます。

サブタイプを使用して、各種情報を識別します。

* `index.rule.violation`：カスタム Oak インデックスと AEM as a Cloud Service との非互換性
* `standard.index.modification`：標準 Oak インデックスに対する変更

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、すべてのカスタムインデックスを確認し、コンテンツインデックス作成ガイドラインに従って再構成することをお勧めします。インデックスコンバーターを使用して、既存のカスタム Oak インデックス定義を AEM as a Cloud Service と互換性のあるカスタム Oak インデックス定義に移行します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#oak-indexes" text="パッケージガイドライン"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html?lang=ja#refactoring-tools" text="インデックスコンバーター"

* 標準 Oak インデックス定義に対する変更は、AEM のアップグレード中に失われることがあります。
* Oak の定義は不変であるため、カスタムプロジェクトコードでパッケージ化します。またデプロイは Cloud Manager を使用してのみ行います。
* Oak インデックス定義はすべて、AEM as Cloud Service での Oak インデックスに関する命名規則、その他のルールに準拠する必要があります。準拠していない定義は、意図しない動作の原因になります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認し、プロジェクトの OID 違反を解決する方法を把握します。また、GitHub の OID 違反例を確認して、インデックスコンバーターツールを使用して従来のインデックスを変換し、AEM as a Cloud Service に対応させる方法も理解します。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID 違反の例 - GitHub"

* メッセージで特定されたインデックスルールの違反を解決します。
* Oak インデックスの新しい定義やカスタム定義をデプロイする場合は、AEM as a Cloud Service の[パッケージガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja)に従ってください。
* カスタマイズした AEM 標準インデックス、および新規のカスタム Oak インデックスの定義は、AEM as Cloud Service の「[コンテンツインデックス作成ガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=ja#preparing-the-new-index-definition)」に従う必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [OID 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)を修正および変更する方法を確認します。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
* [インデックスコンバーター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html?lang=ja#refactoring-tools)を使用して、既存のカスタム Oak インデックス定義を AEM as a Cloud Service と互換性のあるカスタム Oak インデックス定義に移行します。
